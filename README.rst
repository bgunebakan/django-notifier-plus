===============
django-notifier-plus
===============

Send notifications (Email, Push, SMS etc) and manage preferences and permissions per user and group.

See full documentation at http://django-notifier-plus.rtfd.org/

To register a notification::

	create_notification('test-notification')

To send notifications::

	send_notification('test-notification', [user1, user2, ..])


Installation
============

Install via ``pip``::

    $ pip install django-notifier-plus


Setup
=====

1. Add ``notifier`` to INSTALLED_APPS in your django settings file.

    ::

        INSTALLED_APPS = (
            ...
            'notifier',
            ...
        )

2. Settings

    If you are going to use any custom backends to send notifications, add the setting NOTIFIER_BACKENDS to your settings file. If this setting is not defined, only the EmailBackend is used by default.

    ::

        NOTIFIER_BACKENDS = (
            'notifier.backends.EmailBackend',
            'path.to.custom.backend.CustomBackend',
        )


3. Run ``migrate`` to create the necessary tables in the database.
    
    ::

        $ python manage.py migrate

