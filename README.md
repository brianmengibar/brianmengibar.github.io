##Dades Personals

**Nom**: Brian Mengibar Garcia

**Identificador**: isx39441584

**Data**: 06/04/2017

**Mòdul**: m09

**UF**: 3

**Enunciat**: Has d’afegir al teu projecte actual amb `Jekyll` una pàgina que mostri el tag-cloud del lloc web.

* Busca a Internet una solució que no impliqui usar **Ruby ni gemmes**, i tal sols faci servir Liquid.

* Documenta tot el que sigui convenient en el fitxer _README.md._

* Implementa el codi triat dins del teu projecte.

* Una vegada funcioni fes una còpia de la pantalla en una imatge de nom **tag-cloud.png**.

* Afegeix a l’arxiu zip els fitxers de Liquid que presenten el tag-cloud, el fitxer tag-cloud.png i el fitxer README.md.


**Lo primer de tot crec que seria convenient explicar una mica que es un** `tag_cloud`:
Un _tag_cloud_ és una **representació visual de les dades de text**,
generalment utilitzat per descriure les metadades de paraules clau 
(etiquetes) en els llocs web, o per visualitzar text de forma lliure. 
Aquest format és útil per percebre ràpidament els termes més prominents. 


**Nota: no confondre:**
* `tagcloud.html` --> codi extret d'internet per poder crear tag-cloud
* `tags.html` --> layout on especifiquem el nom del nostre apartat, titol, etc.**

**Una vegada feta una petita introducció, dono pas als punts que cal explicar:**
Per internet he trobat una solució que esta molt be detallat i explicat
que aqui adjunto el link: **http://jovandeginste.github.io/2016/05/04/add-a-tag-cloud-to-my-jekyll-site.html**
L'ho que m'ha agradat d'aquesta pagina es que et va ficant els troços 
de codi que tens que anar utilitzant, lo que fa que a l'hora 
d'implementar-lo sigui mes senzill.

El primer que he hagut de fer ha estat crear en el directori 
**_layouts** un nou document anomenat `tagcloud.html`. Que contindra aquest
fitxer? El codi extret de la pagina que he posat abans. A continuació cal
crear un document anomentat `tags.html` que es un layout una mica
personalitzat i conte un include, a on? Al fitxer `tagcloud.html` que es
el que he mencionat abans, el necessari per que apareixin els tags
numerats en aquest nou apartat, l'include te que tenir aquesta forma,
obviament en llenguatge liquid **{% include tagcloud.html %}**.

En el moment que hem actualitzat la pagina podem comprobar que ja tenim
un nou apartat, que en el meu cas es diu TagCloud (ja que en el fitxer
`tags.html` en l'apartat _title_ he ficat **TagCloud**) els tags numerats
i amb diferent tamany, es a dir quants mes posts tingui un tag? Mes gran
es fara aquest tag.

A part d'adjuntar els dos fitxers, posso aqui el codi per qualsevol dubte:

**Codi tagcloud.html**
```
<!--Aquest es el codi extret d'internet, d'una pagina que podeu trobar
en el file README.md . Gracies a aquest codi ens apareixera els nostres
tags que tinguem establerts amb diferent tamany, depenent de la quantitat
de posts que hi continguin aquell tag especific i de pas, tambe contindrà
el numero de posts que conte aquest tag-->

{% capture site_tags %}{% for tag in site.tags %}{{ tag | first }}{% unless forloop.last %},{% endunless %}{% endfor %}{% endcapture %}
{% assign site_tags = site_tags | split: ',' %}

{% assign tag_count = 0 %}
{% for tag in site_tags %}
{% assign tag_count = tag_count | plus: site.tags[tag].size %}
{% endfor %}

{% for tag in tags %}
{% assign rel_tag_size = site.tags[tag].size | times: 4.0 | divided_by: tag_count | plus: 1 %}
<span style="white-space: nowrap; font-size: {{ rel_tag_size }}em; padding: 0.6em;">
	<a href="{{ site.baseurl }}/tags/{{ tag | slugize }}" class="tag">{{ tag | slugize }}
		<span>({{ site.tags[tag].size }})</span>
	</a>
</span>
{% endfor %}
```

**Codi tags.html**
```
---
layout: default
title: TagCloud
permalink: /tagcloud/
---

<!--Creacio d'apartat per tag-clouds-->
<div class="apartat-tag">
	<h1 class="page-heading">TagCloud</h1>

	<p class="post-meta" style="text-align: justify;">
	{% capture site_tags %}{% for tag in site.tags %}{{ tag | first }}{% unless forloop.last %},{% endunless %}{% endfor %}{% endcapture %}
	{% assign tags = site_tags | split:',' | sort %}
	{% include tagcloud.html %}
	</p>
</div>
```
