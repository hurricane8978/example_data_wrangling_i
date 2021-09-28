---
title: "Simple document"
output: html_document
---

```{r, echo =FALSE, message=FALSE}
library(tidyverse)
library(janitor)
library(readxl)
library(haven)
```


##import some data

I want to import"FAS_litters.csv".

```{r}
litters_df = read_csv("data/FAS_litters.csv")
litters_df
```
#read_csv(/Users)

```{r}
names(litters_df)

litters_df = janitor :: clean_names(litters_df)
names(litters_df)

```

Yay! Now I have better names


```{r}
litters_df

head(litters_df)

```

```{r, eval= FALSE}

view(litters_df)

```


Here's "skimr":

```{r}
skimr :: skim(litters_df)
```



##Arguments in "read_csv"

```{r}

litters_df =
  read_csv(
    "data/FAS_litters.csv",
    skip = 5,
    col_names =FALSE,
    na="Low8"
  )
```


```{r}
litters_data = read_csv(file = "./data/FAS_litters.csv",
  col_types = cols(
    Group = col_character(),
    `Litter Number` = col_character(),
    `GD0 weight` = col_double(),
    `GD18 weight` = col_double(),
    `GD of Birth` = col_integer(),
    `Pups born alive` = col_integer(),
    `Pups dead @ birth` = col_integer(),
    `Pups survive` = col_integer()
  )
)
tail(litters_data)



```



## Reading from Excel

```{r}
mlb11_df = read_excel("data/mlb11.xlsx")


```



```{r}
fellow_df =  read_excel("data/LotR_Words.xlsx"",range = "B3:D6s")

```


##Read a SAS file

this is where I tried to read a SAS file but did't work
```{r}
pulse_df = read_sas("data/public_pulse_data.sas7bdat")
```









