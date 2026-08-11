# Microeconomica — published site

This repo publishes the [Microeconomica](content/README.md) knowledge vault (an Introduction to Microeconomics course, built around Osborne & Rubinstein's *Models in Microeconomic Theory*) as a website using [Quartz](https://quartz.jzhao.xyz/), deployed to GitHub Pages via the workflow in `.github/workflows/deploy.yml`.

- Vault content lives entirely under [`content/`](content/) — see [`content/README.md`](content/README.md) for the vault's own format, sourcing, and reading order documentation.
- Quartz tooling (everything outside `content/`) is MIT-licensed, from [jackyzha0/quartz](https://github.com/jackyzha0/quartz) — see `LICENSE.txt`.
- TikZ figures render client-side via [TikZJax](https://github.com/artisticat1/tikzjax) (`quartz/components/scripts/tikzjax.inline.ts`), matching how they render in Obsidian.

## Updating the site (Part I / Part II content)

1. Edit the vault (either directly in `content/`, or in the original Obsidian vault and copy changes into `content/`). If you sync with `rsync -a --delete Microeconomica/ content/`, note that `content/index.md` is **repo-only** (it doesn't exist in the source vault) and `--delete` will remove it — recreate it from git history (`git checkout -- content/index.md`) or re-add it by hand if that happens.
2. `npx quartz build --serve` to preview locally.
3. Commit and push to `main` — the GitHub Actions workflow rebuilds and redeploys automatically.

## Updating the TD tutorials section (password-protected)

The `td-tutorials/` folder in the vault (exercises, solutions, and private teaching notes for running tutorial sessions) is **never committed to this repo in plaintext** — `content/td-tutorials/` is gitignored, and Quartz's own build never sees it. Instead, the section is pre-rendered and encrypted locally, and only the ciphertext is committed under `static-protected/td-tutorials/`, which the CI workflow copies into the build output after the normal Quartz build. This keeps the raw exercises/solutions out of the public git history entirely, since GitHub Pages on this account requires a public repo.

To publish an update to this section after editing it in the vault:

1. Copy the updated `td-tutorials/` folder from the vault into `content/td-tutorials/` (temporarily — it's gitignored, so this is safe to do locally without risk of committing it).
2. `npx quartz build` — renders the TD pages with the real site theme (same header/footer/CSS as everything else).
3. Remove `content/td-tutorials/` again immediately: `rm -rf content/td-tutorials`.
4. Encrypt the rendered pages in place, overwriting `static-protected/td-tutorials/` with the new ciphertext:
   ```bash
   npx staticrypt public/td-tutorials/* -r -d static-protected/td-tutorials
   ```
   (leave the glob unquoted so the shell expands it — a quoted glob gets passed to StatiCrypt literally and fails with `ENOENT`.)
   This will prompt for the password interactively (or read it from `STATICRYPT_PASSWORD` in your shell env / a local `.env` file — never commit that env file). Re-use the same password as before so existing bookmarked/"remember me" sessions keep working; the pinned salt in the committed `static-protected/td-tutorials/.staticrypt.json` (not secret — see [StatiCrypt's docs](https://github.com/robinmoisson/staticrypt#why-does-staticrypt-create-a-config-file)) keeps re-encryptions consistent.
5. `rm -rf public` (discard the local build — it's gitignored anyway, just cleaning up).
6. Commit only `static-protected/td-tutorials/` and push to `main`.

**Never commit `content/td-tutorials/`.** If you ever see it staged in `git status`, that's a mistake — unstage it before committing.
