If you are using Leiningen 2.x behind an HTTP proxy you need to set
the `http_proxy` environment variable before launching Leiningen.

In Linux/Unix put this in `~/.profile`:

    http_proxy=http://username:password@proxy:port
    https_proxy=http://username:password@proxy:port

Or in Windows:

    http_proxy=http://username:password@proxy:port
    https_proxy=http://username:password@proxy:port

## Non-proxy hosts

To supply a list of hosts for which Lein should bypass the configured proxy, set the `http_no_proxy` environment variable:

    http_no_proxy="*.example1.com|*.example2.com|*.example3.com"

Leiningen uses clj-http which is built on the Apache HttpComponents Client. This means that to set non-proxy hosts you're required to use the Java format (pipe-delimited).

Since 2.1.2, if `http_no_proxy` is not set then Leiningen will attempt to use your system's existing `no_proxy` environment variable to define non-proxy hosts. The format of the `no_proxy` value is likely to be incompatible with the clj-http proxy selector, so Leiningen will attempt to convert the value. An example of the conversion:

    no_proxy="example1.com,example2.com,example3.com"

is equivalent to:

    http_no_proxy="*example1.com|*example2.com|*example3.com"

***

For unexpected behaviours could be useful to check the
_get-proxy-settings_ function on
http://github.com/technomancy/leiningen/blob/master/leiningen-core/src/leiningen/core/classpath.clj#L86