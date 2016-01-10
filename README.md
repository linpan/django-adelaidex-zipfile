django\_adelaidex.zipfile
========================

Response and View mixins to allow the creation of zipfile views, for
downloading django ListView or SingleObjectView content.

Usage
-----

Detail view example::

    from django.views.generic.DetailView
    from myapp.models import Model
    class ZipFileDetailView(ZipFileViewMixin, DetailView):
        object_template_name = 'view.html' # required
        model = Model

List view example::

    from django.views.generic.ListView
    from myapp.models import Model
    class ZipFileListView(ZipFileViewMixin, ListView):
        object_template_name = 'view.html' # required
        object_filename = 'obj%d.html'     # optional, default obj%d
        zip_filename = 'list.zip'          # optional, default download.zip
        model = Model

Tests
-----

To set up the virtualenv::

    virtualenv .virtualenv
    source .virtualenv/bin/activate
    pip install --extra-index-url=http://lti-adx.adelaide.edu.au/pypi/ -U -r django_adelaidex/zipfile/tests/pip.txt 

To run the tests::

    python manage.py test

To check coverage::

    coverage run --include=django_adelaidex/*  python manage.py test     
    coverage report

    Name                                           Stmts   Miss  Cover
    ------------------------------------------------------------------
    django_adelaidex/__init__                          0      0   100%
    django_adelaidex/zipfile/__init__                  0      0   100%
    django_adelaidex/zipfile/mixins                   26      0   100%
    django_adelaidex/zipfile/response                 17      0   100%
    django_adelaidex/zipfile/tests/__init__            0      0   100%
    django_adelaidex/zipfile/tests/settings           10      0   100%
    django_adelaidex/zipfile/tests/test_response     100      0   100%
    ------------------------------------------------------------------
    TOTAL                                            153      0   100%

Build
-----

To build the pip package::

    python setup.py sdist

