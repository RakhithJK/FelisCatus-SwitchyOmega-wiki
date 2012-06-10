PAC profiles specify [[PAC]] scripts which choose proxy servers programmatically.

# Settings UI
Users can enter the URL to the PAC file, or write/edit raw scripts in a textarea. Scripts can be imported through file upload.

# Function
If the scripts are contained in the profiles, the raw scripts will be sent to the browser. Otherwise, the URLs will be told to the browser, and the browsers will decide when to download them.
However, if a [[result profile]] is a PAC profile, the extension will always try to download the script by the URL.
The scripts will be executed to determine the proxies **every time** a request is made by the browser.

# Inclusion in [[switch profile]]s
If a PAC profile is included in a switch profile, the PAC script is wrapped into the [[generated PAC script|PAC generation]]s, which can cause [[various problems|PAC inclusion problems]].

# Design goals
A PAC profile can be used directly by `mode=pac_script`, and included in a [[switch profile]] as well.
PAC 