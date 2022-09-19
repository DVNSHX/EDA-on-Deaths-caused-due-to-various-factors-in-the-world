# EDA-on-deaths-caused-due-to-various-factors-in-the-world
exploratory data analysis on deaths caused due to various factors in the world from 1990 to 2019

#### Table of Contents
  * [Setup DB](#setup-db)
  * [Viewing date](#viewing-data)
  * [Queries](#queries)

*The data was collected from https://ourworldindata.org/causes-of-death*

## Setup DB
*The data has been pre-cleaned in excel for missing values; omission of columns with missing value is strategy employed as the causes were not that relevant to the EDA. Furthermore, clumped regions were removed and only individual countries were left in the csv*
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

## Viewing Data
```sql
select * from number_of_deaths limit 10;
```
```
country              | year_of_study | meningitis | alzheimers_and_dementias | parkinsons | nutrition_deficiencies | malaria | drowning | interpersonal_violence | maternal_disorders | hiv | drug_use_disorder | tuberculosis | cardio | respiratory_infections | neonatal_disorders | alcohol_use_disorder | selfharm | forces_of_nature | diarrheal_diseases | environmental_heat_cold | neoplasms | conflict_and_terrorism | diabetes | kidney_diseasesn | posionings | proteinenergy_malnutrition | road_injuries | chronic_respiratory_disease | liver_diseases | digestive_diseases | fire_and_hot_substances | acute_hepatitis
---------------------+---------------+------------+--------------------------+------------+------------------------+---------+----------+------------------------+--------------------+-----+-------------------+--------------+--------+------------------------+--------------------+----------------------+----------+------------------+--------------------+-------------------------+-----------+------------------------+----------+------------------+------------+----------------------------+---------------+-----------------------------+----------------+--------------------+-------------------------+-----------------
 Afghanistan         |          1990 |       2159 |                     1116 |        371 |                   2087 |      93 |     1370 |                   1538 |               2655 |  34 |                93 |         4661 |  44899 |                  23741 |              15612 |                   72 |      696 |                0 |               4235 |                     175 |     11580 |                   1490 |     2108 |             3709 |        338 |                       2054 |          4154 |                        5945 |           2673 |               5005 |                     323 |            2985
 Albania             |          1990 |        107 |                      360 |         93 |                     37 |       0 |      147 |                    177 |                 26 |   1 |                 5 |           46 |   6701 |                   2140 |                871 |                   10 |      125 |                0 |                 76 |                       5 |      2616 |                      0 |      100 |              241 |         13 |                         35 |           395 |                        1006 |            326 |                648 |                      31 |               4
 Algeria             |          1990 |        839 |                     1337 |        439 |                    453 |       9 |     1207 |                    491 |               1634 |  44 |               171 |          939 |  53488 |                   8125 |              17931 |                   75 |     1405 |                0 |               2908 |                      35 |     10571 |                      4 |     1743 |             3559 |        485 |                        422 |         13438 |                        4410 |           2401 |               3981 |                    1113 |             486
 American Samoa      |          1990 |          1 |                        3 |          1 |                      2 |       0 |        4 |                      3 |                  1 |   0 |                 0 |            1 |     66 |                     10 |                 12 |                    0 |        3 |                0 |                  3 |                       1 |        31 |                      0 |       16 |                8 |          0 |                          2 |             5 |                          17 |              5 |                  9 |                       0 |               0
 Andorra             |          1990 |          0 |                        6 |          2 |                      0 |       0 |        0 |                      1 |                  0 |   1 |                 0 |            0 |     65 |                      6 |                  1 |                    1 |        6 |                0 |                  0 |                       0 |       101 |                      0 |        4 |                4 |          0 |                          0 |             8 |                          16 |              6 |                 10 |                       0 |               1
 Angola              |          1990 |       3407 |                      293 |         86 |                  12232 |    5544 |     1093 |                    458 |               1662 | 239 |                19 |        14896 |  11871 |                  19616 |              14210 |                   98 |      973 |                0 |              35849 |                     102 |      4883 |                   2756 |     1519 |             1059 |        389 |                      11942 |          5062 |                        2794 |           2782 |               4481 |                     431 |             645
 Antigua and Barbuda |          1990 |          2 |                       12 |          3 |                      4 |       0 |        4 |                      2 |                  0 |   7 |                 0 |            1 |    170 |                     22 |                 10 |                    3 |        1 |                0 |                  3 |                       0 |        75 |                      0 |       34 |               15 |          1 |                          3 |             6 |                           7 |              9 |                 17 |                       2 |               0
 Argentina           |          1990 |        772 |                     4983 |       1494 |                   1323 |       9 |     1128 |                   2024 |                448 | 559 |                22 |         1641 |  98783 |                   8684 |               9407 |                  949 |     2758 |               21 |               1073 |                      29 |     56399 |                    162 |     7096 |             7129 |        308 |                       1277 |          4361 |                        9894 |           5943 |              12139 |                     627 |             107
 Armenia             |          1990 |         24 |                      359 |         76 |                     57 |       0 |      320 |                    179 |                 31 |   1 |                 5 |          109 |  10672 |                   1147 |               1155 |                   88 |      105 |                0 |                385 |                     183 |      4136 |                     25 |      495 |               68 |         83 |                         23 |           551 |                        1078 |            406 |                802 |                     230 |               8
 Australia           |          1990 |         99 |                     3669 |        880 |                     77 |       0 |      295 |                    380 |                 19 | 379 |               458 |           99 |  51230 |                   1823 |                872 |                  270 |     2342 |               16 |                 38 |                      40 |     31401 |                      2 |     2198 |             1712 |         47 |                         47 |          2739 |                        6966 |           1394 |               3944 |                     147 |               6
 ```

## Queries
### Extract Data for Deaths caused by Parkinsons Disease
```sql
select country, year_of_study, parkinsons from number_of_deaths limit 10;
```
```
country             | year_of_study | parkinsons
---------------------+---------------+------------
 Afghanistan         |          1990 |        371
 Albania             |          1990 |         93
 Algeria             |          1990 |        439
 American Samoa      |          1990 |          1
 Andorra             |          1990 |          2
 Angola              |          1990 |         86
 Antigua and Barbuda |          1990 |          3
 Argentina           |          1990 |       1494
 Armenia             |          1990 |         76
 Australia           |          1990 |        880
 ```
 ## Visualise total deaths caused due to parkinsons disease from 1990 to 2019
 ![image](https://user-images.githubusercontent.com/45635012/190979564-1d40ca32-f4ff-49f6-8eb8-490e0a2b8def.png)
*Insight: Parkinsons disease has been globally increasing, we can further check the countries where parkinsons has decreases and diagnose how they have controlled it to share the interventions with other countries*

### Top 10 distinct countries with most deaths in a year caused due to Malaria
```sql
select
distinct country,
MAX(malaria) as malaria_max
from number_of_deaths
group by country
order by malaria_max desc
limit 10;
```
```
           country            | malaria_max
------------------------------+-------------
 Nigeria                      |      280604
 India                        |      162369
 Democratic Republic of Congo |      102544
 Uganda                       |       57993
 Cote d'Ivoire                |       42573
 Burkina Faso                 |       41921
 Tanzania                     |       39868
 Ethiopia                     |       39036
 Bangladesh                   |       38637
 Niger                        |       36155
 ```
 ## Visualise top 10 countries with the most number of deaths due to Malaria in a year
 ![image](https://user-images.githubusercontent.com/45635012/190988081-cc0d907a-a6f0-4c84-88d3-70b081511261.png)
 
 ## Analysis of deaths caused by AIDS in the world for year 2019
 ```sql
 select country,hiv
from number_of_deaths
where year_of_study = 2019
order by hiv desc;
```
```sql
             country              |  hiv
----------------------------------+--------
 South Africa                     | 143851
 Nigeria                          |  82270
 Mozambique                       |  66304
 Kenya                            |  51135
 India                            |  46298
 China                            |  31746
 Tanzania                         |  27125
 Ethiopia                         |  26591
 Cameroon                         |  23172
 Zambia                           |  22540
 Uganda                           |  20762
 Zimbabwe                         |  20722
 Russia                           |  18682
 Thailand                         |  17215
 Angola                           |  16802
 Brazil                           |  15561
 Ghana                            |  14621
 Malawi                           |  14227
 Cote d'Ivoire                    |  13638
 Lesotho                          |  10793
 Democratic Republic of Congo     |  10238
 United States                    |   7053
 Ukraine                          |   6643
 Vietnam                          |   6399
 Haiti                            |   5908
 Botswana                         |   5612
 Indonesia                        |   5603
-- More  --
```
## Visualize a world map with deaths caused by AIDS as a heatmap 
![image](https://user-images.githubusercontent.com/45635012/190989766-a2c24330-fe74-4979-bd54-a7071de899dd.png)


