
<!-- README.md is generated from README.Rmd. Please edit that file -->

## SARB Quarterly Bulletin Data

*\<last updated on 2020-04-27\>*

This R package provides convenient access to the data that accompanies
the South African Reserve Bank Quarterly Bulletin. Variables that are of
the same frequency have been converted to `tibble` format and have been
saved as `.RData` files. The names for each of these files is as
follows:

  - **sarb\_annual.RData**
  - **sarb\_quarter.RData**
  - **sarb\_month.RData**
  - **sarb\_week.RData**
  - **sarb\_day.RData**

The column headers relate to each of the alpha-numeric codes that are
used by the SARB. The first column is reserved for the date. The
`lubridate` package was used for the date field where the first day of
the year, quarter or month is used. In addition, the first Monday of the
week is used from weekly data. The weekly data may include a few zeros
that may have arisen on public holidays.

The most recent description file that is provided by the SARB has been
saved is also included and an additional `.xlsx` version is included in
the **desc** sub-folder. The layout is consistent with the way in which
this data is provided.

## Installation

To install the repository the current data from GitLab:

``` r
# install.packages("devtools")
devtools::install_gitlab("KevinKotze/sarbcurrent")
```

To install the repository the current data from GitHub:

``` r
# install.packages("devtools")
devtools::install_github("KevinKotze/sarbcurrent")
```

## Usage

To view all of the data objects that are included in the package:

``` r
library(sarbcurrent)
data(package = 'sarbcurrent')
```

``` r
library(tidyverse)
sarb_quarter %>% 
  select(date, KBP6006D) %>% 
  tail()
```

## Historic real-time data vintages

Historic real-time data vintages, as described in the article by Dean
Croushore and Tom Stark (2001), “A Real-Time Data Set for
Macroeconomists”, *Journal of Econometrics*, vol 105, pp. 111-30, may be
accessed in a similar manner. For example, to access the dataset that
was released in 2012q2, you should install the following package.

``` r
devtools::install_gitlab("KevinKotze/sarb2012q2")
```

or

``` r
devtools::install_github("KevinKotze/sarb2012q2")
```

See
<https://www.philadelphiafed.org/research-and-data/real-time-center/real-time-data/>
for additional details on the real time dataset that is provided for the
United States economy.

## Disclaimer

Please note that this is not an official release of data and I’m in no
way responsible for the results that may be produced using these data
files. Researchers are encouraged to make use of the official data
release that is available from the South African Reserve Bank.
