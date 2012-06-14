Host wildcard conditions match [[URL]]s to wildcard patterns.
This condition type is the preferred way of applying profiles to websites.

## Magic
If a wildcard pattern begins with `.` or `*.`, then it matches any subdomain **and the main domain**.

To override this behavior, use `**` instead of `*` as the beginning. `**.example.com` will not match `example.com`.

## Example
Pattern: `*.example.com` (or `.example.com`)

Matching: `a.example.com`, `a.b.example.com`, `example.com` (See above)

Not matching: `example.test`, `example.com.test`, `anotherexample.com` (Apologies to whoever owns the domain)

## Design goals
Wildcard conditions are the most commonly used conditions. Therefore, they are expected to be fast on [[compiling|PAC generating]] and executing.

[[Wildcard optimization]] should be used for simple wildcards, whenever possible. `*.example.com` could compile to something like `if (host.indexOf('.example.com') == host.length - 12 || host == 'example.com')` to avoid using [[RegExp]].

If optimization is not possible, they should be translated to [[regex]]es on PAC generation. `shExpMatch` calls `new RegExp` internally in Chromium, so this function should not be used at all.