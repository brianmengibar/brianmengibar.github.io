---
layout: post
title:  "Informacio Adicional Sobre Liquid"
date:   2016-12-30 11:27:40 +0200
categories: jekyll update
tags: [liquid,Jekyll]
---

![liquid](/public/liquid.png)

**Que es Liquid?**

``Liquid`` és un **llenguatge de plantilles segur desenvolupat per Shopify.** ``Liquid`` està dissenyat
per als usuaris finals per poder executar la lògica dins dels fitxers de plantilla sense imposar
cap risc per a la seguretat al servidor d'allotjament.

``Jekyll`` utilitza ``liquid`` per **generar el contingut de l'entrada dins de l'estructura de disseny de 
pàgina final** i com a interfície principal per treballar amb el seu lloc i dades post/pàgina.

A continuació os mostro les variables que podeu trobar en jekyll gracies al sistema ``liquid``:

**Variables Globals**

* ``site``
Informació del lloc + Arxiu de configuració ``_config.yml.``

* ``page``
Informació de la pagina + ``YAML``

* ``layout``
Informació del disseny + ``YAML``

* ``content``
Contingut renderitzat de les pagines del disseny

* ``paginator``
Variable que s'utilitza quan es configura la paginació

**Variables del lloc web**

* ``site.item``
Hora actual (**quan s'executa l'ordre ``jekyll``**)

* ``site.pages``
Llistat de totes les pagines

* ``site.posts``
Llista cronologica inversa de tots els posts

* ``site.related_posts``
Llistat dels ultims 10 posts pero ordre cronologic invers
