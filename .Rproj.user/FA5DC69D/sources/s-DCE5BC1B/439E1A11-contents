## Outline and Code of Demonstration
## Use xaringan
## To-Do:
##   1. Applicable data sets
##   2. Delineate specific principles
##   3. Use R4DS
##   4. Humor at beginning or throughout
##   5. Show potential errors (and the consequences)

library(tidyverse)
library(furniture)

## == Student and Alcohol Consumption == ##

d1 = read.table("data_student_alcohol/student-mat.csv", sep=",", header=TRUE)
d2 = read.table("data_student_alcohol/student-por.csv", sep=",", header=TRUE)

d = inner_join(d1, d2, 
              by=c("school","sex","age","address","famsize",
                   "Pstatus","Medu","Fedu","Mjob","Fjob","reason",
                   "nursery","internet"))
nrow(d) # 382 students


## == Opiate Prescriptions == ##

d1 = read_csv("data_opiate_rx/opioids.csv")
d2 = read_csv("data_opiate_rx/overdoses.csv")
d3 = read_csv("data_opiate_rx/prescriber-info.csv")

d3long = gather(d3, drug, count, 6:256) %>%
  filter(count > 0)
