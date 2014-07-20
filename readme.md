# About
This is a base project for Django REST endpoint plus generic  api with AngularJS frontend using the elegant and practical Zurb Foundation for styling.

_This readme is very vague, and only meant for myself (and others that know the basics of Django + Angular, Foundation, and Docker. Pretty specific and limited crowd I know :)_
# Docker
### PostGresQL Container with PostGIS

run `docker build -t jradd/postgis:latest .` to build. 
And use the following runtime command to initialize.
```
CONTAINER=$(docker run -d -v /var/lib/postgresql jradd/postgis:2.1)
```


# Installing
Build requirements with `bower install` from the requirements directory.
Django requirements will change frequently, as this is a premature build for personal projects.


```
./manage.py migrate
```


Add the apps directory to python path with `add2virtualenv apps/` from project root.


Via `/admin`, add a Site record for localhost and at least one SocialApp (Twitter, Google, Facebook) for Auth backend.



# Static File Management

`bower install` installs apps to `static/bower_components`, including foundation and angular

In dev mode, we serve directly out of `static`.

In production, `collectstatic` copies all of this plus media included with installed apps over to `static_apps`, which is where everything gets served from.

To enable Django's minification enable Compression:
`COMPRESS_ENABLED = True`

# API

append `?format=json` to any REST URL to return raw data.
