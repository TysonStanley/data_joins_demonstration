## Create Multi-Table Office-Parks Data Set
## Tyson S. Barrett
## Based on `key_diagram.jpg`

load("data_officeparks/OfficeParks.RData")

df = df %>%
  mutate(age = c(4, 2, 2, 3, 
                 5, 5, 5, 4, 
                 3, 3, 3, 2,
                 2, 3, 3, 3,
                 1, 2, 3, 4,
                 2, 3, 3, 4, 
                 5, 1, 1, 3, 
                 4, 5, 3, 2,
                 4, 5, 5, 5,
                 4, 5))

## ------ ##
## Tables ##
## ------ ##

## Demographics
demo = df %>%
  select(nam, show, phys, marr, gend, race, age, inco)

## Measurement Occasion Info
occasion = tribble(~show, ~time, ~date,
                   "Office", 1, "2007-04-01",
                   "Office", 2, "2011-04-01",
                   "Parks",  1, "2010-04-01",
                   "Parks",  2, "2014-09-01") %>%
  mutate(date = lubridate::date(date))

## Individual Health Measures
health = df %>%
  select(prod1, prod2, depr1, depr2, awkw1, awkw2, ment1, ment2, nam, show) %>%
  furniture::long(c("prod1", "prod2"),
                  c("depr1", "depr2"),
                  c("awkw1", "awkw2"),
                  c("ment1", "ment2"),
                  id = c("nam", "show"),
                  v.names = c("prod", "depr", "awkw", "ment"))

## Show Info
show = df %>%
  select(show, start_date, last_aired) %>%
  dplyr::distinct()

## Measurement Info
depr_info = tribble(~depr, ~info,
                    1,     "no depression",
                    2,     "no depression",
                    3,     "no depression",
                    4,     "no depression",
                    5,     "no depression",
                    6,     "no depression",
                    7,     "no depression",
                    8,     "no depression",
                    9,     "no depression",
                    10,    "no depression",
                    11,    "no depression",
                    12,    "no depression",
                    13,    "depression",
                    14,    "depression",
                    15,    "depression",
                    16,    "depression",
                    17,    "depression",
                    18,    "depression",
                    19,    "depression",
                    20,    "depression")

save(demo, occasion, health, show, depr_info,
     file = "data_officeparks/OfficeParks_Tables.rda")

## age:
##    1 = < 20
##    2 = 21 - 30
##    3 = 31 - 40
##    4 = 41 - 50
##    5 = 51 +

