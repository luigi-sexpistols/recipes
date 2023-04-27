# Recipes

## Todo

In no particular order:

* Recipe photos
* Layout and styling
* [Automatic discovery of included files (chapter indices, recipes, etc)](https://tex.stackexchange.com/questions/200937/how-to-automatically-include-several-text-documents-into-a-latex-document)

## Recipes to Add

* Filipino turmeric-scented pork stew
* Fake curry
* Chicken with almonds
* Lasagne

## Compiling

Using Docker:

```sh
docker run -it --rm \
    -v miktex:/miktex/.miktex \
    -v `pwd`:/miktex/work \
    miktex/miktex pdflatex src/recipes.tex
```

## 

## Adding New Recipes

Add a new file into the relevant chapter folder (e.g. `src/recipes/dinner/steak.tex`) using the following template:

```latex
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
    \item Do a thing.
    \item Do another thing.
\end{enumerate}
```

Add a reference to this file into `src/recipes/dinner/_index.tex`.

