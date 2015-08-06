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

To run the tests::

    virtualenv .virtualenv
    source .virtualenv/bin/activate
    pip install --extra-index-url=http://lti-adx.adelaide.edu.au/pypi/ -U -r django_adelaidex/zipfile/tests/pip.txt 
    python manage.py test


Build
-----

To build the pip package::

    python setup.py 

