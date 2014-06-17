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

  

***

For unexpected behaviours could be useful to check the
_get-proxy-settings_ function on
http://github.com/technomancy/leiningen/blob/master/leiningen-core/src/leiningen/core/classpath.clj#L86