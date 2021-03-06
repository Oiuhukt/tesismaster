-----------------------------

# tesismaster

Este es el repositorio donde guardo el código de mi tesis de maestría. Para compilar el archivo en un pdf tomé el makefile creado por [alejandrogallo](https://github.com/alejandrogallo/latex-makefile/releases/latest). Pongo sus instrucciones originales abajo. También pueden ver el documento en [Papeeria](https://www.papeeria.com/join?token_id=d76b5624-5fd1-4757-a74d-47f63964aec1&retry=3)

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /> Este trabajo está bajo la licencia <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.


----------------------------------


# The ultimate TeX Makefile #

## Installing ##

Just get a built makefile from
[the latest release](
https://github.com/alejandrogallo/latex-makefile/releases/latest
) and put it in your TeX project folder.

## Building ##

To build you have to initialize the submodules:

```
git submodule init
git submodule update
```

and then just hit

```
make
```
You will need the macro processor `m4`.


## Quick start ##

Just drop the Makefile in your project directory and hit make.  The makefile
should recognise the main document automatically by looking for a
`\begin{document}` in the `tex` file of the current directory.

The main idea of the makefile is not to modify it directly, but rather through
a `make` configuration file `config.mk`. There you can set many important
variables for the project, like the verbosity `QUIET=1` and many more.


## Features overview ##


  * Build in a different directory.
  * Multi bibtex files.
  * Automatic handling of the table of contents (smart recompilation).
  * Automatic handling of [bibtex](http://www.bibtex.org/) (smart recompilation).
  * Import `.sty` files (latex packages) from custom directory.
  * Distribution making for sending documents to the publisher.
  * Automatic recognition of included graphics.
    - Automatic [asymptote](http://asymptote.sourceforge.net/) compilation.
    - Automatic [gnuplot](http://www.gnuplot.info/) compilation.
    - Automatic `python` figures compilation.

## Overridable variables ##
  * `VAR_NAME`(`DEFAULT`):  Brief description. If the default value is too long to appear it is
    omitted and a `see` is put in its place.  If there is no default value then
    the keyword `empty` appears.

  * `SH`(`bash`): Shell used
  * `SHELL`(`see`): Alias for `SHELL'
  * `PY`(`python`): Python interpreter
  * `PYTHON`(`see`): Alias for `PY'
  * `PERL`(`perl`): Perl command
  * `GREP`(`grep`): Grep program version
  * `FIND`(`find`): Find utility
  * `SED`(`see`): `sed` program version
  * `AWK`(`see`): `awk` program to use
  * `CTAGS`(`ctags`): For creating tags
  * `READLINK`(`see`): To get complete paths
  * `XARGS`(`xargs`): `xargs` program to use
  * `TR`(`tr`): `tr` program to use
  * `GIT`(`git`): `git` version to use
  * `WHICH`(`which`): `which` program to use
  * `SORT`(`sort`): `sort` program to use
  * `UNIQ`(`uniq`): `uniq` program to use
  * `MAKE`(`see`): `Makefile` binary
  * `RM`(`rm`): `rm` command
  * `CXX`(`g++`): C++ compiler
  * `CC`(`gcc`): C compiler
  * `FC`(`gfortran`): Fortran compiler
  * `BUILD_DIR`(`.`): Folder to build the project
  * `LATEX`(`pdflatex`): Shell utilities
  * `PDFLATEX`(`pdflatex`): Main pdflatex engine
  * `QUIET`(`0`): If secondary programs output is shown
  * `QQUIET`(`empty`): If the log messages should be also muted
  * `DEBUG`(`empty`): If the commands issued should be printed write `DEBUG=1` if you want to see all commands.
  * `TPUT`(`see`): For coloring
  * `WITH_COLOR`(`1`): If messages should have color
  * `DBG_FILE`(`.makefile-dbg`):
  * `COLOR_R`(`see`): Red
  * `COLOR_G`(`see`): Green
  * `COLOR_Y`(`see`): Yellow
  * `COLOR_DB`(`see`): Dark blue
  * `COLOR_L`(`see`): Lila
  * `COLOR_LB`(`see`): Light blue
  * `COLOR_E`(`see`): Empty color
  * `ARROW`(`@echo "see`):
  * `ARROW`(`@echo "===>"`):
  * `ECHO`(`@echo`):
  * `MAIN_SRC`(`see`): Main texfile in the current directory
  * `FMT`(`pdf`): Format to build to
  * `VIEW`(`1`): If `BUILD_DOCUMENT` should be previewed after building
  * `INCLUDES_REC`(`3`): Depth for discovering automatically included texfiles
  * `INCLUDES`(`see`): Texfiles included in the main tex file
  * `TEXFILES`(`see`): All `texfiles` in the project
  * `BIBTEX_FILES`(`see`): Bibtex files in the current directory
  * `PREFIX`(`see`): Source directory
  * `BUILD_DIR`(`.`): Folder to build the project
  * `BUILD_DIR_FLAG`(`see`): Build dir flag for latex. If `BUILD_DIR = .` then `BUILD_DIR_FLAG` is not defined, else `BUILD_DIR = -output-directory $(BUILD_DIR)`
  * `PACKAGES_DIR`(`libtex`): Tex libraries directory
  * `PACKAGES_FILES`(`see`): Which files are tex libraries
  * `DEFAULT_DEPENDENCIES`(`\`): Default dependencies for `BUILD_DOCUMENT`
  * `DEPENDENCIES`(`see`): General dependencies for `BUILD_DOCUMENT`
  * `TOC_DEP`(`see`): These files  are to keep  track of the  dependencies for latex  or pdf includes, table of contents generation or figure recognition
  * `FIGS_DEP`(`see`):
  * `DEPS_DIR`(`.deps`): Folder to keep makefile dependencies
  * `FIGURES`(`empty`): Figures included in all texfiles
  * `BIBTEX`(`bibtex`): For converting document formats
  * `ASYMPTOTE`(`asy`): For asymptote figures
  * `GNUPLOT`(`gnuplot`): Gnuplot interpreter
  * `PDF_VIEWER`(`see`): Recognise pdf viewer automagically
  * `RM`(`rm`): Remove command
  * `RM_FLAGS`(`-rf`):
  * `CLEAN_FILES`(`see`): Files to be cleaned
  * `DIST_DIR`(`dist`): Distribution directory
  * `LATEXDIFF`(`latexdiff-git`): For creating differences in a repository
  * `DIFF`(`HEAD HEAD~1`): Commits to compute the difference from
  * `DIFF_BUILD_DIR_MAIN`(`diffs`):
  * `DIFF_BUILD_DIR`(`see`):
  * `DIFF_SRC_NAME`(`diff.tex`):
  * `SPELLER`(`aspell`): Speller program to use
  * `SPELL_DIR`(`.spell`): Directory to store spelling related information
  * `SPELL_LANG`(`en`): Language for the spelling program
  * `CHECK_SPELL`(`empty`): Wether or not spelling should be checked
  * `TEX_LINTER`(`chktex`): For checking tex syntax
  * `MAKEFILE_UPDATE_URL`(`see`):
  * `CTAGS_OPTIONS`(`--language-force=latex -R *`): Options for ctags command



## Targets ##
### Bibliography generation ###


This generates a `bbl` file from a  `bib` file For documents without a `bib`
file, this  will also be  targeted, bit  the '-' before  the `$(BIBTEX)`
ensures that the whole building doesn't fail because of it

```bash
make $(BIBITEM_FILES)
```
### Force compilation ###


This makefile only compiles the TeX document if it is strictly necessary, so
sometimes to force compilation this target comes in handy.

```bash
make force
```
### View document ###


Open and refresh pdf.

```bash
make view-pdf
```
### Open pdf viewer ###


Open a viewer if there is none open viewing `$(BUILD_DOCUMENT)`

```bash
make open-pdf
```
### Refresh mupdf ###


If the opened document is being viewed with `mupdf` this target uses the
mupdf signal API to refresh the document.

File: clean.m4
Remove command
Default clean file to be cleaned
Files to be cleaned

Main cleaning


This does a main cleaning of the produced auxiliary files.  Before using it
check which files are going to be cleaned up.

```bash
make clean
```
### Distribution ###


Create a distribution folder wit the bare minimum to compile your project.
For example it will consider the files in the DEPENDENCIES variable, so make
sure to update or add DEPENDENCIES to it in the config.mk per user
configuration.

```bash
make dist
```
### Distribution clean ###


Clean distribution files

```bash
make dist-clean
```
### Diff ###


This target creates differences between older versions of the main latex file
by means of [GIT](https://git-scm.com/). You have to specify the commits that
you want to compare by doing

```bash
make DIFF="HEAD HEAD~3" diff
```
If you want to compare the HEAD commit with the commit three times older than
HEAD. You can also provide a *commit hash*. The default value is `HEAD HEAD~1`.

The target creates a distribution folder located in the variable
`DIFF_BUILD_DIR`.
```bash
make diff
```
### Check spelling ###


It checks the spelling of all the tex sources using the program in the
SPELLER variable. The default value of the language is english, you can
change it by setting in your `config.mk` file
```make
SPELL_LANG = fr
```
if you happen to write in french.

Wether to check spelling or not is controlled by the `CHECK_SPELL`
variable, so if you want to check spelling set it to one
```make
CHECK_SPELL = 1
```
otherwise do not set it.

```bash
make spelling
```
### Check syntax ###


It checks the syntax (lints) of all the tex sources using the program in the
TEX_LINTER variable.

```bash
make lint
```
### Update the makefile from source ###


You can always get the  latest `Makefile` version using this target.  You may
override the `MAKEFILE_UPDATE_URL` to  any path where you save your own
personal makefile

```bash
make update
```
### Ctags generation for latex documents ###


Generate a tags  file so that you can navigate  through the tags using
compatible editors such as emacs or (n)vi(m).

```bash
make tags
```
### Print a variable used by the Makefile ###


For debugging purposes it is useful to print out some variables that the
makefile is using, for that just type `make print` and you will be prompted
to insert the name of the variable that you want to know.

```bash
make FORCE
```
### Print quick help ###


It prints a quick help in the terminal
```bash
make help
```
