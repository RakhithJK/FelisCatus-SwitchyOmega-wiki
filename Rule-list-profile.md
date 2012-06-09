A rule list profile is a list of auto switch [[condition]]s. It is a good way for sharing a lot of conditions with others.
The conditions are described by a rule list, which use special [[rule list format]]s.

# Setting UI
**TODO**(catus)
_Users can input the URL where the rule list can be downloaded and set the update interval. [[Rule list format]]s can be explicitly chosen. However, it can be parsed from the file header in most situations._

# Function
A rule list profile has two user-definable [[result profile]]s. One is selected when at least one condition is met, while the other is selected when all conditions fail, or at least one [[reverse condition]] evaluates to true.

# Inclusion in switch profiles

# Design goal
Rule list profiles should be treated as [[switch profile]]s internally, especially when [[compiled to PAC scripts|PAC generation]]. See [[switch profile]].