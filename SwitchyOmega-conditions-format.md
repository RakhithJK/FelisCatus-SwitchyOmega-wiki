Example
-------

```ini
[SwitchyOmega Conditions]
; A line starting with semi-colon is a comment line, ignored by the parser.
; When you edit rules using the table-based visual editor in SwitchyOmega options page, the original
; formatting, including the comments, is NOT preserved.

; If you want to stick a note associated with the rule, use a @rule directive above each rule.
; Such notes will be picked up by the visual editor and re-emitted when you publish in text format.
@note This is a HostWildcardCondition matching *.example.com.
*.example.com

; This is a UrlWildcardCondition.
UrlWildcard: https://*.google.com/*

; You can also write UW for short, representing the same UrlWildcardCondition.
UW: https://*.google.com/*

; This is a UrlRegexCondition. Most types of conditions can be represented with :ConditionType pattern
UrlRegex: ^https://www\.example\.(net|org)/

; Conditions can be prefixed with ! to make it exclusive. Any requests matching an exclusive condition will
; use the "default profile" instead of "match profile".
@note Use the default profile for internal stuff at my company
!*.internal.example.org

; Conditions are matched against the request in top-down order.
; The process stops as soon as the first matching condition is applied.

; If no other condition matches, the "default profile" will be used.
```

Design goal
-----------

* Allow ANY condition of ANY type to be represented in the rule list.
* Strict, sequential matching order from top to bottom, just as in Switch Profile.
* Optionally, allow result profiles to be attached to the rule list.

Result profile
--------------

If the rule list contains the `@with result` directive, the name of result profile is appended to every condition. Example:

```ini
[SwitchyOmega Conditions]
; The following line triggers the "result profile" mode.
@with result

; When this condition matches, the profile "ABC" will be used.
@note Use ABC Profile for example.com
*.example.com +ABC

; When this condition matches, the profile "DEF" will be used.
@note DEF is my preferred profile for Google
UrlWildcard: https://*.google.com/* +DEF

; Exclusive conditions still DO NOT have profile names.
!*.example.org

; The rule list MUST contain a catch-all "*" condition at last.
* +GHI
```

Note: The plus "+" sign is only for separating profile names with the condition pattern. It is not part of the profile name.

Additionally, the following changes apply when results are enabled:

* The rule list MUST contain a catch-all "*" condition at last, whose result profile is called the default profile.
* The result of normal conditions is the result profile attached to it.
* The result of exclusive conditions is the "Default profile" in the catch-all rule.
  * ... which means exclusive conditions DO NOT have profile names appended to them.

Abbreviations
-------------

Condition types in the rule list can be abbreviated for short. The following abbreviations are recognized (regardless of case):

* TrueCondition
  * True
* FalseCondition
  * False
  * Disabled
* UrlRegexCondition
  * UR
  * URegex
  * UrlR
  * UrlRegex
* UrlWildcardCondition
  * U
  * UW
  * Url
  * UrlW
  * UWild
  * UWildcard
  * UrlWild
  * UrlWildcard
* HostRegexCondition
  * R
  * HR
  * Regex
  * HostR
  * HRegex
  * HostRegex
* HostWildcardCondition
  * (just write the pattern with no prefix)
  * H
  * W
  * HW
  * Wild
  * Wildcard
  * Host
  * HostW
  * HWild
  * HWildcard
  * HostWild
  * HostWildcard
* BypassCondition
  * B
  * Bypass
* KeywordCondition
  * K
  * KW
  * Keyword
* IpCondition
  * Ip
* HostLevelsCondition
  * Lv
  * Level
  * Levels
  * HL
  * HLv
  * HLevel
  * HLevels
  * HostL
  * HostLv
  * HostLevel
  * HostLevels
* WeekdayCondition
  * WD
  * Week
  * Day
  * Weekday
* TimeCondition
  * T
  * Time
  * Hour
