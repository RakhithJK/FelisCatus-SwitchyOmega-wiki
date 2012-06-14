Host regex conditions are used when [[host wildcard condition]]s are not powerful enough for matching the [[URL]]s.
Though they can make full use of JavaScript [[regex]]es, they are slower.


### Example
This pattern mimics the `localHostOrDomainIs` [[PAC]] function: `^test(.example.com)?$`

Matching: `test`, `test.example.com`

Not matching: `test.example.test`, `test2`, `test2.example.com`

host_regexp (slow, include localHostOrDomainIs)

## Design goals
Regexes create `new Regexp(...)` when called, so they are sure to be slow.
Because regexes are too complex, the extension should not try to optimize them.

Regex conditions should not be used when wildcards are okay. 