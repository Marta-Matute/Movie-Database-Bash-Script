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
- Per a qualsevol altre entrada, es mostra un missatge d'error i transcorren 3 segons fins que es
torna a mostrar el menú.

**llistat_anys_disponibles.txt:** Aquest script guardarà en un arxiu tots els anys que apareguin al cinquè camp de l'arxiu netflix.csv i els imprimirà en files de 6 columnes dins un requadre amb el títol *POSSIBLES ANYS*.
