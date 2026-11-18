# Recipes

## Todo

In no particular order:

* Recipe photos
* Layout and styling

## Recipes to Add

* Filipino turmeric-scented pork stew
* Fake curry
* Lasagne

## Compiling

Build the PDF locally with Docker Compose:

```sh
HOST_UID="$(id -u)" HOST_GID="$(id -g)" docker compose run --rm build
```
The Docker image is pinned by digest so local and GitHub Actions builds use the
same TeX Live environment. The generated `recipes.pdf` is written in the
repository root.


## Adding New Recipes

Add a new file into the relevant chapter folder (e.g. `src/recipes/dinner/steak.tex`) and add a to it file into its 
folder's `_index.tex`.

### Index Reference

```latex
\subfile{steak}
```

### New Recipe Template

```latex
\clearpage
\section{Recipe Name}

\index{author!John Doe}
\index{meat!beef!steak}
\index{starch!rice}
\index{country!Mexico}
\index{stew}
  
Source: https://example.com/link/to/recipe

Recipe notes go here.

\subsection{Ingredients}

\begin{itemize}
    \item 1 bread
    \item \sfrac{1}{2} tbsp stuff
\end{itemize}

Ingredient notes go here

\subsection{Method}

\begin{enumerate}
    \item Do a thing at \celsius{180}.
    \item Do another thing.
\end{enumerate}
```

