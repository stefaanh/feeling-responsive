---
title: Tijdstip Test
layout: page
sidebar: left
toc: true
vroeger: 1957-06-10 07:56:04 +0100
later: 2020-12-31 23:59:59 +0100
utc_eeuwwissel: 2000-01-01 00:00:00 UTC
cet_eeuwwissel: 2000-01-01 00:00:00 CET
permalink: tijdstiptest
---

## This page tests different forms of localized date and time strings
{: .no_toc }

These examples are based on the documentation of Ruby, Liquid and Jekyll
* [Ruby Time class](https://ruby-doc.org/stdlib-2.7.0/libdoc/time/rdoc/Time.html#method-c-zone_offset)
* [Official Liquid filters](https://shopify.github.io/liquid/filters/date/)
* [Jekyll Liquid filters](https://jekyllrb.com/docs/liquid/filters/)
* [STRFTIME online tool](http://strftime.net/)


### Nu ("now" en "today")

|----+----+----|
|filter|rendering|opmerking|
|----:|----|----|
|{% raw %}{{ "now" \| date_to_xmlschema }}{% endraw %} | {{ "now" | date_to_xmlschema }} | jekyll filter : ISO 8601 format. |
|{% raw %}{{ "today" \| date_to_xmlschema }}{% endraw %} | {{ "today" | date_to_xmlschema }} | jekyll filter : ISO 8601 format. |
|{% raw %}{{ "now" \| date_to_string }}{% endraw %} | {{ "now" | date_to_string }} | jekyll filter |


### Begin van de dag op middernacht
Tijdstip afgekapt op dagresolutie (`'%F'`)
{% assign middernacht = "now" | date: '%F' %}  
`{% raw %}{% assign middernacht = "now" | date: '%F' %}{% endraw %}`  
{{ middernacht | date_to_xmlschema }}

### Einde van de dag op middernacht
Tijdstip in seconden (`'%s'`) + een daglang seconden (24 uur x 60 min. x 60 sec. = 86400 sec.) , afgekapt op dagresolutie (`'%F'`) 
{% assign end-of-day = "now" | date: '%s' | plus: 86400 | date: '%F' %}  
`{% raw %}{% assign end-of-day = "now" | date: '%s' | plus: 86400 | date: '%F' %}{% endraw %}`  
{{ end-of-day }}

### UTC Eeuwwissel
frontmatter: page.utc_eeuwwissel: {{ page.utc_eeuwwissel }}  
`{% raw %}{{ page.utc_eeuwwissel | date_to_xmlschema }}{% endraw %}`  
{{ page.utc_eeuwwissel | date_to_xmlschema }}  
`{% raw %}{{ page.utc_eeuwwissel | date: "%F %T" }}{% endraw %}`  
{{ page.utc_eeuwwissel | date: "%F %T" }}

### CET Eeuwwissel
frontmatter: page.cet_eeuwwissel: {{ page.cet_eeuwwissel }}  
`{% raw %}{{ page.utc_eeuwwissel | date_to_xmlschema }}{% endraw %}`  
{{ page.utc_eeuwwissel | date_to_xmlschema }}  
`{% raw %}{{ page.utc_eeuwwissel | date: "%F %T" }}{% endraw %}`  
{{ page.utc_eeuwwissel | date: "%F %T" }}

----

### 'format/time' include
Rendert enkel uur en minuten als tekst in een lang, kort of "strftime" formaat.  
Toont niks indien uur en minuut 0 zijn.

#### Parameters
* **timestamp**
*	**format**: één van
    * 'lang'
    *	'kort' (default)
    *	Ruby "strftime" string.  
			
----

#### {% assign halfelf = "2019-03-07 10:30" %} Voorbeeld: op het haf uur
{{halfelf}}

`{% raw %}{% include format/time timestamp=halfelf format="lang" %}{% endraw %}`  
*"{% include format/time timestamp=halfelf format="lang" %}"*    

`{% raw %}{% include format/time timestamp=halfelf format="kort" %}{% endraw %}`  
*"{% include format/time timestamp=halfelf format="kort" %}"*    

`{% raw %}{% include format/time timestamp=halfelf format="(%H:%M)" %}{% endraw %}`  
*"{% include format/time timestamp=halfelf format="(%H:%M)" %}"*    

`{% raw %}{% include format/time timestamp=halfelf %}{% endraw %}`  
*"{% include format/time timestamp=halfelf  %}"*    

----

#### {% assign tien_uur = "2019-03-07 10:00" %} Voorbeeld: een precies uur
{{tien_uur}}

`{% raw %}{% include format/time timestamp=tien_uur format="lang" %}{% endraw %}`  
*"{% include format/time timestamp=tien_uur format="lang" %}"*    

`{% raw %}{% include format/time timestamp=tien_uur format="kort" %}{% endraw %}`  
*"{% include format/time timestamp=tien_uur format="kort" %}"*    

`{% raw %}{% include format/time timestamp=tien_uur format="(%H:%M)" %}{% endraw %}`  
*"{% include format/time timestamp=tien_uur format="(%H:%M)" %}"*    

`{% raw %}{% include format/time timestamp=tien_uur %}{% endraw %}`  
*"{% include format/time timestamp=tien_uur %}"*    

----

### 'format/date' include
Rendert enkel datum als tekst in een lang, kort of "strftime" formaat.   
Toont optioneel de weekdag.  
Toont niks indien uur en minuut 0 zijn.

#### Parameters
* **timestamp**
*	**format**: één van
    * "lang"
    *	"kort" (default)
    *	Ruby *"strftime"* string.  
          (default `site.date_short` which is "{{site.date_short}}"  
          falls back to "%e/%-m/%Y")
* **weekdag**: werkt enkel wanneer format "lang" of "kort" is
    * {{ true }}
    *	{{ false }} (default)
		
----

#### {% assign nu = "now"  | date_to_xmlschema %} Voorbeeld: Nu
{{nu}}

`{% raw %}{% include format/date timestamp=nu format="lang" weekdag=true %}{% endraw %}`    
*"{% include format/date timestamp=nu format="lang" weekdag=true %}"*   

`{% raw %}{% include format/date timestamp=nu format="kort" weekdag=true %}{% endraw %}`    
*"{% include format/date timestamp=nu format="kort" weekdag=true %}"*

`{% raw %}{% include format/date timestamp=nu format="lang" %}{% endraw %}`    
*"{% include format/date timestamp=nu format="lang" %}"*   

`{% raw %}{% include format/date timestamp=nu format="kort" weekdag=false %}{% endraw %}`    
*"{% include format/date timestamp=nu format="kort" weekdag=false %}"*

`{% raw %}{% include format/date timestamp=nu format="(%H:%M)" %}{% endraw %}`    
*"{% include format/date timestamp=nu format="(%H:%M)" %}"*

`{% raw %}{% include format/date timestamp=nu %}{% endraw %}`  
*"{% include format/date timestamp=nu %}"*
