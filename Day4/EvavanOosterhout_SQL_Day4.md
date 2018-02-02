# SQL database

For this exercise data was downloaded from [study by Wilman et al. (2014)](https://figshare.com/collections/EltonTraits_1_0_Species-level_foraging_attributes_of_the_world_s_birds_and_mammals/3306933/1). A SQLite database was created from the four datasets.
 

Research questions:
1)  What is the difference in body weight for nocturnal and non nocturnal birds?

SQL query:
```
SELECT Nocturnal, ROUND(AVG("Bodymass-Value"),2) AS "Average body mass (g)"
FROM BirdFuncDat
WHERE nocturnal is not null
GROUP BY Nocturnal
```
Answer:

Nocturnal:  269.2 gram

Non nocturnal: 285.27 gram

2)  What is the most referenced book in the mamal dataset?

SQL query:
```
SELECT "Diet-source", "Full reference", COUNT(*) Occurences
FROM MamFuncDat
LEFT JOIN MamFuncDatSources
ON "Diet-Source" = Ref_ID
WHERE Ref_ID IS NOT NULL
GROUP BY "Diet-source", "Full reference"
ORDER BY COUNT(*) DESC
LIMIT 1
```
Answer: 
Nowak R.M. (1999). Walker's mammals of the world. Sixth edition edn. The Johns Hopkins University Press, Baltimore, Maryland

*Code mamal database*

CREATE TABLE "MamFuncDat" ("MSW3_ID" INTEGER, "Scientific" VARCHAR, "MSWFamilyLatin" VARCHAR, "Diet-Inv" INTEGER, "Diet-Vend" INTEGER, "Diet-Vect" INTEGER, "Diet-Vfish" INTEGER, "Diet-Vunk" INTEGER, "Diet-Scav" INTEGER, "Diet-Fruit" INTEGER, "Diet-Nect" INTEGER, "Diet-Seed" INTEGER, "Diet-PlantO" INTEGER, "Diet-Source" VARCHAR, "Diet-Certainty" VARCHAR, "ForStrat-Value" VARCHAR, "ForStrat-Certainty" VARCHAR, "ForStrat-Comment" VARCHAR, "Activity-Nocturnal" INTEGER, "Activity-Crepuscular" INTEGER, "Activity-Diurnal" INTEGER, "Activity-Source" VARCHAR, "Activity-Certainty" VARCHAR, "BodyMass-Value" FLOAT, "BodyMass-Source" VARCHAR, "BodyMass-SpecLevel" INTEGER)

*Code mamal source database*

CREATE TABLE "MamFuncDatSources" ("Ref_ID" VARCHAR, "Full Reference" VARCHAR)

*Code bird database*

CREATE TABLE "BirdFuncDat" ("SpecID" INTEGER, "PassNonPass" VARCHAR, "IOCOrder" VARCHAR, "BLFamilyLatin" VARCHAR, "BLFamilyEnglish" VARCHAR, "BLFamSequID" INTEGER, "Taxo" VARCHAR, "Scientific" VARCHAR, "English" VARCHAR, "Diet-Inv" INTEGER, "Diet-Vend" INTEGER, "Diet-Vect" INTEGER, "Diet-Vfish" INTEGER, "Diet-Vunk" INTEGER, "Diet-Scav" INTEGER, "Diet-Fruit" INTEGER, "Diet-Nect" INTEGER, "Diet-Seed" INTEGER, "Diet-PlantO" INTEGER, "Diet-5Cat" VARCHAR, "Diet-Source" VARCHAR, "Diet-Certainty" VARCHAR, "Diet-EnteredBy" VARCHAR, "ForStrat-watbelowsurf" INTEGER, "ForStrat-wataroundsurf" INTEGER, "ForStrat-ground" INTEGER, "ForStrat-understory" INTEGER, "ForStrat-midhigh" INTEGER, "ForStrat-canopy" INTEGER, "ForStrat-aerial" INTEGER, "PelagicSpecialist" INTEGER, "ForStrat-Source" VARCHAR, "ForStrat-SpecLevel" INTEGER, "ForStrat-EnteredBy" VARCHAR, "Nocturnal" INTEGER, "BodyMass-Value" FLOAT, "BodyMass-Source" VARCHAR, "BodyMass-SpecLevel" INTEGER, "BodyMass-Comment" VARCHAR, "Record-Comment" VARCHAR)
