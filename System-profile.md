The system profile is a predefined profile which explicitly uses the system proxy settings.

# Setting UI
This profile is predefined and not configurable. It is also hidden from the profile list to prevent confusion.

# Function
When this profile is applied, the system proxy settings come into effect.

# Inclusion in [[switch profile]]s
This profile cannot be configured as a [[result profile]].

# Design goal
It should be an wrapper of the Chrome `system` [proxy mode][Chrome proxy modes].

[Chrome proxy modes]: https://code.google.com/chrome/extensions/proxy.html#proxy_modes