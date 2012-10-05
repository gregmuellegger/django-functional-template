django-functional-template
==========================

**django-functional-template** is a django app that provides a few template
filters that allows you to use functional programming paradigms in django
templates.

Ideas
-----

Those filters usually operate on a list of objects.

Here are some ideas how they might work::

    Apply the filter "first" to all the objects in the list.
    {{ object_list|map:"first" }}

    Return a list that contains the values of the objects attribute "id"
    {{ object_list|attr:"id" }}

    Remove all falsy elements.
    {{ object_list|filter }}

    Remove all truethy elements.
    {{ object_list|exclude }}

    Returns true if all elements are true
    {{ object_list|all }}

    Returns true if at least one element is true
    {{ object_list|any }}

    Returns true if at least on of the elemnts equals 2
    {{ object_list|any:2 }}

Use the different filters together for greater power::

    Test if any of the objects is public
    {{ object_list|attr:"is_public"|any }}

    Get the number of items that are not superusers
    {{ object_list|attr:"is_superuser"|exclude|length }}

    Check if one of the strings in a list starts with an "A"
    {{ object_list|map:"first"|any:"A" }}
