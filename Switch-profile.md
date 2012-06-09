A switch profile selects the [[result profile]] with the first [[condition]] match. If no condition is met, the default switch profile is used.

# Setting UI
**TODO**(catus)
_Something similiar to the [[SwitchySharp]] AutoSwitch config tab, but with [[drag sorting]]._

# Function
**TODO**(catus)

# Inclusion in switch profiles
Switch profiles can be included in switch profiles, which allows advanced configuration. However, circular references are prevented.

# Design goal
Switch profiles compile to [[PAC]] scripts.
Included profiles (directly or indirectly) should be tracked for efficiency of the generated code. It also helps to prevent circular references.

**TODO**(catus): More details please. This is **very** important for the whole project.