---
title : "An example to understand time in R"

---

I always forget how to deal with date and time in R. So I decided to document it.

So far smth like this:

```
d <- read.csv("marathon-data.csv", stringsAsFactors = F)

library(lubridate)
d$hms <- format(d$final, format = "%H:%M:%S")
d$hms <- as.POSIXct(d$hms, format = "%H:%M:%S")

library(ggplot2)
ggplot(d, aes(y=hms, x=age, group=age)) + geom_boxplot() + facet_wrap(.~gender)

```
