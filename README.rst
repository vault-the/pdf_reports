PDF Reports
===========

.. image:: https://travis-ci.org/Edinburgh-Genome-Foundry/pdf-reports.svg?branch=master
   :target: https://travis-ci.org/Edinburgh-Genome-Foundry/pdf-reports
   :alt: Travis CI build status

.. image:: https://coveralls.io/repos/github/Edinburgh-Genome-Foundry/pdf-reports/badge.svg?branch=master
   :target: https://coveralls.io/github/Edinburgh-Genome-Foundry/pdf-reports?branch=master


*PDF Reports* is a Python library to create nice-looking PDF reports from HTML or `Pug <https://pugjs.org>`_ templates. It is used at the `Edinburgh Genome Foundry <http://www.genomefoundry.org//>`_ to unify the look of web-generated reports across different libraries and services.

For instance your template ``template.pug`` may look like this (see a `full example <>`_):

.. code:: pug

    #sidebar I am the text in the sidebar.

    h1 {{ title }}

    .ui.piled.segment
      p Oh hi there ! I am some text in a cool box.

    ...

Your Python code will be as follows:

.. code:: python
    from pdf_reports import pug_to_html, write_report
    html = pug_to_html("template.pug", title="My report")
    write_report(html, "example.pdf")


And your final result may look like this:

There is no documentation at the moment but since it is only two functions you can just have a look at their in-code documentation.

How it works
-------------

The library consists of just a few lines of Python, using `pypugjs <https://github.com/akubera/pypugjs>`_ to parse Pug templates,  optionally including stylesheets from the `Semantic UI <https://semantic-ui.com/>`_ CSS framework, and finally calling `weasyprint <http://weasyprint.org/>`_ for PDF generation.

Importantly, because of the use of Semantic UI and the Lato font, pdf_reports currently requires an internet connection. It is also not the fastest report generator you will come accross, partly because it uses internet files.

Installation
-------------

You can install the library via PIP

.. code::

    sudo pip install pdf_reports

Alternatively, you can unzip the sources in a folder and type

.. code::

    sudo python setup.py install

License = MIT
--------------

This open-source software project was originally written at the `Edinburgh Genome Foundry
<http://www.genomefoundry.org/>`_ by `Zulko <https://github.com/Zulko>`_
and `released on Github <https://github.com/Edinburgh-Genome-Foundry/pdf_reports>`_ under the MIT licence (¢ Edinburg Genome Foundry). Everyone is welcome to contribute !