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
