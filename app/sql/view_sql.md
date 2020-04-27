# Query Used to Create Combined View



CREATE VIEW pandemics_combined AS

SELECT 

country.country_id AS "Country_ID"
,country.country AS "Country_Name"
,disease.disease_id AS "Disease_ID"
,disease.disease AS "Disease_Name"
,covid19.week AS "Weeks"
,covid19.cases AS "Cases"
,covid19.deaths AS "Deaths"
,covid19.year AS "Year"

FROM public.country

JOIN public.covid19
    ON covid19.country_id = country.country_id
    
JOIN public.disease
    ON covid19.disease_id = disease.disease_id
    
UNION 

SELECT 

country.country_id 
,country.country 
,disease.disease_id 
,disease.disease 
,h1n1.week 
,h1n1.cases 
,h1n1.deaths
,h1n1.year 

FROM public.country

JOIN public.h1n1
    ON h1n1.country_id = country.country_id
    
JOIN public.disease
    ON h1n1.disease_id = disease.disease_id
    
UNION

SELECT 

country.country_id 
,country.country 
,disease.disease_id 
,disease.disease 
,sars.week 
,sars.cases 
,sars.deaths 
,sars.year 

FROM public.country

JOIN public.sars
    ON sars.country_id = country.country_id
    
JOIN public.disease
    ON sars.disease_id = disease.disease_id
