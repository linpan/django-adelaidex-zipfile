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

