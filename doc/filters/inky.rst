``inky``
========

.. versionadded:: 2.12
    The ``inky`` filter was added in Twig 2.12.

The ``inky`` filter processes an `inky email template
<https://github.com/zurb/inky>`_:

.. code-block:: twig

    {% apply inky %}
        <row>
            <columns large="6"></columns>
            <columns large="6"></columns>
        </row>
    {% endapply %}

You can also use the filter on an included file:

.. code-block:: twig

    {{ include('some_template.inky.twig')|inky }}

.. note::

    The ``inky`` filter is part of the ``CssInlinerExtension`` which is not
    installed by default. Install it first:

    .. code-block:: bash

        $ composer req twig/cssinliner-extra

    Then, use the ``twig/extra-bundle`` on Symfony projects or add the extension
    explictly on the Twig environment::

        use Twig\Extra\CssInliner\CssInlinerExtension;

        $twig = new \Twig\Environment(...);
        $twig->addExtension(new CssInlinerExtension());
