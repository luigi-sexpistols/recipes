# Agent Instructions

## Repository layout

- `src/recipes.tex` is the main LaTeX document.
- Recipe chapters live in `src/recipes/<chapter>/`.
- Every chapter's `_index.tex` contains `\subfile{...}` entries for its recipes.
- Generated LaTeX files and `recipes.pdf` are build artifacts and should not be committed.

## Adding recipes

1. Put the recipe in the appropriate chapter directory as a descriptive, lowercase, hyphenated `.tex` filename.
2. Follow the recipe template in `readme.md`: `\clearpage`, `\section`, relevant `\index` entries, source, ingredients and method.
3. Use existing macros and packages: for example, `\celsius{180}`, `\sfrac{1}{2}` and `\begin{multicols}{2}`.
4. Add the recipe to that directory's `_index.tex`.
5. Include author, website and source URL where the recipe has an external source. Paraphrase recipe prose rather than copying nonessential narrative.
6. Update completed items in `readme.md` or chapter TODO comments when a listed recipe is added.

## Building

Use Docker Compose for local builds:

```sh
HOST_UID="$(id -u)" HOST_GID="$(id -g)" docker compose run --rm build
```

Do not revert to the previous MiKTeX volume command. `compose.yaml` pins a TeX Live image by digest and uses `latexmk -gg` to force a complete build, including tables of contents and indexes. GitHub Actions runs the same Compose service, so reproduce CI locally with this command.

After building:

- Confirm that `recipes.pdf` exists in the repository root.
- For recipe changes, verify the new section names are present in the PDF, for example with `pdftotext recipes.pdf -`.

## Git workflow

- By default, update `main` and create new feature branches from it. Use another base branch only when explicitly requested.
- Keep unrelated working-tree changes unstaged and out of the commit.
- Stage only files that belong to the requested task and review `git diff --cached` before committing.
- Include the configured Copilot co-author trailer when committing.
- Push with the branch's configured `origin`; this repository uses the SSH alias `git@luigi.github.com`.
- Do not rewrite history unless explicitly requested.
