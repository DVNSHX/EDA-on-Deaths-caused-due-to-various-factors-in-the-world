# EDA-on-deaths-caused-due-to-various-factors-in-the-world
exploratory data analysis on deaths caused due to various factors in the world from 1990 to 2019

#### Table of Contents
  * [Setup DB](#setup-db)
  * [Shape of Data](#shape-of-data)
  * [Viewing date](#viewing-data)
  * [Distinct values](#distinct-values)
  * [Order by](#order-by)
  * [Case](#case)
  * [Data Aggregation](#data-aggregation)
  * [Pattern Match](#pattern-match)
  * [Group By](#group-by)
  * [Window Functions](#window-functions)
  * [Join](#join)

*The data was collected from https://ourworldindata.org/causes-of-death*

## Setup DB
```sql
copy number_of_deaths from 'file_path' delimiter ',' csv header;
```
