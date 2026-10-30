# Search in the Marine Regions Gazetteer by names, MRGID or reverse geocode with a pair of WGS84 coordinates x and y

Search in the Marine Regions Gazetteer by names, MRGID or reverse
geocode with a pair of WGS84 coordinates x and y

## Usage

``` r
gaz_search(x, ...)

# S3 method for class 'character'
gaz_search(x, ...)

# S3 method for class 'numeric'
gaz_search(x, ..., y = NULL)

# S3 method for class 'sfg'
gaz_search(x, ...)

# S3 method for class 'sf'
gaz_search(x, ...)

# S3 method for class 'sfc'
gaz_search(x, ...)
```

## Arguments

- x:

  object to perform the search with. Can be:

  - (character) Free text search

  - (integer) A valid Marine Regions Gazetteer Identifier
    ([MRGID](https://docs.ropensci.org/mregions2/reference/MRGID.md))

  - (double) Longitude in WGS84

  - Aditionally, you can pass objects of class
    [sf::sf](https://r-spatial.github.io/sf/reference/sf.html) or
    [sf::sfc](https://r-spatial.github.io/sf/reference/sfc.html) with
    geometry of class `POINT`

- ...:

  Arguments passed on to
  [`gaz_rest_record_by_mrgid`](https://docs.ropensci.org/mregions2/reference/gaz_rest_record_by_mrgid.md),
  [`gaz_rest_records_by_name`](https://docs.ropensci.org/mregions2/reference/gaz_rest_records_by_name.md),
  [`gaz_rest_records_by_names`](https://docs.ropensci.org/mregions2/reference/gaz_rest_records_by_names.md),
  [`gaz_rest_records_by_lat_long`](https://docs.ropensci.org/mregions2/reference/gaz_rest_records_by_lat_long.md)

  `with_geometry`

  :   (logical) Add geometry to the result data frame? Default = FALSE

  `rdf`

  :   (logical) Return an object of class
      [rdflib::rdf](https://docs.ropensci.org/rdflib/reference/rdf.html)?

  `typeid`

  :   (numeric) Restrict to one or more placetypeIDs. Retrieve a list of
      placetypeIDs with
      [`gaz_rest_types()`](https://docs.ropensci.org/mregions2/reference/gaz_rest_types.md)

  `language`

  :   (character) Restrict to one language. Provide as a 2 digits
      ISO-639. See ISOcodes::ISO_639_2.

  `like`

  :   (logical) Add a '%'-sign before and after the name? (SQL LIKE
      function). Default = TRUE

  `fuzzy`

  :   (logical) Use Levenshtein query to find nearest matches? Default =
      TRUE

- y:

  (double) Latitude in WGS84 (Optional)

## Value

A data frame with Gazetteer entries

## Examples

``` r
# \donttest{

# Look-up a name in the Gazetteer
gaz_search("North Sea")
#> Error in gaz_rest_records_by_name(x, ...): HTTP 503 Service Unavailable.

# Get the entries of two known MRGID including their geometry
gaz_search(c(14, 17), with_geometry = TRUE)
#> Error in FUN(X[[i]], ...): HTTP 503 Service Unavailable.

# Maybe the name is in another language...
gaz_search("Noordzee", language = "nl")
#> Error in gaz_rest_records_by_name(x, ...): HTTP 503 Service Unavailable.

# Get all the records intersecting with the longitude 51.21551 and latitude 2.927
# restricting to some placetypes
gaz_search(x = 2.927, y = 51.21551, typeid = c(255, 259))
#> Error in gaz_rest_records_by_lat_long(latitude, longitude, ...): HTTP 503 Service Unavailable.
# }
```
