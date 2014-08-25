Organisering af domænelogik
===========================

Tre måder at organisere sin domænelogik:

1. Domænemodel (god til meget komplekse domæner - måske > 60? 70? 80? klasser?)
2. Transkationsskript (god til meget simple domæner - måske < 25 klasser?)
3. Tabelmodul (midt i mellem)

Transaktionsskript: Man koder ikke klasserne fra UML Domænemodellen - de bruges
primært til at definere tabeller i databasen. Domænelogikken består af små
metoder - transaktionsskripter - der ind- og udlæser data efterhånden som de
efterspørges af UI. Der er normalt ikke et Data Source lag.

.. note::

   En interessant konsekvens ved automatisk tildeling af uafhængigt ID: 2. 
   normalform opfyldes automatisk.

Tabelmodul: I C# bruger man DataSet. DataSet'et får en ConnectionString (eller
en xml fil, og andre muligheder). Struktureret tilgang til data, men stadig
ikke union mellem data og adfærd (attributter og metoder). DataSet'et er
nærmest identisk med tabellen. Man giver den også SQL statements til CRUD.
Entity Framework som OR/M er et eksempel på "tabelmodul i den virkelige
verden".

Servicelag
==========

Svarer til et Controller-lag.

.. note::

   Fejl bør håndteres så tæt som muligt på der hvor de opstår. Eks. tager GUI
   sig af at tjekke at numeriske indtastninger rent faktisk er numeriske.
