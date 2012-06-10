A fixed server profile contains the proxy servers to be used for requests. 

# Settings UI
_Maybe a 4*4 grid: 4 traffic protocol rows (HTTP, HTTPS, FTP, fallback) and 3 field columns (scheme, host, port). Or the users can use one single proxy server for all traffic in a way._
**TODO**(catus)

# Function
When a fixed server profile is applied directly, the request traffic will go through the corresponding proxy servers for the protocol. If a fallback proxy is provided, it handles all traffic on the protocol which proxy server has not been set.

# Inclusion in [[switch profile]]s
If a fixed server profile is included as a [[result profile]], it should first parse the protocol from the request URI, and then choose the right server according to the same rules above.

# Design goals
It should fully support all kinds of values in [Chrome Proxy Rules][]. The protocol of traffic can be different from the schemes of [[proxy server]]s.
A fixed server profile should be translatable **to and from** a Chrome `ProxyRules` object.
For each protocol(HTTP, HTTPS or FTP) and the fallback, three fields can be set: scheme, host (required) and port. Scheme should be "http", "https", "socks4" or "socks5".

[Chrome Proxy Rules]: https://code.google.com/chrome/extensions/proxy.html#proxy_rules