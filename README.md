# mapix
A set of simple bash commands that bring r-spatial tools to the Linux command line. My motivation for writing these were a bunch of geojson files I had to go through, some of them just needed visual inspection, others needed some editing.

## Installation
### Installing R and r-spatial tools
These scripts assume that [R](https://www.r-project.org/) along with the packages [sf](https://github.com/r-spatial/sf), [mapview](https://github.com/r-spatial/mapview), and [mapedit](https://github.com/r-spatial/mapedit) are all installed already. To install R, downlaod from [your favorite CRAN mirror](https://github.com/r-spatial/mapedit). Once you have R installed, open an R session, and install `sf`, `mapview`, and `mapedit` by running the following command:

```r
install.packages(c("sf", "mapview", "mapedit"))
```
Or, to make sure you get the latest features in these libraries, install with [devtools](https://github.com/hadley/devtools):

```r
install.packages("devtools")
devtools::install_github("r-spatial/sf")
devtools::install_github("r-spatial/mapview")
devtools::install_github("r-spatial/mapedit")
```
### Installing mapix
For debian-based systems, download the `mapix.deb` file and install with `apt`. Otherwise download the scripts in the `src` directory and place them in your `/usr/local/bin/` directory. Give yourself permission to read and execute the scripts (e.g. `sudo chmod 755 /usr/local/bin/Rint` etc) and you're all set!


## Usage
### Rint

`Rint` is a trick by [Jon Gjengset](https://github.com/jonhoo) to get R to run a script interactively. Check out [his explanation for how it works](https://thesquareplanet.com/blog/interactive-r-scripts/). I changed it slightly to allow the R script to accept command line arguments. The commands are all executed with `Rint`.

### mapcreate
Usage: `mapcreate `_`filename`_

This will create a new file with the given filename with the drawn features. Make sure it has a valid extension like '.geojson', '.shp', '.kml', etc.

### mapupdate
Usage: `mapupdate `_`input_filename`_ _`[output_filename]`_

This is used to edit an existing file. If you call `mapupdate` with just one filename, your edits will overwrite the original file with your edits. If you call it with two filenames, the first will be used as the input file, and the second will be the new file where the edits will be written to.

### mapview
Usage: `mapview `_`filename`_

If you just want to inspect a file visually, use `mapview`. 

All of the commands should open in the default browser.
