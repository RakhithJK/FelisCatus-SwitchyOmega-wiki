PAC profiles specify [[PAC]] scripts which choose proxy servers programmatically.

# Setting UI
**TODO**(catus)

# Function
**TODO**(catus)

# Inclusion in [[switch profile]]s
If a PAC profile is included in a switch profile, the PAC script is written into [[generated PAC script|PAC generation]]s, which can cause [[various problems|PAC inclusion problems]].

# Design goal
A PAC profile can be used directly by `mode=pac_script`, and included in a [[switch profile]] as well.
