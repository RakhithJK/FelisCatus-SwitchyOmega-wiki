The Auto-detect profile is a predefined profile which acts like a [[PAC profile]] with its URL fixed to `http://wpad/wpad.dat`.

# Setting UI
This profile is predefined and not configurable. It is also hidden from the profile list to prevent confusion.

# Function
When applied directly, the browser will try downloading `http://wpad/wpad.dat` and use the response content as a [[PAC]] script. If the request failed, the browser fall backs to direct connection. See [[PAC profile]].
When included in a [[switch profile]], the effects are exactly the same as those of a [[PAC profile]] with URL `http://wpad/wpad.dat`.

# Inclusion in [[switch profile]]s
See [[PAC profile]].

# Design
It should set the [proxy mode][Chrome proxy modes] to `auto_detect` when applied directly. When included, it should be treated as a [[PAC profile]] internally.

[Chrome proxy modes]: https://code.google.com/chrome/extensions/proxy.html#proxy_modes