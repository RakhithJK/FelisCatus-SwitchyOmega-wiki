When matching the host name is not sufficient, wildcard matching can be performed on the whole URL.

For matching entire sites, use [[host wildcard condition]]s. For keyword matching on HTTP only, use [[keyword condition]]s. The two new types of conditions should replace most usage of URL wildcard conditions.

## Example
Pattern: `http://www.example.com/*`

Matching: `http://www.example.com/home`, `http://www.example.com/?q=test`

Not matching: `https://www.example.com/home`, `https://www.example.com.test/`

## Design goals
URL wildcard conditions are not so popular as [[host wildcard conditon]]s. But this is not a reason for not optimizing them.

[[Wildcard optimization]] should be used for simple wildcards on [[compiling|PAC generating]], whenever possible.

Most URL wildcards will only include `*`s at the beginning, the end, or both. Focus on translating them to string functions for greater speed.

If optimization is not possible, they should be translated to [[regex]]es on PAC generation. `shExpMatch` calls `new RegExp` internally in Chromium, so this function should not be used at all.