.. highlight:: csharp

Sockets
=======

Test 1 og 2
-----------

.. todo::

   Find ud af hvordan tingene skal være organiseret!

   Husk at du bare kan ignorere mappen src hvis du vil have din egen kode i
   Sphinx-mappen, men stadig gerne vil føre seperat version control.

   Hvad gør jeg med udleveret materiale som er under copyright? git ignore
   igen, ligner det. Hvad sker der i Sphinx hvis man linker til fil som ikke
   findes? Linkchecker...

.. todo::

   Det skal være muligt at linke til en mappe, på samme måde som :download:
   linker til en enkelt fil - hele mappen kopieres!

Jeg har lært noget med deep copy af lister i dag - se Test2.

I den udgave af Test2 som jeg afleverede, lavede jeg en fejl ved kopiering af
lister. Jeg ville lave en kopi, da jeg skulle bruge en liste som jeg godt måtte
slette elementer fra. Men i stedet for at lave en kopi, kopierede jeg blot
referencen! Dum fejl.

Efter lidt googling fandt jeg ud af, at kopiering af en liste ikke er ligetil -
der er ikke nogen liste.deepcopy() metode. Men hvis det er en liste af value
types så kan man kopiere således::

   // original is type List<double>
   List<double> copy = new List<double>(original);


Sockets
-------

Man kan lægge StreamReader og StreamWriter ovenpå en binær stream
(NetworkStream) når man laver sockets i C# - brug Flush når man skal sende før
buffer er fuld (eller sæt AutoFlush på writeren - så sender den på hver write).

Det er godt design at have en Handler klasse (ligesom Python har det), det gør
det også meget nemmere at bruge tråde.
