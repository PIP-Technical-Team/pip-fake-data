
<!-- README.md is generated from README.Rmd. Please edit that file -->

# pip-fake-data

The goal of pip-fake-data is to enable end-users to more easily explore
the computations that generates the poverty and inequality statistics
published on [PIP](https://pip.worldbank.org/home)

Since most data used in PIP are confidential microdata, this fake
dataset has been created to match the exact format expected by the
[pipapi](https://github.com/PIP-Technical-Team/pipapi) package.

# Getting started

Make sure the `pipapi` package is installed on your machine.

``` r
library(pipapi)
#> Warning: package 'pipapi' was built under R version 4.1.2
#> Info: Disk based caching is enabled.
lkups <- create_versioned_lkups(data_dir = ".")
lkups$versions
#> [1] "20211212_2011_01_01_PROD" "20200101_2011_01_01_PROD"
```
