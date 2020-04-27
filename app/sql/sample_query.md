# sample query used to join on population density


-- will need to join on year and country to return accurate population density data <br>
SELECT <br>

t1.*<br>
,t2.year<br>
,t2.population_density<br>


FROM public.pandemics_combined t1<br>

JOIN public.population t2<br>
    ON t2.year = t1."Year"<br>
    AND t2.country_id = t1."Country_ID"<br>
