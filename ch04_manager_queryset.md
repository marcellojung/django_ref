# Chapter4

### Python shell 
* [IPython](http://ipython.org/)
* [BPython](https://bpython-interpreter.org/)
* [ django-extensions](https://django-extensions.readthedocs.io)

### Manager & Queryset
* [Managers](https://docs.djangoproject.com/en/2.1/topics/db/managers/)
* [QuerySet API reference](https://docs.djangoproject.com/en/2.1/ref/models/querysets/)
* [Making queries](https://docs.djangoproject.com/en/2.1/topics/db/queries/)




Django-debug-Toolbar
---
* [Django Debug Toolbar](https://django-debug-toolbar.readthedocs.io/en/latest/installation.html)

* settings.py  추가
    ~~~python
    INSTALLED_APPS = [
        'debug_toolbar',
    ]

    MIDDLEWARE = [
        'debug_toolbar.middleware.DebugToolbarMiddleware',
    ]

    INTERNAL_IPS = ['127.0.0.1']
    ~~~~

* myproject/urls.py 추가
    ~~~python
    from django.conf import settings
    if settings.DEBUG:
        import debug_toolbar
        urlpatterns += [
            path('__debug__/', include(debug_toolbar.urls)),
        ] 
    ~~~

