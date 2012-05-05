===========
Shess README
============


Overview
--------

Shess (pronounce as she-es-es) is a DSL to generate CSS in Python, Ruby, and so on.

Benefits:

* Variable is available to abstract color value and so on.
* Function (or method) is available to make CSS to be DRY.
* Arithmetic operation is available to calculate width, margin or padding.
* Nested structure is available to represent CSS rulesets structure.


Example (Python)
----------------

example.py::

    from shess import CSS

    main_color = '#09f'
    back_color = '#fff'

    css = CSS()

    with css('.table'):
        css.border_collapse = 'collapse'
        with css('td', 'th'):
            css.border     = 'solid 1px %s' % main_color
            css.padding    = '2px 5px'
        with css('th'):
            css.background = main_color
            css.color      = back_color

    print(str(css))


Output::

    $ python example.py
    .table {
      border-collapse: collapse;
    }
    .table td, .table th {
      border: solid 1px #09f;
      padding: 2px 5px;
    }
    .table th {
      background: #09f;
      color: #fff;
    }


How to checkout
---------------

Shess's repository contains branches for each language.
Please switch branch what you want after cloning resposity.

    ## if you want to get Python source code of Shess:
    $ git clone https://github.com/kwatch/shess.git
    $ cd shess/
    $ git checkout python     # switch to 'python' branch


License
-------

MIT License


Author
------

Makoto Kuwata <kwa@kuwata-lab.com>
