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

## Template

Use this template for new recipes:

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
