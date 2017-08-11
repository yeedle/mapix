# mapix
A set of scripts that bring r-spatial tools to the Linux command line. My motivation for writing these were a bunch of geojson files I had to go through, some of them just needed visual inspection, others needed some editing.

## Installation
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

Download the scripts in `src` directory and place them in your `/usr/local/bin/` directory. Give yourself permission to read and execute the scripts (`sudo chmos 755 /usr/local/bin/Rint` etc). You're all set!


## Usage
### Rint

`Rint` is a trick by [Jon Gjengset](https://github.com/jonhoo) to get R to run a script interactively. Check out [his explanation for how it works](https://thesquareplanet.com/blog/interactive-r-scripts/). I changed it slightly to allow the R script to accept command line arguments.

### mapcreate
Usage: `mapcreate filename`

This will create a new file with the given filename with the drawn features. Make sure it has a valid extension like '.geojson', '.shp', '.kml', etc.

### mapupdate
Usage: `mapupdate input_filename [output_filename]`

This is used to edit an existing file. If you call `mapupdate` with just one filename, your edits will overwrite the original file with your edits. If you call it with two filenames, the first will be used as the input file, and the second will be the new file where the edits will be written to.

### mapview
Usage: `mapview filename`

If you just want to inspect a file visually, use `mapview`. 

All of the commands should open in the default browser.
