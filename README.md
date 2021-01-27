# image_recipes

Collection of command-line scripts for image conversions.

These scripts are wrappers for ghostscript, pdflatex, cwebp. Script with names ending in '2' perform two rounds of conversions at single- and double-resolution. 


## Examples

### From pdf

The `pdf2png2` and `pdf2webp2` scripts are similar. They perform conversions from pdf to other image formats.

```
./pdf2webp2 figure.pdf
```

The conversion generates two png files (`figure@1x.png` and `figure@2x.png`) and two webp files (`figure@1x.webp` and `figure@2x.webp`). The files are single-resolution (1x) and double-resolution (2x) images.

The default single- and double-resolution settings are 150 dpi and 300 dpi. The default webp compression quality is 95. These settings can be changed via environment variables.

```
dpi=300 cwebp_q=99 ./pdf2webp2 figure.pdf
```


### From tex

The `tex2webp2` script converts tex content (e.g. equations) to images. The content is expected without tex boilerplate. As an example, a file `equation.tex` below has three lines which define an equation.

```
$$
\sum_{n=0}^\infty \frac{1}{n^2} = \frac{\pi^2}{6}
$$
```

The script converts the tex file into images.

```
tex2webp2 equation.tex
```

The conversion produces a pdf, two png files, and two webp files.


