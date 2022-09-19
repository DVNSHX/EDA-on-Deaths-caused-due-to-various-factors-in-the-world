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
### Create DB
```sql
CREATE TABLE number_of_deaths
(
    country text,
    year_of_study integer,
    meningitis integer,
    alzheimers_and_dementias integer,
    parkinsons integer,
    nutrition_deficiencies integer,
    malaria integer,
    drowning integer,
    interpersonal_violence integer,
    maternal_disorders integer,
    hiv integer,
    drug_use_disorder integer,
    tuberculosis integer,
    cardio integer,
    respiratory_infections integer,
    neonatal_disorders integer,
    alcohol_use_disorder integer,
    selfharm integer,
    forces_of_nature integer,
    diarrheal_diseases integer,
    environmental_heat_cold integer,
    neoplasms integer,
    conflict_and_terrorism integer,
    diabetes integer,
    kidney_diseasesn integer,
    posionings integer,
    proteinenergy_malnutrition integer,
    road_injuries integer,
    chronic_respiratory_disease integer,
    liver_diseases integer,
    digestive_diseases integer,
    fire_and_hot_substances integer,
    acute_hepatitis integer
);
```

## Shape of Data
```sql
select * from number_of_deaths limit 10;
```
```sql




