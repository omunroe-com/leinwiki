If you are using Leiningen 2.x behind an HTTP proxy you need to set
the `http_proxy` environment variable before launching Leiningen.

In Linux/Unix put this in `~/.profile`:

    http_proxy=http://username:password@proxy:port

Or in Windows:

    http_proxy=http://username:password@proxy:port

***

For unexpected behaviours could be useful to check the
_get-proxy-settings_ function on
http://github.com/technomancy/leiningen/blob/master/leiningen-core/src/leiningen/core/classpath.clj#L81
