If you are using lein2 behind an HTTP proxy you need to set the _http_proxy_ environment variable before launching any remote lein command. In a Windows setup, you can do it in the following way:

`set http_proxy=http://username:password@proxy:port`

Then a remote command would work, for example:
`lein new noir test-noir`


***
For unexpected behaviours could be useful to check the _get-proxy-settings_ function on http://github.com/technomancy/leiningen/blob/master/leiningen-core/src/leiningen/core/classpath.clj#L81