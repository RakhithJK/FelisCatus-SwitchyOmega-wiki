Conditions decide the [[result profile]]s of [[Switch profile]]s.

The extension goes through all the conditions in their order until it founds a match or all conditions fail.
The profile of the first matched condition will be selected, or the default profile is selected if no condition matches.

_Conditions were called 'patterns' or 'rules' in [[SwitchySharp]]._

# Host conditions
## [[Host wildcard condition]]
Matches when the [[host]] of the [[URL]] matches the [[wildcard]] expression. Fails otherwise.

## [[Host regex condition]]
Matches when the [[host]] of the [[URL]] matches the [[regex]]. Fails otherwise.

## [[Host levels condition]]
Matches when the count of `.`(dots) in the host name is within a fixed range.

# URL conditions
## [[URL wildcard condition]]
Matches when the [[URL]] matches the [[wildcard]] expression. Fails otherwise.

## [[URL regex condition]]
Matches when the [[URL]] matches the [[regex]]. Fails otherwise.

## [[Keyword condition]]
Keyword conditions can be used to match HTTP URLs that contain one or more keywords. Especially useful when dancing with the [[GFW]].

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