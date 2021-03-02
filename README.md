
<!-- README.md is generated from README.Rmd. Please edit that file - rmarkdown::render('README.Rmd', output_format = 'github_document', output_file = 'README.md') -->

# Plumabato

<!-- badges: start -->

![Bitbucket open
issues](https://img.shields.io/bitbucket/issues-raw/NiccoloSalvini/plumbato?style=flat-square)
<!-- badges: end -->

<br> <br>

This is a simple *template* package illustrating how to incorporate
`Plumber` framework for APIs into an R package. It blends the existing
library `plungr` test for robust production grade API in R, inspired by
the [Golem](https://thinkr-open.github.io/golem/) software framework
with the `Plumbpkg` by James Blair and the [RSudio Solution
Engineering](https://github.com/sol-eng/plumbpkg).

There are two main motivations behind this example:

1.  Demonstrate how to build Plumber APIs into a package with a *robust
    sf framework* (originally developed for Shinyapps)
2.  Demonstrate how to test Plumber APIs using
    [testthat](https://testthat.r-lib.org)

## Architecture ▶️

The design of this package is heavily influenced by [this
discussion](https://community.rstudio.com/t/plumber-api-and-package-structure/18099)
on RStudio Community.

    ── DESCRIPTION
    ├── LICENSE
    ├── LICENSE.md
    ├── NAMESPACE
    ├── R
    │   ├── api1.R
    │   └── api2.R
    ├── README.md
    ├── inst
    │   └── plumber
    │       ├── api1
    │       │   └── plumber.R
    │       └── api2
    │           ├── entrypoint.R
    │           └── plumber.R
    ├── man
    ├── plumbpkg.Rproj
    └── tests
        ├── testthat
        │   ├── test-api1.R
        │   ├── test-api2.R
        │   └── test-plumber.R
        └── testthat.R

The `R/` directory contains all of the R functions used in the Plumber
APIs. This enables the functions to be tested using files in the
`tests/` directory. The Plumber APIs are defined in files in
`inst/plumber/` and are also tested using testthat and
[httr](https://httr.r-lib.org).

## Deploy 🌀

This repository deploys both APIs to [RStudio
Connect](https://www.rstudio.com/products/connect/) using
[Travis](https://travis-ci.org/). The deployment is managed by
[`scripts/deploy-rsc.sh`](scripts/deploy-rsc.sh) and uses the RStudio
Connect API. Because this repository uses Travis, the APIs will only be
deployed **after** tests have successfully completed.

There are certainly other ways this content could be deployed, either
using other CI/CD solutions or using [RStudio Connect’s ability to
publish content from a git
repository](https://docs.rstudio.com/connect/1.7.6/user/git-backed.html).

### License:

[![License:
MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
