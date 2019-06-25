Django Bootstrap Fields
=======================

``django-bootstrap-fields`` provides you with a ``{% dbs_field %}`` tag
that allows you to easily render Django form fields with complete
Bootstrap html markup.

Installation
------------

Install latest stable version into your python path using ``pip``:

::

    pip install -U django-bootstrap-fields

Add ``dbs_fields`` to your ``INSTALLED_APPS`` in ``settings.py``:

::

    INSTALLED_APPS = (
        ...
        'dbs_fields',
    )

Templates
---------

You can set your default template pack for your project using the
``DBS_TEMPLATES`` Django settings variable:

::

    DBS_TEMPLATES = 'bootstrap4'  # Options: 'bootstrap3', 'bootstrap4', 'bootstrap4custom'

Usage
-----

One tag to rule them all! ``django-bootstrap-fields`` only comes with
one easy to use tag that will detect which field is being rendered and
style it accordingly.

::

    {% dbs_field field inline=True sr_label=True prepend="$" append=".00" %}

Example
-------

::

    {% extends “base.html” %}
    {% load dbs_tags %}

    {% block content %}
        
        <form action="." method="post">
            {% csrf_token %}
            {% for field in form %}
                {% dbs_field field %}
            {% endfor %}
        </form>

    {% endblock content %}