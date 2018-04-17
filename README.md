# docker-kiwiirc
A docker build of kiwi-irc made to be used along with an nginx container

## Usage

_This does not container a web server. If you pull this hoping for a ready-to-go Kiwi IRC app, you will be disappointed._

This builds Kiwi directly from source and leaves the "production-ready" minified contents in `/app/kiwiirc`. Using Docker's multi-staged builds, you can copy the assets directly from `/app/kiwiirc/dist` and into your webroot.

It's also recommended that you add your own `config.json` in the same directory, as this one provides the default.

Example:

```
FROM nginx:stable

COPY --from=bbriggs/kiwiirc:latest /app/kiwiirc/dist /usr/share/nginx/html
COPY config.json /usr/share/nginx/html/static/config.json

EXPOSE 80
```

If you find yourself pulling this whole container, you probably did it wrong.
