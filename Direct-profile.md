The direct profile is a predefined profile which forces all requests to be made directly.

# Setting UI
This profile is predefined and not configurable. It is also hidden from the profile list to prevent confusion.

# Function
When this profile is applied, all connections are created directly, without any proxy involved.

# Inclusion in [[switch profile]]s
Direct connections are used when applied automatically, exactly the same way as applied applied manually.

# Design goal
It should be an wrapper of the Chrome `direct` [proxy mode][Chrome proxy modes]. When included in [[PAC]] scripts, the return value should always be `"DIRECT"`.

[Chrome proxy modes]: https://code.google.com/chrome/extensions/proxy.html#proxy_modes