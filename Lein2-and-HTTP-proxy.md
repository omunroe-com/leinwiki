If you are using lein2 behind an HTTP proxy you need to set the _http_proxy_ environment variable before launching any remote lein command. In a Windows setup, you can do in the following way:

`set http_proxy=http://username:pwd@proxy.com:port`

Then a remote command would work, for example:
`lein new noir test-noir`

