# InstallR [![Build Status](https://travis-ci.org/horver/InstallR.svg?branch=master)](https://travis-ci.org/horver/InstallR)

Installs libraries for an R script

## What is this?
This little package can install and load libraries which are needed for any R script. It scan through the script file, then install the dependencies. Also you can define a yaml file, that contains the dependencies and the package will load/install them.

### Why?
I wrote this package for fun and learning purpose. But I hope, that it will may useful for somebody.

## Usage

### Installing

```r
library(devtools)
install_github("horver/InstallR")
```

### Functions

- `install_from_list` Install and load from vector:

This function installs and loads (if `load` `TRUE`) the libraries which are given by a `c()` vector.
```r
install_from_list(c("RUnit", "caret"), load = TRUE)
```

- `install_from_script` Install and load from file(s):

This function scans through an R script or scripts ( `c("file1.R", "file2.R")` ) then
installs and loads (if load TRUE) the libraries.
```r
install_from_script("file.R", load = TRUE)
```

- `install_from_yml` Install and load from YAML:

Needed libraries are in a `*.yml` file. The structure should look like this:

```yaml
deps:
  - testthat
  - RUnit
  - caret
load: true
```
And usage of the function: 

```r
install_from_yml("deps.yml", load = TRUE)
```
