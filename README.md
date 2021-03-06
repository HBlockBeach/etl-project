# <div align="center">**Pandæmonium**<div> 

## Team:
* [Kafui Ahedor](https://github.com/kafui001)
* [Sean Atkins](https://github.com/SMAtkins)
* [Hunter Block-Beach](https://github.com/HBlockBeach)
* [Ryan Klueg](https://github.com/coconutpep)




## Project Background:
<div align="center"> From smallpox to typhoid, epidemics have plagued humans for all of history. In more recent history we have been hit by SARS-CoV (SARS, 2002), A/H1N1 (swine flu/spanish flu, 2009), and SARS-CoV2 (COVID19/coronavirus, 2019). While preventing these types of events is impossible, having a better understanding of the transmission and death rates, as well as observing how the viruses change overtime, may be key to understanding and ultimately preparing for large scale epidemics. </div><br>

<div align="center">Our objective is to collect data related to SARS, H1N1, and COVID19 in order to analyze infection rates in specific countries as well as compare the transmission and death rates among the diseases. </div>

#### <div align="center"> More infomation about the team and project can be accessed through the link below<br> https://hblockbeach.github.io/etl-project/</div>


## Relevant Files:

#### Raw Data:
* [/app/resources/](app/resources)
1. COVID19: covid_19_clean_complete.csv
2. H1N1: h1n1.csv
3. SARS: sars.csv
4. Population Density: popdensity.csv

#### Cleaned Data:
* [/app/data/](app/data)
1. COVID19: cleancovids.csv
2. H1N1: h1n1_clean.csv
3. SARS: sars_clean.csv
4. Population Density: populationDensity.csv

#### Jupyter Notebooks:
* [/app/](app)
1. COVID19 Clean.ipynb
2. H1N1: h1n1_clean.ipynb
3. SARS: sars_clean.ipynb
4. Population Density: popden.ipynb
5. Data Manipultion for PostGres: Tables.ipynb

#### Manipulated Data for PostGres:
* [/app/data/postgres_files](app/data/postgres_files)
1. COVID19: covid_final.csv
2. H1N1: h1n1_final.csv
3. SARS: sars_final.csv
4. Population Density: pop_density_table.csv
5. Country Table: country_table.csv

#### ERD:
* [/app/data/ERD](app/data/erd_final.jpg)
![ERD](app/data/erd_final.jpg "ERD")

#### SQL:
* [/app/sql](app/sql)
1. Schema: schema.md
2. View: view_sql.md
3. Sample Query: sample_query.md

#### GitHub Pages Data:
* [/docs/](docs)
1. Main Page HTML: index.html
2. Team Page HTML: team.html
* [/docs/assets](docs/assets)
1. Main Page CSS: style.css
2. Team Page CSS: team.css
