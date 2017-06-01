Warning: As of Chromium 52, the full URLs of the `https://` scheme are [no longer provided to PAC scripts](https://github.com/FelisCatus/SwitchyOmega/wiki/Chromium-Full-URL-Limitation). As a result, **URL wildcard** and **URL regex** conditions may not work properly in SwitchyOmega.

The most powerful and the slowest condition type in [[SwitchyOmega]]. Just do what you want to the [[URL]], if you are a big fan of [[regex]]es.

## Example
Pattern: `^https?://\w+\.example\.com/`

Matching: `http://www.example.com/home`, `https://search.example.com/?q=test`

Not matching: `ftp://ftp.example.com/`, `http://example.com/`

## Design goals
Regexes create `new Regexp(...)` when called, so they are sure to be slow.
Because regexes are too complex, the extension should not try to optimize them.

Regex conditions should not be used when wildcards are okay. 