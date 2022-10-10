
<!-- README.md is generated from README.Rmd. Please edit that file -->

# rirods2

<!-- badges: start -->
<!-- badges: end -->

The goal of rirods2 is a pure R client for iRODS

## Installation

You can install the development version of rirods2 like so:

``` r
# install.packages("devtools")
devtools::install_github("MartinSchobben/rirods2")
```

## Example

This is a basic example which shows you how to quickly launch a local
iRODS. For more information check <https://github.com/irods/irods_demo>.

``` bash
# clone the repo
# git clone https://github.com/irods/irods_demo
# initiate git submodules
# git submodule update --init
# to start
cd ../irods_demo
docker-compose up
```

To connect with the iRODS server on can do the following:

``` r
library(rirods2)

# get token
tk <- get_token()

# add user bobby
riadmin(token = tk, action = "add", target = "user", arg2 = "bobby", 
        arg3 = "rodsuser")

# check if bobby is added
rils(token = tk)

# remove user bobby
riadmin(token = tk, action = "remove", target = "user", arg2 = "bobby")

# check if bobby is removed
rils(token = tk)
```

## Stop your local iRODS server

``` bash
docker-compose down
```
