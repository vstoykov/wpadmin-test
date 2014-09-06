# WPAdmin Test

This project is created to demonstrate bug in Django Templateing system.
The bug is present when custom `inclusion_tag` is created which use recursion3
in the template (call itself) and also template loader used is `django.template.loaders.cached.Loader`.

Combination of template tags and templates which leads to `RuntimeError: maximum recursion depth exceeded` using Django's Cached Template Loader is present in `django-wpadmin`.


## Steps to reproduce

1. Clone the repo:

    git clone https://github.com/vstoykov/wpadmin-test.git

2. Create virtual environment (optional)
3. Install Django and django-wpadmin (from PyPi or from source)
4. Run migrations (Django 1.7) or sync database (Django < 1.7)
5. Create superuser
6. Log into administration.
7. Refresh the page

Result: Eror screen with RuntimeError will occur.
