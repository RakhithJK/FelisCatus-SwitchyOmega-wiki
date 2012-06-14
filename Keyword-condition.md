A keyword condition matches if the [[URL protocol]] is HTTP, **and** the pattern is an exact sub-string of the URL. (It behaves like the URL wildcard pattern `http://*pattern*`, where `pattern` is the keyword pattern.)

Keyword conditions are useful if you want to avoid [[connection reset]]s by the [[GFW]], by requesting URLs that contain certain keywords through a proxy.

## Example
Pattern: `example.com`

Matching: `http://www.example.com`, `http://search.test/?q=example.com`

Not matching: `https://www.example.com`, `https://search.test/?q=example.com`

## Design goals
Keyword conditions are expected to be used very very frequently in China, _for China is a country of china [citation needed]_.
They can be the largest part of a [[switch profile]] or a [[rule list profile]].

Luckily, they are easy to optimize. First, see whether the protocol is `HTTP`. Then, check whether the keyword is a substring of the [[URL]].