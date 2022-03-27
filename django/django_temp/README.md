# DjangoTemplateNote

# Comparing

```
{% if name == "someone" %}
   ............
   ............
{% endif %}

{% if name != "someone" %}
   ............
   ............
{% endif %}
```

# Dot lookup

```
Dot lookups can be summarized like this: when the template system encounters a dot in a variable name, it tries the following lookups, in this order:

Dictionary lookup (e.g., foo["bar"])
Attribute lookup (e.g., foo.bar)
Method call (e.g., foo.bar())
List-index lookup (e.g., foo[2])

The system uses the first lookup type that works. It’s short-circuit logic.
```
