A **profile** in [[SwitchyOmega]] is a proxy mode that can be applied manually or automatically.

In addition to [[fixed servers|fixed server profile]], [[PAC]] scripts are also [[supported|PAC profile]].
There is also a new type of profiles, [[switch profile]], which calls other profiles based on various conditions.
Rule lists are processed as [[Rule list profile]]s.

# Simple profiles
## [[Fixed server profile]]
A fixed server profile contains a set of fixed servers for the traffic protocols (HTTP, HTTPS, FTP, fallback).
It can be applied directly or automatically applied as results of [[switch profile]]s.

## [[Direct profile]]
The direct profile is a predefined profile. When applied, it forces all traffic to be made directly. It can also be a result of a [[switch profile]].

## [[System profile]]
The system profile is a predefined profile which allows using the proxy config of the current environment. This profile cannot be included in a [[switch profile]] because it is not supported in [[PAC]] scripts.

## [[AutoDetect profile]]
The AutoDetect profile is a predefined profile and an equivalent to Chrome `auto_detect` [mode][Chrome proxy modes].
**TODO**(catus): Find out the exact effect of setting Chrome `auto_detect` [mode][Chrome proxy modes], and see whether it can be included in a [[switch profile]].

[Chrome proxy modes]: https://code.google.com/chrome/extensions/proxy.html#proxy_modes
## [[PAC profile]]
A PAC profile contains a [[PAC]] script, which can be included in the profile or [[loaded dynamically|PAC downloading]] from a URL or a local file.

# Complex profiles
## [[Switch profile]]
Switch profiles deprecate the AutoSwitch mode in [[SwitchySharp]]. Like the AutoSwitch mode, they choose a [[result profile]] according to the user defined [[match rules|switch rule]] dynamically for each request when applied.
Switch profiles themselves are valid result profiles, which allows more flexible configuration.

## [[Rule list profile]]
Rule list profiles extend the "Online Rule List" feature of SwitchySharp. They are collections of [[switch profile condition|condition]]s.
If any of the conditions are met, the match [[result profile]] is used. If any [[reverse condition]]s are met, or all the conditions failed, the default result profile is used.