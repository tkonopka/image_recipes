# image_recipes

Collection of command-line scripts for image conversions.

These bash scripts are fairly simple wrappers for ghostscript, pdflatex, cwebp. Script with names ending in '2' perform two rounds of conversions at single- and double-resolution. 


## Examples

### From pdf

A standard conversion from pdf to png and webp file formats.

```
./pdf2webp2 figure.pdf
```

The conversion generates two png files (`figure@1.png` and `figure@2.png`) and two webp files (`figure@1.webp` and `figure@2.webp`). The files contins single-resolution and double-resolution images.

The default single- and double-resolution settings are 150dpi and 300dpi. The default webp compression quality is 95. These settings can be changed via environment variables.

```
dpi=300 cwebp_q=99 ./pdf2webp2 figure.pdf
```


### From tex

The `tex2webp2` script convert tex content (e.g. equations) to images. The tex content is expected without tex-document boilerplate. An example:

```
$$
\sum_{n=0}^\infty \frac{1}{n^2} = \frac{\pi^2}{6}
$$
```

Conversion of the tex file into a figure.

```
tex2webp2 equation.tex
```

The conversion produces a pdf, two png files, and two webp files.


