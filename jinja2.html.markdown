---
language: jinja2
filename: learnjinja2.txt
contributors:
  - ["Dreftymac", "https://github.com/dreftymac"]
---

[Jinja2](http://jinja.pocoo.org/docs/dev/intro/#) is a templating language for Python. 

```jinja
{# this is a comment #}

{#
  jinja2 supports balanced tokens for specifying comments,
    placeholders, and control structures.
#}

{#
  The tokens are user-configurable.
  <%   this could work as an alternate token syntax  %>
  <!-- this could work as an alternate token syntax -->
#}

Welcome to {{project_name}}!

{#- this is a comment with leading and trailing whitespace trimmed -#}

This is a feature of {{project_desc}}!

{#
@@@ ------------------------------------------------------------------------
@@@ templates can declare their own internal python variables
@@@ ------------------------------------------------------------------------
#}
{%- set orgname   = 'Fake Company'  -%}
{%- set orgyear   = 1999            -%}          
{%- set orgroles  = {"admin":"monitors the servers"
    ,"developer":"processes tasks"
    ,"accountant":"counts the beans"}
    -%}

### ********************
Welcome to {{orgname}}.
We were established in {{orgyear}}.          
{% for role in orgroles.keys() |sort %}
  * The {{role}} person {{orgroles[role]}}!
{% endfor %}
### ********************

{#-
@@@ ------------------------------------------------------------------------
@@@ most data will obviously come from a source external to the template
@@@ this YAML is a demo of external data
@@@ ------------------------------------------------------------------------
project_author:   valued customer
project_name:     barebones jinja2 demo
project_desc:     Learn X in Y minutes
project_url:      "https://github.com/adambard/learnxinyminutes-docs"
list_of_colors:
  - red
  - orange
  - yellow
  - green
  - blue
  - indigo
  - violet
dictionary_of_places:
  New York:
    Capital: Albany
  California:
    Capital: Sacramento
  France:
    Capital: Paris
table_of_datarows:
  - {"alpha":"one", "bravo":"two",  "charlie":"three", }
  - {"alpha":"uno", "bravo":"dos",  "charlie":"tres",  }
  - {"alpha":"ein", "bravo":"swei", "charlie":"drei",  }
-#}


{#-
@@@ ------------------------------------------------------------------------
@@@ dot syntax can be used for nested expressions so long as there's no 
@@@ intervening whitespace
@@@ ------------------------------------------------------------------------                   
#}

### ********************          
{{dictionary_of_places.California.Capital}}
### ********************

### ********************          
{{dictionary_of_places["New York"].Capital}}
### ********************           

{#
@@@ ------------------------------------------------------------------------
@@@ loops can iterate over arbitrary python expressions, with conditions
@@@ and filters
@@@ ------------------------------------------------------------------------                   
#}

{% for field in (table_of_datarows[0].keys() |sort) if not field == 'alpha' %}
  <a href="{{project_url}}">{{field}}</a>
{% endfor %}

{%- for row in table_of_datarows %}
  <b>{{ row.alpha }}</b>
{% endfor -%}
```
