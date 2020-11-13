# HTTP/2.0

- [nghttp2](https://github.com/nghttp2/nghttp2): HTTP/2 C Library and tools
- [spof-o-matic](https://github.com/pmeenan/spof-o-matic)
- [Can I use ?](https://caniuse.com/?search=http2)

## Debug

### Book

- [Using WebPageTest](https://www.oreilly.com/library/view/using-webpagetest/9781491902783/)

### Tools

- [chrome://net-internals](chrome://net-internals)
- [chrome://net-export/](chrome://net-export/)
- [netlog-viewer](https://netlog-viewer.appspot.com/#import)
- [chrome-http2-log-parser](https://github.com/rmurphey/chrome-http2-log-parser)
- Chrome: [Network Analysis Reference](https://developers.google.com/web/tools/chrome-devtools/network/reference)
- [net/http2](https://github.com/golang/net/tree/master/http2)
- [Wireshark](https://www.wireshark.org/)
- [Charles](https://www.charlesproxy.com/)

#### curl

```bash
curl -v --http2 https://www.facebook.com

...
* ALPN, offering h2
* ALPN, offering http/1.1
...
* TLSv1.2 (OUT), TLS handshake, Client hello (1):
* TLSv1.2 (IN), TLS handshake, Server hello (2):
* TLSv1.2 (IN), TLS handshake, Certificate (11):
* TLSv1.2 (IN), TLS handshake, Server key exchange (12):
* TLSv1.2 (IN), TLS handshake, Server finished (14):
* TLSv1.2 (OUT), TLS handshake, Client key exchange (16):
* TLSv1.2 (OUT), TLS change cipher, Client hello (1):
* TLSv1.2 (OUT), TLS handshake, Finished (20):
* TLSv1.2 (IN), TLS change cipher, Client hello (1):
* TLSv1.2 (IN), TLS handshake, Finished (20):
* SSL connection using TLSv1.2 / ECDHE-ECDSA-AES128-GCM-SHA256
* ALPN, server accepted to use h2
...
< HTTP/2 200
...
```

#### OpenSSL

```bash
echo | openssl s_client -connect \
  www.facebook.com:443 -servername www.facebook.com \
  -alpn spdy/2,h2,h2-14 | grep ALPN

...
DONE
ALPN protocol: h2
```
