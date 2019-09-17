Data Import
================
Ava Hamilton
9/17/2019

\#Load in litter Dataset

``` r
##reads in dataset
##Relative Path
litters_data = read_csv(file = "./data_import_examples/FAS_litters.csv")
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
## clean names
litters_data = janitor::clean_names(litters_data)
```

## Read in pups dataset

``` r
## read in next dataset
#relative
pups_data = read_csv(file = "./data_import_examples/FAS_pups.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   `Litter Number` = col_character(),
    ##   Sex = col_double(),
    ##   `PD ears` = col_double(),
    ##   `PD eyes` = col_double(),
    ##   `PD pivot` = col_double(),
    ##   `PD walk` = col_double()
    ## )

``` r
#absolute
pups_data = read_csv(file = "/Users/avahamilton/Dropbox/Biostat MS/Data Science I/DataWrangling1/data_import_examples/FAS_pups.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   `Litter Number` = col_character(),
    ##   Sex = col_double(),
    ##   `PD ears` = col_double(),
    ##   `PD eyes` = col_double(),
    ##   `PD pivot` = col_double(),
    ##   `PD walk` = col_double()
    ## )

``` r
## clean names
pups_data = janitor::clean_names(pups_data)
```

### play with column parsing

``` r
litters_data = read_csv(file = "./data_import_examples//FAS_litters.csv",
  col_types = cols(
    Group = col_character(),
    `Litter Number` = col_character(),
    `GD0 weight` = col_double(),
    `GD18 weight` = col_double(),
    `GD of Birth` = col_integer(),
    `Pups born alive` = col_integer(),
    `Pups dead @ birth` = col_integer(),
    `Pups survive` = col_integer()
  ))
```

\#\#Read in excel file

``` r
#using readxl package

mlb11_data = read_excel(path = "./data_import_examples/mlb11.xlsx",
                        range = "A1:D7")

write_csv(mlb11_data, path = "./data_import_examples/mlb_subset.csv")
```

\#\#Read in
SAS

``` r
pulse_data = haven::read_sas(data_file = "./data_import_examples/public_pulse_data.sas7bdat")
```
