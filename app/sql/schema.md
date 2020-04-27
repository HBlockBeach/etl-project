# Use this code to create schema in postgres

CREATE TABLE sars (<br>
    "week" INT   NOT NULL,<br>
    "cases" FLOAT   NOT NULL,<br>
    "deaths" FLOAT   NOT NULL,<br>
    "country_id" INT   NOT NULL,<br>
    "year" BIGINT   NOT NULL,<br>
    "disease_id" INT   NOT NULL<br>
);

CREATE TABLE covid19 (<br>
    "week" INT   NOT NULL,<br>
    "cases" FLOAT   NOT NULL,<br>
    "deaths" FLOAT   NOT NULL,<br>
    "country_id" INT   NOT NULL,<br>
    "year" BIGINT   NOT NULL,<br>
    "disease_id" INT   NOT NULL<br>
);

CREATE TABLE h1n1 (<br>
    "week" INT   NOT NULL,<br>
    "cases" FLOAT   NOT NULL,<br>
    "deaths" FLOAT   NOT NULL,<br>
    "country_id" INT   NOT NULL,<br>
    "year" BIGINT   NOT NULL,<br>
    "disease_id" INT   NOT NULL<br>
);

CREATE TABLE population (<br>
    "country_id" INT   NOT NULL,<br>
    "population_density" FLOAT   NOT NULL,<br>
    "year" BIGINT   NOT NULL<br>
);

CREATE TABLE country (<br>
    "country_id" INT   NOT NULL,<br>
    "country" VARCHAR(100)   NOT NULL,<br>
    CONSTRAINT "pk_country" PRIMARY KEY (<br>
        "country_id"<br>
     )
);

CREATE TABLE disease (<br>
    "disease_id" INT   NOT NULL,<br>
    "disease" VARCHAR(100)   NOT NULL,<br>
    CONSTRAINT "pk_disease" PRIMARY KEY (<br>
        "disease_id"<br>
     )
);

ALTER TABLE sars <br>ADD CONSTRAINT "fk_sars_country_id" <br>FOREIGN KEY("country_id")<br>
REFERENCES country ("country_id");

ALTER TABLE sars <br>ADD CONSTRAINT "fk_sars_disease_id"<br> FOREIGN KEY("disease_id")<br>
REFERENCES disease ("disease_id");

ALTER TABLE covid19 <br>ADD CONSTRAINT "fk_covid19_country_id" <br>FOREIGN KEY("country_id")<br>
REFERENCES country ("country_id");

ALTER TABLE covid19<br> ADD CONSTRAINT "fk_covid19_disease_id" <br>FOREIGN KEY("disease_id")<br>
REFERENCES disease ("disease_id");

ALTER TABLE h1n1 <br>ADD CONSTRAINT "fk_h1n1_country_id" <br>FOREIGN KEY("country_id")<br>
REFERENCES country ("country_id");

ALTER TABLE h1n1 <br>ADD CONSTRAINT "fk_h1n1_disease_id" <br>FOREIGN KEY("disease_id")<br>
REFERENCES disease ("disease_id");

ALTER TABLE population<br> ADD CONSTRAINT "fk_population_country_id" <br>FOREIGN KEY("country_id")<br>
REFERENCES country ("country_id");




