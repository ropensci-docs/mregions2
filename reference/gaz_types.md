# Get all the place types of the Marine Regions Gazetteer

Get all the place types of the Marine Regions Gazetteer

## Usage

``` r
gaz_types()
```

## Value

a data frame with three columns:

- `typeID`: the identifier of the place type in the Marine Regions
  Gazetteer database.

- `type`: the name of the place type.

- `description`: if available, the description of the place type.

## See also

[gaz_rest](https://docs.ropensci.org/mregions2/reference/gaz_rest.md)

## Examples

``` r
# \donttest{
# This
gaz_rest_types()
#> Error in httr2::req_perform(.): HTTP 503 Service Unavailable.

# is the same as
gaz_types()
#> Error in httr2::req_perform(.): HTTP 503 Service Unavailable.
# }
```
