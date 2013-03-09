getmediathread
==============

Mezzanine-based project for getmediathread.com

Instructions for setting up getmediathread.com::

	$ pip install -r requirements.txt


How this was made
-----------------

To make this custom theme, we purchased the AppStrap bootstrap theme from wrapbootstrap.com. For $12, it's a steal!

Make a directory structure to hold the theme customizations::

	apps/
	__init__.py
	|__ theme/
		|__ __init__.py
		|__ static/
		|__ templates/

Now run the ``collecttemplates`` command to get all the templates from Mezzanine copied to the ``templates`` directory::

	$ python manage.py collecttemplates
	Copied 43 templates

Now copy the base.html and index.html into your app's template directory::

	$ cp templates/base.html apps/theme/templates/
	$ cp templates/index.html apps/theme/templates/

Now copy the appstrap homepage template that you want to use into your app's template directory::

	$ cp /path/to/appstrap/fixed-header.htm apps/theme/templates/

