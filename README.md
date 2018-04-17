# docker-kiwiirc
A docker build of kiwi-irc made to be used along with an nginx container

## Usage

_This does not container a web server. If you pull this hoping for a ready-to-go Kiwi IRC app, you will be disappointed._

This builds Kiwi directly from source and leaves the contents in `/app/kiwiirc`. You can (should) share a volume between this container and your webserver and let the webserver handle all that stuff. This is just a data container that builds Kiwi.
