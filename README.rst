GetMediathread.com
==================

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

Now copy the static assets, based on what you see appearing as 404s in the Chrome inspector::

	$ cp /path/to/appstrap/css/theme-style.css apps/theme/static/css/
	$ cp /path/to/appstrap/css/custom-style.css apps/theme/static/css/
 	$ cp /path/to/appstrap/js/script.js apps/theme/static/js/
 	$ cp /path/to/appstrap/js/jquery.flexslider-min.js apps/theme/static/js/
	$ cp /path/to/appstrap/js/jquery.quicksand.js apps/theme/static/js/
	$ cp /path/to/appstrap/img/features/* apps/theme/static/img/features/
	$ cp /path/to/appstrap/img/bg* apps/theme/static/img/

Now we need to override the dropdown.html menu, so we must copy the Mezzanine one into our custom templates dir, preserving the same folder structure::

	$ cp templates/pages/menus/dropdown.html apps/theme/templates/pages/menus/
	$ cp templates/pages/menus/tree.html apps/theme/templates/pages/menus/