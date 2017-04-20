---
layout: post
title:  "Informacio adicional Jekyll"
date:   2017-03-28 11:27:40 +0200
categories: jekyll update
tags: [rubygems,Jekyll,liquid,github]
---

![jekyll](/public/jekyll.png)

**Que es Jekyll?**

Jekyll és un motor d'anàlisi integrat utilitzat per construir llocs web estàtics a partir 
de components dinàmics com plantilles, codi de ``liquid``, etc. ``Jekyll`` es coneix com 
_"un simple bloc generador de llocs estàtics"_.

**Que fa Jekyll?**

Jekyll s'instal·la localment amb gemes. Un cop instal·lat, podem executar Jekyll dins del terminal en un directori
i sempre que el directori estigui configurat de la manera que Jekyll espera

**Com instal·lar-lo?**

Molt facil, nomes tens que seguir aquests passos:
* ``sudo dnf install rubygems rubygems-devel ruby-devel``
* ``sudo dnf install redhat-rpm-config``
* ``sudo gem install jekyll``

**Recordar: **Poden fer falta altres paquets, com el compilador de C (``sudo dnf install gcc``), etc., 
però el més probable és que ja estiguin instal·lats. En tot cas, cal llegir atentament el missatges 
en pantalla per saber si cal instal·lar res més, tant paquets de Ruby amb gem o paquets del sistema amb dnf.

En el moment que ja hem instalt tot, cal crear un nou lloc executant aquestes ordres (**recomanable, no com a root**):
* ``jekyll new directori_on_anira_tot``
* ``cd foobar``
* ``cp -r ~/.gem/ruby/gems/minima-*/* .``
* ``sed -i 's/^theme:/#&/' _config.yml``
* ``jekyll serve --watch``

Ara ja es pot amb Firefox visitar la pagina ``http://localhost:4000.``

**Vigilar:** Per aturar el servidor caldra usar ``CTRL-C``, fara falta per si fas canvis a ``_config.yml`` ja que cal
reiniciar el servidor.

L'ultim pas que caldrar fer, es recordar que tens que pujar-ho al teu repositori de ``github``
