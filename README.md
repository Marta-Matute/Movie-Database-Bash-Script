(Catalan follows)
# Movie Menu Selection using Bash

## Goal
This project is designed to display a menu that offers the user a series of criteria found in a `.csv` file. 
The file is comprised of a series of titles, as well as other characteristics, such as a movie description or its rating.

## How to use (in a Linux Machine)
There are a total of 4 scripts written in Bash (`.sh` extension). In a linux machine, it is not necessary to have any extra libraries or dependencies installed.
To start the program, run the file `main.sh`. Here's an example of what the instruction looks like, and what you should get on the terminal: 
```bash
$ bash main.sh
---------------- Menu ----------------
	1. Recomenació ràpida
	2. Llistar per any
	3. Llistar per rating
	4. Criteris de cerca
	5. Sortir
--------------------------------------
Introdueixi una opció: 5
$
```

## File's explanation
**arreglar_dades.sh:** This script modifies the file `netflix.csv` so that the quotes found in some titles are removed, it adds a 0 on the field `user_rating_score` if that value is null, and it also sorts the titles according to the later, as well as removing duplicates. 

**main.sh:** Before anything, the files `anys.txt` (years in catalan), `ratings.txt` and `estrelles.txt` (stars in catalan) will be created, so that we don't get an error when manipulating this files in the case that the user hasn't previously pressed the option that would automatically create them. Right after, the script `arreglar_dades.sh` and `menu.sh` will be called. And finally, the user input for the menu option will be read. 

**opcio1.sh:** The first option filters the movie database according the user defined preferences, if any. If no preferences had been set, then this option will return a movie at random.

**opcio2.sh:** The second option reads a year inputed by the user, and it looks for the all the titles whose production year matches the search. This movie titles are then showed on screen. 

**opcio3.sh:** The third option asks the user for a number of stars (between 1 and 5) by which they want to filter the rating. Then it's showed on screen all the titles that have the introduces rating or higher. The format will also show the number of stars each movie has. 

**opcio4.sh:** Option four will show yet another menu where the search preferences can be changed. This menu has the following options: 

~~~
--------------------------------------
            Criteris de Cerca
--------------------------------------
a. Modificar Preferencies
b. Eliminar Preferencies
c. Preferencies actuals
d. Sortir
 --------------------------------------
~~~

Option **a** (modify preferences) will show sequencially all the criteria that be changed. First it will show all the available years (which calls the script `llistat_anys_disponibles.sh`, and it will show an example of how to introduce the years for the search filter. Lastly it will also ask for the number of stars in the search criteria. 

Option **b** will reset all of the preferences, including year, rating or number or stars.

Option **c** will show whatever the currently saved preferences are. 

Option **d** will go back to the main menu. 

**llistat_anys_disponibles.txt:** This script will save in a text file all the years that appear in at least one movie in the file `netflix.csv`.



# PRÀCTICA 2 - PROGRAMARI DEL SISTEMA

## Objectiu:

La finalitat d'aquest projecte és la d'oferir a l'usuari una sèrie de criteris de recerca dins
un fitxer d'extensió .csv.
Aquest fitxer està format per una llista de títols, acompanyats d'altres característiques, com ara la descripció o el rating.


## Mode d'execució:

El programa consta de 4 scripts en llenguatge Bash. No és necessària la instal.lació de cap software extern. Per a començar el programa s'haurà d'executar l'script "main.sh". Exemple:

```bash
$ bash main.sh
---------------- Menu ----------------
	1. Recomenació ràpida
	2. Llistar per any
	3. Llistar per rating
	4. Criteris de cerca
	5. Sortir
--------------------------------------
Introdueixi una opció: 5
$
```

## Explicació dels programes:
**arreglar_dades.sh:** Aquest script modifica l'arxiu netflix.csv de manera que elimina les cometes que hi ha en alguns dels títols, afegeix 0 al camp *user_rating_score*  si és but, els endreça de més gran a més petit segons aquest mateix camp, i elimina duplicats.

**main.sh:** Abans de res, es crearàn els arxius "anys.txt", "ratings.txt" i "estrelles.txt" per a que no es produeixin errors quan els volguem manipular en cas que l'usuari no hagi executat l'opció *Criteris de cerca* abans d'executar *Recomenació ràpida*.  Tot seguit es cridarà a l'script "arreglar_dades.sh", i per últim crida a l'script "menu.sh" i llegeix la opció introduida per pantalla. Per a cadascuna d'elles, cridarà al programa corresponent. 

**opcio1.sh:** Per a la opció 1, el programa filtra l'arxiu netflix.csv segons les preferències que l'usuari hagi introduit amb anterioritat. Si no s'ha introduit cap preferència, la opció 1 retornarà qualsevol títol de l'arxiu.

**opcio2.sh:** Per a la opció 2, es llegeix un any introduit per l'usuari, i es fa una cerca dins el document per a trobar tots els títols que coincideixin amb l'any de producció. Aquests títols es mostren per pantalla.

**opcio3.sh:** Per a l'opció 3 es demana a l'usuari que introdueixi un nombre d'estrelles per les que vol filtrar (un nombre de l'1 al 5). Seguidament s'imprimeix per pantalla un llistat dels títols que tinguin un "user rating score" igual o més gran que el que l'usuari ha introduit per pantalla. El format serà el nombre d'estrelles que té la película, el títol i l'any.
**opcio4.sh:** Per a l'opcio 4 es tornarà a mostrar un altre menú, referent als criteris de cerca. Les opcions seràn:
~~~
--------------------------------------
            Criteris de Cerca
--------------------------------------
a. Modificar Preferencies
b. Eliminar Preferencies
c. Preferencies actuals
d. Sortir
 --------------------------------------
~~~
Per a la opció **a** es mostraràn sequencialment tots els criteris que es poden canviar. Primer es mostraràn tots els anys disponibles (per a fer-ho cridarem a l'script "llistat_anys_disponibles.sh") i es mostrarà un exemple de com introduir els anys. Segon s'ensenyaran tots els ratings possibles i també es mostrarà un exemple. Finalment es demanarà el nombre d'estrelles.
Per a la opció **b** es resetejaràn totes les preferències de manera que no hi haurà cap any, rating o nombre d'estrelles preferent. 
Per a la opció **c** s'ensenyaran les preferències que hi hagi guardades.
La opció **d** simplement tornarà al menú principal.
Aquest menú també accepta les entrades de les opcions en majuscula. Qualsevol altre opció introduida tornarà un missatge d'error i tornarà a mostrar el menú.
Al menú principal, si no s'introdueix un número de l'1 al 4 es mostra un missatge d'error i transcorren 3 segons fins que es
torna a mostrar el menú.

**llistat_anys_disponibles.txt:** Aquest script guardarà en un arxiu tots els anys que apareguin al cinquè camp de l'arxiu netflix.csv i els imprimirà en files de 6 columnes dins un requadre amb el títol *POSSIBLES ANYS*.
