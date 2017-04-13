---
layout: post
title:  "Ordres Github"
date:   2017-03-30 11:27:40 +0200
categories: jekyll update
tags: [github]
---
**Llista d'ordres útils per Git**

**Per clonar el repositori de GitHub (només una vegada):**
* ``git clone https://github.com/susannalles/MinimalEditions.git``

**Per pujar nous materials a GitHub:**
* ``git init``: s'inicia git a l'intern del directori
* ``git add nom_file.txt``: afegeix el document (o directori) en l'area d'espera ("stage")
* ``git commit -m "el meu primer missatge de canvis"``: descriu els canvis realitzats
* ``git remote add origin https://github.com/brianmengibar/prova2.git``: apunta a l'adreça on vols pujar el nou material
* ``git push -u origin master``: puja els canvis al repositori remote a GitHub per primera vegada

**Push & Pull**
* ``git add``: afegeix el document (o directori) en l'area d'espera ( "stage")
* ``git commit -m "missatge amb els detalls del canvi"``: descriu els canvis realitzats
* ``git push origin master``: pugeu els canvis a GitHub git push origin [branch]: 
pugeu els canvis al repositori remote a GitHub. Assegurar d'escriure el nom del branch que vols pujar els seus canvis

**Sincronitzar la nostra còpia amb l'original:**
* ``git pull``: baixa els canvis del repositori remot a la nostra còpia en local

**La Brúixola:**
* ``git status``: assenyala el que s'ha modificat a la carpeta de treball

**Branches**
* ``git branch``: Per veure en què branch estas treballant.
* ``git branch [name]``: Per crear un branch nou. **Assegurar d'usar git 
checkout per cambiar al branch.**
* ``git checkout [branch]``: Per canviar d'un branch a un altre. 
Així per exemple, si estem en "master" i volem canviar-nos a un branch 
anomenat _"classwork"_, farem **'git checkout classwork'**.
* ``git branch -d [name]``: Per treure un branch. És possible que git et 
dóni un error. **Git no et permet treure un branch que té commits no 
escrits al origin amb aquesta ordre.** Si aquestes completament segur que 
vols treure el branch, pots fer servir l'ordre ``git branch -D [name]``.
* ``git checkout -b nombre_branch``: per baixar el contingut d'un branch
* ``git pull origin nombre_branch``: per actualitzar el contingut d'un branch 
(i començar a treballar en aquest branch).
* ``git checkout -b nombre_branch``: per descarregar el contingut d'un branch
* ``git checkout - file.html``: per ignorar els canvis fets en local 
(quan volem fer un push)
