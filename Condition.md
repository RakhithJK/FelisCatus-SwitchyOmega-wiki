Conditions decide the [[result profile]]s of [[Switch profile]]s.

The extension goes through all the conditions in their order until it founds a match or all conditions fail.
The profile of the first matched condition will be selected, or the default profile is selected if no condition matches.

_Conditions were called 'patterns' or 'rules' in [[SwitchySharp]]._

# Host conditions
## [[Host wildcard condition]]
Matches when the [[host]] of the [[URL]] matches the [[wildcard]] expression. Fails otherwise.
### Special things
If a wildcard pattern begins with `.` or `*.`, then it matches any subdomain **and the main domain**.
### Example
Pattern: `*.example.com` (or `.example.com`)

Matching: `a.example.com`, `a.b.example.com`, `example.com` (See above)

Not matching: `example.test`, `example.com.test`, `anotherexample.com` (Apologies to whoever owns the domain)

## [[Host regex condition]]
Matches when the [[host]] of the [[URL]] matches the [[regex]]. Fails otherwise.

Regex conditions should not be used when wildcards are okay, because regexes are more difficult to optimize, thus slower.

### Example
This pattern mimics the `localHostOrDomainIs` [[PAC]] function: `^test(.example.com)?$`

Matching: `test`, `test.example.com`

Not matching: `test.example.test`, `test2`, `test2.example.com`

host_regexp (slow, include localHostOrDomainIs)

## [[Host levels condition]]
Matches when the count of `.`(dots) in the host name is within a fixed range.

### Example
If the host level equals `0`, then the domain is an internal domain.
You can use this condition type if all your external traffic should be sent via a proxy.

# URL conditions
## [[URL wildcard condition]]
Matches when the [[URL]] matches the [[wildcard]] expression. Fails otherwise.
### Example
Pattern: `http://www.example.com/*`

Matching: `http://www.example.com/home`, `http://www.example.com/?q=test`

Not matching: `https://www.example.com/home`, `https://www.example.com.test/`

## [[URL regex condition]]
Matches when the [[URL]] matches the [[regex]]. Fails otherwise.

Regex conditions should not be used when wildcards are okay, because regexes are more difficult to optimize, thus slower.

### Example
Pattern: `^https?://\w+\.example\.com/`

Matching: `http://www.example.com/home`, `https://search.example.com/?q=test`

Not matching: `ftp://ftp.example.com/`, `http://example.com/`

## [[Keyword condition]]
A keyword condition matches if the [[URL protocol]] is HTTP, **and** the pattern is an exact sub-string of the URL. (It behaves like the URL wildcard pattern `http://*pattern*`, where `pattern` is the keyword pattern.)

Keyword conditions are useful if you want to avoid [[connection reset]]s by the [[GFW]], by requesting URLs that contain certain keywords through a proxy.

### Example
Pattern: `example.com`

Matching: `http://www.example.com`, `http://search.test/?q=example.com`

Not matching: `https://www.example.com`, `https://search.test/?q=example.com`

# DateTime conditions
## [[Date range condition]]
Matches when the current day of month is within a fixed range.

## [[Time range condition]]
Matches when the current time (in 24hr) is within a fixed range.

## [[Weekday range condition]]
Matches when the current day of week is within a fixed range.

# Special conditions
## [[Always condition]]
As its name suggested, this condition is always matched.

This condition effectively returns the corresponding [[result profile]], and all the following conditions are ignored.

## [[Never condition]]
This condition always fails.

This condition effectively prevents the corresponding [[result profile]] from being selected.