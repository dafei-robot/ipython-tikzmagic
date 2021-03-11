# ipython-tikzmagic

IPython magics for generating figures with TikZ. You can select the output format as svg, png or jpg, define the image size, specify a scale factor, load TikZ packages, and save to external files. The accompanying IPython notebooks shows some examples demonstrating how to use these features.

The package requires a working LaTeX installation, ImageMagick and pdf2svg.

## Installation

```pip install git+git://github.com/dafei-robot/ipython-tikzmagic.git```

## Usage

Load package by writing
```
%load_ext tikzmagic
```
in a notebook cell.
```
%%tikz
\draw (0,0) rectangle (1,1);
\filldraw (0.5,0.5) circle (.1);
```

## Optional Arguments

- `-sc` or `--scale`: scaling factor of plots, default=1
- `-s` or `--size`: pixel size of plots, e.g., `-s width,height`, default=400,240
- `-b` or `--border`: border of plots, default=0pt
- `-f` or `--format`: plot format (svg, png or jpg), default=svg
- `-e` or `--encoding`: text encoding, default=utf-8
- `-p` or `--package`: LaTeX packages to load, separated by comma, e.g., `-p pgfplots,textcomp`, default=None
- `-l` or `--library`: TikZ libraries to load, separated by comma, e.g., `-l matrix,arrows`, default=None
- `-g` or `--pgfplotslibrary`: Pgfplots libraries to load, separated by comma, e.g., `-l matrix,arrows`, default=None
- `-ct` or `--circuitikz`: Use CircuiTikZ package instead of regular TikZ, default=False
- `-po` or `--pictureoptions`: Additional arguments to pass to the `\tikzpicture` command, default=None
- `--raw`: Raw latex content, except for the leading `\documentclass` command, default=False
- `--showlatex`: Show the LATeX file instead of generating image, for debugging LaTeX errors, default=False
- `--imagemagick`: Name of ImageMagick executable, optionally with full path, default=`convert`
