.. _settings:

Settings
********

The app offers several settings. By default, they are:

.. code-block:: python

   PODCAST_SINGULAR = True

   PODCAST_ID = 1

   PODCAST_NO_ARTWORK = 'podcast/img/no_artwork.png'

   PODCAST_PAGINATE_BY = 10

``PODCAST_SINGULAR``
====================

A boolean indicating display of multiple podcast shows.

The app displays a single show by default. If you would like to display multiple shows, set the ``PODCAST_SINGULAR`` variable in ``settings.py``.

.. code-block:: python

   PODCAST_SINGULAR = False

If you have multiple shows, you might want to edit the URL pattern in ``urls.py`` from ``podcast/`` to ``podcasts/``, although the difference is purely cosmetic.

.. code-block:: python

   urlpatterns = [
       # ...
       url(r'^podcasts/', include('podcast.urls')),
   ]

``PODCAST_ID``
==============

An integer indicating the primary key of the show to display; used when ``PODCAST_SINGULAR`` is ``True``. Concept modeled after the |SITE_ID|_ setting used in the `Sites <https://docs.djangoproject.com/en/1.10/ref/contrib/sites/>`_ application.

.. |SITE_ID| replace:: ``SITE_ID``
.. _SITE_ID: https://docs.djangoproject.com/en/1.10/ref/settings/#site-id

The app displays the first show by default.

``PODCAST_NO_ARTWORK``
======================

A string indicating the path to an image used when artwork is lacking; used for shows, episodes, and video enclosures.

Although the path can be customized in the setting, you're probably better off overriding the image look up at the project level; that is, creating a new image at ``myproject/static/podcast/img/no_artwork.png``.

``PODCAST_PAGINATE_BY``
=======================

An integer indicating how many items to display in a list view or in a detail view of related objects; used for shows and episodes.
