# ***Extract*** 
### Data Sources
#### Kaggle: 
1. COVID-19, csv
2. H1N1, csv
3. SARS, csv

#### The World Bank:
1. Population Density 2003, csv
2. Population Density 2009, csv

#### Worldometer:
1. Population Density 2020, web scrape 


# ***TRANSFORM***
### Cleaning:
#### Disease Data:
The raw disease data contained information about key statistics (cases, deaths, recoveries) for the affected countries on a day by day basis. Several enhanbements were needed to make the data usable for analysis. 

1. Stray characters were removed from the dataset 
2. Country names were standardized across datasets
3. Data was grouped by week since disease onset to normalize the datasets to one another allowing the analyst to compare apples to apples 

#### Population Density Data:
The raw population density data contains a wide range of data including country codes, land, area, and year over year changes. Many of these columns were unecessary and there were many extra countries. 

1. Extraneous columns were removed
2. Countries not in the data were removed

### Transfomation:
#### Disease Data:
The disease data needed to be denormalized. 

1. County_id added and country column dropped 
2. Year of data added for join on population density
3. Disease_id added for joins/disease identification in joined datasets

#### Population Density:
The population density data contained data in one row. In order to be used, it needed to be transformed into a new configuration 

1. Data was manipulated to change the structure:
* Original Structure **fake data**: <br>
Country,             2003,                2009,                2020<br>
US,                     10,                    20,                    30<br>

* Updated Structure **fake data**:<br>
Country,           Year ,                 Density  <br>
US,                   2003,                   10 <br>
US,                   2009,                   20<br>
US,                   2020,                   30<br>


#### Table Creation:
Two key tables were created.
1. Country, each unique country in the datasets was assigned a unique id
2. Disease, each unique disease in the datasets was assigned a unique id


# ***LOAD***
### Tables:
* Country
* Disease
* Population
* covid19
* h1n1
* sars

ERD can be viewed [here](https://github.com/HBlockBeach/etl-project/blob/master/app/data/erd.JPG)

PGadmin
relational
why?
