A fixed server profile contains the proxy servers to be used for requests. 

# Setting UI
**TODO**(catus)

# Function
**TODO**(catus)

# Inclusion in [[switch profile]]s
**TODO**(catus)

# Design goal
It should fully support all kinds of values in [Chrome Proxy Rules][]. The protocol of traffic can be different from the schemes of [[proxy server]]s.
A fixed server profile should be translatable **to and from** a Chrome `ProxyRules` object.

[Chrome Proxy Rules]: https://code.google.com/chrome/extensions/proxy.html#proxy_rules