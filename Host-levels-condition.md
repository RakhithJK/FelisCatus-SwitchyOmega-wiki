Host level conditions count the dots (`.`) in the host name.
They are fast, but nearly useless.

## Example
If the host level equals `0`, then the domain is an internal domain.
You can use this condition type if all your external traffic should be sent via a proxy.

## Design goals
Because few people want to to use them, and they can't be slow, we should not put too much effort on it. Use `dnsDomainLevels`, and don't forget to re-implement it.