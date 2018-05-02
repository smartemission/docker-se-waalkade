# Waalkade App

The `Waalkade` is a minimal web application for City of Nijmegen that shows the current values of
sensors and live video on Waalkade.

## Hosting

The Docker Image is hosted as: [smartemission/se-waalkade at DockerHub](https://hub.docker.com/r/smartemission/se-waalkade).

## Environment

At the moment no environment variables are required: the `Waalkade` will use the
locally running `sosemu` API.

## Architecture

The image contains a static HTML webapp running in an `nginx` webserver.
It uses Leaflet for mapping and Handlebars for client-side templating.

The app should be accessed via the URL `<container-address>/waalkade`.
Main reason is to allow `nginx` to do a relative `301` redirect to `/waalkade/`, i.s.o.
every reverse proxy like Kubernetes or Traefik to bother with redirects.

The app uses the `sosemu` API service which is called via JSONP from the browser.

## Links

* SE Platform doc: http://smartplatform.readthedocs.io/en/latest/
