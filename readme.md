# recipes
Luigi Sexpistols' Recipes

## Compiling

Using Docker:

```sh
docker run -it --rm \
    -v miktex:/miktex/.miktex \
    -v `pwd`:/miktex/work \
    miktex/miktex pdflatex src/recipes.tex
```

## Adding New Recipes

Add a new file into the relevant chapter folder (e.g. `src/recipes/dinner/steak.tex`) using the following template:

```latex
\section{Recipe Name}
  
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
      \item Do a thing.
      \item Do another thing.
    \end{enumerate}
```

Add a reference to this file into `src/recipes/dinner/_index.tex`.

