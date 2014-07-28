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

Since 2.1.2, if `http_no_proxy` is not set then Leiningen will attempt to use your system's existing `no_proxy` environment variable to define non-proxy hosts. The format of the `no_proxy` value is likely to be incompatible with the clj-http proxy selector, so Leiningen will attempt to convert the value. For instance, the following value:

    no_proxy="example1.com,example2.com,example3.com"

is equivalent to:

    http_no_proxy="*example1.com|*example2.com|*example3.com"

## NTML proxies

If you are running a linux system behind an NTML proxy the initial install may fail with a message containing the following:

    org.apache.http.client.protocol.RequestAuthenticationBase process
    WARNING: NTLM authentication error: Credentials cannot be used for NTLM authentication: org.apache.http.auth.UsernamePasswordCredentials

This happens when NTML block certain terminal commands (e.g. wget)

One solution is to install cntlm [http://cntlm.sourceforge.net/](http://cntlm.sourceforge.net/), an intermediate proxy, which forwards requests through to the NTLM proxy with domain authentication. You will need to configure your proxy url, username, password (or better, hashed versions, see the "cntlm -H" option) and your domain in the cntlm.conf file. Your system proxy settings (e.g. $http_proxy env variable) must then be changed to point to the cntlm proxy (default http://localhost:3128).

## SOCKS Proxies

If you are using Leiningen 2.x behind a SOCKS proxy, you might find that getting the JVM to cooperate with your proxy can be very frustrating. It is easiest, then, to turn your SOCKS proxy into an HTTP proxy using Privoxy. Go to [http://privoxy.org/](http://privoxy.org) and install the latest version, and at the end of the configuration file (found at `/etc/privoxy/config` on most Linux systems), add the following:

    forward-socks5 / proxy_host:proxy_port

Replacing `proxy_host` with your SOCKS proxy's hostname or IP, and `proxy_port` with your SOCKS proxy's port. Then, follow the directions above for HTTP proxies.

***

For unexpected behaviours could be useful to check the
_get-proxy-settings_ function on
http://github.com/technomancy/leiningen/blob/master/leiningen-core/src/leiningen/core/classpath.clj#L86