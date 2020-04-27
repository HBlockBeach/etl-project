# Query Used to Create Combined View



CREATE VIEW pandemics_combined AS<br>

SELECT <br>

country.country_id AS "Country_ID"<br>
,country.country AS "Country_Name"<br>
,disease.disease_id AS "Disease_ID"<br>
,disease.disease AS "Disease_Name"<br>
,covid19.week AS "Weeks"<br>
,covid19.cases AS "Cases"<br>
,covid19.deaths AS "Deaths"<br>
,covid19.year AS "Year"<br>

FROM public.country<br>

JOIN public.covid19<br>
    ON covid19.country_id = country.country_id<br>
    
JOIN public.disease<br>
    ON covid19.disease_id = disease.disease_id<br>
    
UNION <br>

SELECT <br>

country.country_id <br>
,country.country <br>
,disease.disease_id <br>
,disease.disease <br>
,h1n1.week <br>
,h1n1.cases <br>
,h1n1.deaths<br>
,h1n1.year <br>

FROM public.country<br>

JOIN public.h1n1<br>
    ON h1n1.country_id = country.country_id<br>
    
JOIN public.disease<br>
    ON h1n1.disease_id = disease.disease_id<br>
    
UNION<br>

SELECT <br>

country.country_id <br>
,country.country <br>
,disease.disease_id <br>
,disease.disease <br>
,sars.week <br>
,sars.cases <br>
,sars.deaths <br>
,sars.year <br>

FROM public.country <br>

JOIN public.sars<br>
    ON sars.country_id = country.country_id<br>
    
JOIN public.disease<br>
    ON sars.disease_id = disease.disease_id<br>
