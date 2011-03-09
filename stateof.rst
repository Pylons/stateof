.. include:: <s5defs.txt>

PyCon 2011: State of Pylons, Turbogears, and repoze.bfg
=======================================================

:Authors:  Chris McDonough, Ben Bangert, Mark Ramm
:Date: 3/11/2011

``repoze.bfg``
--------------

- Web framework inspired by Pylons, Django and Zope.

.. class:: center

   .. image:: bfgbook3d-front.png

``repoze.bfg``
--------------

- First released in July 2008.

- Latest release of repoze.bfg: 1.3 on November 1, 2010.

- Since November 1, 2010, about 1350 downloads (weak takeup).

- 198 members of the repoze-dev maillist as of Mar 5 2011.

- ~28 PyPI packages which depend on repoze.bfg

Pyramid
-------

October 2010, ``repoze.bfg`` was forked to become Pyramid, a Pylons Project
subproject.

.. image:: pyramid-positive-80.png

Sample Application
-------------------

::

   # imports elided
   @view_config(route_name='home')
   def hello_world(request):
       return Response('Hello world!')

   if __name__ == '__main__':
       config = Configurator()
       config.add_route('home', '/')
       config.scan()
       app = config.make_wsgi_app()
       serve(app, host='0.0.0.0')

Pyramid
-------

- ``repoze.bfg`` minus ZCML, plus Mako, built-in sessioning, better URL
  dispatch features, and better imperative configuration extensibility.

- Works on PyPI and Jython.

- Latest release of Pyramid: 1.0 on January 31, 2011.

- Since January 31, 2011 ~ 4500 downloads (strong takeup).

- ~34 PyPI packages which depend on Pyramid as of March 5.

Pyramid Features
----------------

- Map URLs to code.

- Authentication and authorization.

- Internationalization.

- Single-file apps or apps as packages.

- Easy unit, integration, functional testing.

- WSGI deployment.

- Comprehensive docs.

Pyramid Features (more)
-----------------------

- Chameleon and Mako templating out of the box; Jinja2 as an add-on.
  Multiple templating systems can be used at the same time.

- Easy "REST API" creation and JSON rendering.

- Runs on CPython 2.4+, GAE, Jython, and PyPy (no Python 3 support).

- Multiple modes of configuration.

- Extensible configuration ("plugins", reuse apps without forking).

- Static asset features.

Pyramid Features (more)
-------------------------

- Sessioning, flash messaging, CSRF protection.

- Event system.

- Exception views.

- WSGI middleware-provided exception debugging (WebError) and profiling
  (repoze.profile).

- Fast.

- 100% statement coverage via unit tests.

Pyramid Non-Features
--------------------

- Not a "full-stack" framework; persistence-system agnostic, no admin
  interface.

- Not a "microframework".  Has ~ 16 distribution dependencies.
  Microframework-like single-file apps possible though.

- Somewhere in the middle; provides useful "rails".

Paster Templates
-----------------

- Pyramid itself has very few opinions.

- Paster templates have lots of opinions.

- Templates use (and disuse) specific Pyramid features and provide
  integrations with specific persistence systems (SQLAlchemy, ZODB, MongoDB,
  etc).

Technologies
------------

- WebOb

- Paste

- ``zope.component``

- Chameleon

- Mako

- Venusian (scanning library)

Not Zope
--------

- Pyramid != Zope.  Uses ``zope.component`` as a library, but it is not an
  application-developer visible feature.

- Steals some features from Zope though (traversal, declarative
  authorization).

Not Pylons
----------

- Pyramid shares no DNA with Pylons.

- But supports many Pylons-esque features.

- Similar, but not identical routing syntax.

- Plugpoints implemented via composition rather than subclassing.

- Has an analogue of Pylons-style "controllers" called "handlers".

"MVC"
-----

- Labels.

- To me, it's not MVC.  To you, it might be.

Pyramid Add-Ons
---------------

* ``pyramid_beaker``: Beaker session backend plug-in.

* ``pyramid_handlers``: analogue of Pylons-style "controllers" for Pyramid.

* ``pyramid_jinja2``: Jinja2 template renderer for Pyramid

* ``pyramid_mailer``: a package for sending emails.

Pyramid Add-Ons (more)
----------------------

* ``pyramid_rpc``: RPC service add-on for Pyramid.

* ``pyramid_who``: Authentication policy for pyramid using repoze.who 2.0
  API.

* ``pyramid_xmlrpc``: XML-RPC add-on for Pyramid

* ``akhet``: (in progress): Pylons-style development for Pyramid.

Pylons Project
--------------

- Merger of the Pylons and ``repoze.bfg`` communities.  Hoping to bring some
  TurboGears folks aboard in 2011.

- Pylons 1.x web framework shifted into “legacy” status.  Maintained
  indefinitely.

Pylons Subprojects
------------------

- Pylons-the-web-framework.

- Pyramid and its add-ons.

- Deform/Colander (form lib and validation lib).

BFG to Pyramid
--------------

- Almost unanimous support from community members wrt to switch to Pyramid
  branding.

- Almost total conversion of BFG community into Pylons community.

- BFG 1.3 will be the last release: superseded by Pyramid.

- Pyramid is mostly backwards compatible with ``repoze.bfg`` via the use of
  automated conversion via the ``bfg2pyramid`` script.

BFG Community Quotes
--------------------

`"Congrats! Great to see synergy, particularly amongst Python web
frameworks!"`

`"HOORAY!!!!!"`

`"This just totally made my day! Way to go guys."`

BFG Community Quotes
--------------------

`"Can I just say this is an almost unheard of degree of maturity and
pragmatism for a framework author to display. I'm very impressed, and this is
surely a good thing. Congratulations. :)"`

