---
language: jinja2
filename: learnjinja2.txt
contributors:
  - ["Dreftymac", "https://github.com/dreftymac"]
---

[Jinja2](http://jinja.pocoo.org/docs/dev/intro/#) is a templating language for Python, modelled after Django. 

```jinja
{#- this is a comment -#}

{#-
  jinja2 supports balanced tokens for specifying comments,
    placeholders, and control structures.
    The tokens are user-configurable.
-#}

Hello {{project_author}}! This is a variable placeholder.

{#-
@@@ ------------------------------------------------------------------------
@@@ the following YAML-formmated data is used as the demonstration data 
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
  - {"alpha":one, "bravo":two, "charlie":three, }
  - {"alpha":uno, "bravo":dos, "charlie":tres,  }
  - {"alpha":ein, "bravo":swei, "charlie":drei, }
-#}
```
