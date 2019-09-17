Data Wrangling 1
================
Junhui Mi
2019/9/17

## Load in a dataset from CSV

``` r
## reads in a dataset
litters_data = read_csv("FAS_litters.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   Group = col_character(),
    ##   `Litter Number` = col_character(),
    ##   `GD0 weight` = col_double(),
    ##   `GD18 weight` = col_double(),
    ##   `GD of Birth` = col_double(),
    ##   `Pups born alive` = col_double(),
    ##   `Pups dead @ birth` = col_double(),
    ##   `Pups survive` = col_double()
    ## )

``` r
litters_data = janitor::clean_names(litters_data)
```

    ## Warning in FUN(X[[i]], ...): strings not representable in native encoding
    ## will be translated to UTF-8

``` r
pups_data = read_csv("FAS_pups.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   litter_number = col_character(),
    ##   sex = col_double(),
    ##   pd_ears = col_double(),
    ##   pd_eyes = col_double(),
    ##   pd_pivot = col_double(),
    ##   pd_walk = col_double()
    ## )

``` r
pups_data = janitor::clean_names(pups_data)
skimr::skim(pups_data)
```

    ## Skim summary statistics
    ##  n obs: 313 
    ##  n variables: 6 
    ## 
    ## -- Variable type:character ---------------------------------------------------------
    ##       variable missing complete   n min max empty n_unique
    ##  litter_number       0      313 313   3  15     0       49
    ## 
    ## -- Variable type:numeric -----------------------------------------------------------
    ##  variable missing complete   n  mean   sd p0 p25 p50 p75 p100     hist
    ##   pd_ears      18      295 313  3.68 0.59  2   3   4   4    5 ▁▁▅▁▁▇▁▁
    ##   pd_eyes      13      300 313 12.99 0.62 12  13  13  13   15 ▂▁▇▁▁▂▁▁
    ##  pd_pivot      13      300 313  7.09 1.51  4   6   7   8   12 ▃▆▇▃▂▁▁▁
    ##   pd_walk       0      313 313  9.5  1.34  7   9   9  10   14 ▁▅▇▅▃▂▁▁
    ##       sex       0      313 313  1.5  0.5   1   1   2   2    2 ▇▁▁▁▁▁▁▇

``` r
write_csv(pups_data, path = "FAS_pups.csv")
```

## Read from Excel

``` r
## reads in a dataset from excel
mlb11_data = read_excel("mlb11.xlsx", range = "A1:D7")
```

## Read from SAS

``` r
## reads in a dataset from SAS
pulse_data = read_sas("public_pulse_data.sas7bdat")
```
