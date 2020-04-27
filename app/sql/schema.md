# Use this code to create schema in postgres

CREATE TABLE sars (
    "week" INT   NOT NULL,
    "cases" FLOAT   NOT NULL,
    "deaths" FLOAT   NOT NULL,
    "country_id" INT   NOT NULL,
    "year" BIGINT   NOT NULL,
    "disease_id" INT   NOT NULL
);

CREATE TABLE covid19 (
    "week" INT   NOT NULL,
    "cases" FLOAT   NOT NULL,
    "deaths" FLOAT   NOT NULL,
    "country_id" INT   NOT NULL,
    "year" BIGINT   NOT NULL,
    "disease_id" INT   NOT NULL
);

CREATE TABLE h1n1 (
    "week" INT   NOT NULL,
    "cases" FLOAT   NOT NULL,
    "deaths" FLOAT   NOT NULL,
    "country_id" INT   NOT NULL,
    "year" BIGINT   NOT NULL,
    "disease_id" INT   NOT NULL
);

CREATE TABLE population (
    "country_id" INT   NOT NULL,
    "population_density" FLOAT   NOT NULL,
    "year" BIGINT   NOT NULL
);

CREATE TABLE country (
    "country_id" INT   NOT NULL,
    "country" VARCHAR(100)   NOT NULL,
    CONSTRAINT "pk_country" PRIMARY KEY (
        "country_id"
     )
);

CREATE TABLE disease (
    "disease_id" INT   NOT NULL,
    "disease" VARCHAR(100)   NOT NULL,
    CONSTRAINT "pk_disease" PRIMARY KEY (
        "disease_id"
     )
);

ALTER TABLE sars ADD CONSTRAINT "fk_sars_country_id" FOREIGN KEY("country_id")
REFERENCES country ("country_id");

ALTER TABLE sars ADD CONSTRAINT "fk_sars_disease_id" FOREIGN KEY("disease_id")
REFERENCES disease ("disease_id");

ALTER TABLE covid19 ADD CONSTRAINT "fk_covid19_country_id" FOREIGN KEY("country_id")
REFERENCES country ("country_id");

ALTER TABLE covid19 ADD CONSTRAINT "fk_covid19_disease_id" FOREIGN KEY("disease_id")
REFERENCES disease ("disease_id");

ALTER TABLE h1n1 ADD CONSTRAINT "fk_h1n1_country_id" FOREIGN KEY("country_id")
REFERENCES country ("country_id");

ALTER TABLE h1n1 ADD CONSTRAINT "fk_h1n1_disease_id" FOREIGN KEY("disease_id")
REFERENCES disease ("disease_id");

ALTER TABLE population ADD CONSTRAINT "fk_population_country_id" FOREIGN KEY("country_id")
REFERENCES country ("country_id");




