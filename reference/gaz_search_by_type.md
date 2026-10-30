# Retrieve Gazetteer Records by Placetype

Retrieve Gazetteer Records by Placetype

## Usage

``` r
gaz_search_by_type(x, ...)

# S3 method for class 'character'
gaz_search_by_type(x, ...)

# S3 method for class 'numeric'
gaz_search_by_type(x, ...)
```

## Arguments

- x:

  A [place
  type](https://docs.ropensci.org/mregions2/reference/gaz_types.md).
  Either:

  - (character) The name of a place type.

  - (integer) The typeid of a place type.

- ...:

  Arguments passed on to
  [`gaz_rest_records_by_type`](https://docs.ropensci.org/mregions2/reference/gaz_rest_records_by_type.md)

  `type`

  :   (character) The placetype from
      [`gaz_rest_types()`](https://docs.ropensci.org/mregions2/reference/gaz_rest_types.md)

  `with_geometry`

  :   (logical) Add geometries to the result data frame? Default = FALSE

## Value

A data frame with Gazetteer entries

## See also

[`gaz_types()`](https://docs.ropensci.org/mregions2/reference/gaz_types.md)

## Examples

``` r
# \donttest{
# This
gaz_search_by_type("EEZ")
#> Error in FUN(X[[i]], ...): HTTP 503 Service Unavailable.

# is the same as
gaz_search_by_type(70)
#> Error in httr2::req_perform(.): HTTP 503 Service Unavailable.
# }
```
