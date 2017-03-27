About the Project
-----------------

### What is SwitchyOmega?

SwitchyOmega is a proxy configuration tool. It allows easy management of multiple proxies and switching between them. Currently, it supports Google Chrome and other Chromium-based browsers.

### Where can I get it?

You can try it on [Chrome Web Store](https://chrome.google.com/webstore/detail/padekgcemlokbadohgkifijomclgjgif),
or grab a packaged extension file for offline installation on the [Releases page](https://github.com/FelisCatus/SwitchyOmega/releases).

### What's the relationship with SwitchySharp, SwitchyPlus and "Proxy Switchy!"?

SwitchyOmega can be considered the 2.x version of SwitchySharp. It provides all the features in SwitchySharp, SwitchyPlus and "Proxy Switchy!" and is compatible with the options of the old version.

Existing users are strongly advised to [update to SwitchyOmega](https://github.com/FelisCatus/SwitchyOmega/wiki/What's-new-in-SwitchyOmega#how-to-upgrade) for the newest fixes and features because the mentioned projects are not maintained any more. SwitchySharp users can automatically upgrade to SwitchyOmega by installing SwitchyOmega from the Chrome Web Store.

The old extensions are still available on Chrome Web Store because we do not want to force anyone to upgrade. Feel free to upgrade to SwitchyOmega if you need [the new features](https://github.com/FelisCatus/SwitchyOmega/wiki/What's-new-in-SwitchyOmega) at any time.

Proxies
-------

### This thing does not come with any free proxies!!!!!!!!1

Yup, that's right. You need your own proxy server for SwitchyOmega to work. SwitchyOmega is only meant to be a tool which you can use to configure your browser. We do not have free proxies for you to try it out because we are not a commercial company.

Nor does SwitchyOmega provide free VPNs or other network services. We do not have any charges or subscriptions. We do not provide support for any proxy server or proxy software. If you see any network provider that claims SwitchyOmega as their partner, please let us know. Because we do not have any partners right now.

### Will SwitchyOmega unblock XYZ, hide my IP address or do other wonderful tricks?

Short answer: No.

Long answer: SwitchyOmega will not magically unblock websites or protect your privacy, unless you instruct it to use a proxy server which does. You should only use trusted proxy servers, because SwitchyOmega can not protect you from bad proxies that inject ads, track you or record your password. And if you don't have a proxy server, you probably won't need SwitchyOmega. Sounds reasonable, right?

### I saw advertisements inserted to websites! OMG, what have you done?!

Please, calm down. SwitchyOmega never inserts any advertisements or makes any changes to any web pages. We have no reason to do that since we are not for profit.

Most of the time, it is the proxy server you are using who does that. Or sometimes, your ISP is the one to blame. SwitchyOmega has no way to prevent those changes.

If you still don't believe me, please take a look at the [source code](https://github.com/FelisCatus/SwitchyOmega).

Switching
---------

### Why can't I select System Proxy in Switch Profiles?

According to PAC limitations, this cannot be implemented in SwitchyOmega.

As a workaround, you can create a profile in SwitchyOmega that does the same thing as your system proxy.

If your system proxy is a fixed proxy server, you can create a Proxy Profile in SwitchyOmega and fill in the same protocol, server and port. The newly created Proxy Profile can be used in Switch Profiles.

If your system proxy is set by your network administrator, there is a high chance that [WPAD](https://en.wikipedia.org/wiki/Web_Proxy_Auto-Discovery_Protocol) is used. Try creating a PAC Profile and fill in the URL `http://wpad/wpad.dat`. Then, hit the update button to see whether a script can be downloaded or not. If so, the newly created PAC Profile can be used in Switch Profiles. If not, please consult your network administrator.

If your proxy is set by another extension, try selecting `[System Proxy]` from SwitchyOmega popup menu and configure the other extension. Then, open SwitchyOmega popup menu again and see whether there is an `(external profile)` entry on it. If so, please click on that entry and give it a name to create a profile accordingly. The newly created Proxy Profile can be used in Switch Profiles. (This only captures the proxy settings at that moment and will automatically update if the proxy dynamically changes.)

### SwitchyOmega conflicts with other extensions. Now what?

SwitchyOmega will conflict with other extensions trying to control the proxy settings. Such conflicts are caused by the design of the Chrome browser and thus cannot be avoided. Please notice some ad-removal extensions may also use proxy settings to do their trick. Check all your installed extensions.

When SwitchyOmega has a higher priority, it can be configured to voluntarily give back the control by selecting the [System Proxy] item in the popup menu. See above on how to capture the proxy settings into SwitchyOmega. Otherwise, you will see a red badge on the SwitchyOmega icon indicating insufficient priority.

Re-installing SwitchyOmega should raise its priority, providing a possible workaround.

### Can you add support for tab-based or window-based switching?

Sorry, no. Tab information is not available to PAC scripts. Since SwitchyOmega uses PAC scripts behind the scene, it also suffers from such limitations.

If you need to use different proxies for different windows, you can [add more persons in Chrome](https://support.google.com/chrome/answer/2364824). Each person can install SwitchyOmega and keep their own settings. This allows you to open one window for each person with different proxy settings.

Networking
----------

### I can't even access the Internet when I enable SwitchyOmega!

There is definitely something wrong with your configuration, your proxy server or your network connection. Here are the things to check.

* Is your proxy server running? If you use a proxy software, make sure to start it as well.
  - If you don't have a proxy server, then you don't need SwitchyOmega.
* Is your network connection working? Try selecting `[Direct Connection]` and visit a webpage.
  - Also, try other network diagnostic tools and methods.
* Did you choose the right profile in the popup menu? You need to choose the one you configure.
* Did you specify the wrong host, port or protocol?
  - Type `chrome://net-internals/#proxy` in the address bar and Enter. See what's there.
  - If it shows the wrong information, fix that in SwitchyOmega options and choose it from the popup menu.
  - If it shows totally different things, see the FAQ about conflicts.
  - Hint: Most of the time the protocol should be HTTP or SOCKS/SOCKS5. HTTPS proxies are pretty rare.
  - Hint: Most of the time you do not need advanced settings. Try only using the `(default)` row.
* If none of above applies, please open an issue with the following information.
  - Screenshot of your Proxy Profile on the options page.
  - Copy & paste or screenshot of `chrome://net-internals/#proxy`.
  - You may change or mask the server address to protect your privacy.
  - What URL are you trying to visit?
  - What is the error code on the error page? It begins with `ERR_`.

### Why can't I use username/password authentication for SOCKS proxies?

SOCKS Authentication is [not implemented in Chrome](https://code.google.com/p/chromium/issues/detail?id=256785) and therefore cannot be done in SwitchyOmega. No Chrome Extension can do that as far as we know.

### Does SwitchyOmega support remote DNS resolution?

Yes, since Chrome always use remote DNS resolution. In fact, there is no way for SwitchyOmega to tell it not to.

If you are using SOCKS5, please be aware of [a potential leak](https://github.com/FelisCatus/SwitchyOmega/wiki/DNS-and-SOCKS-proxy#english). See the linked page for workarounds.

### Can SwitchyOmega support route tables or IP-based/geo-based switching?

No. Proxies do not operate on the IP protocol layer. Route tables will only work with VPNs. As a proxy configuration tool, it is natural that SwitchyOmega cannot provide such support.

User Interface
--------------

### Sometimes the popup window is not the right size / got cut off on the top.

Similar issues include "[Direct]" not being visible (or just a blue bar is visible) and so on.

This seems to be [a known bug in Chromium](https://bugs.chromium.org/p/chromium/issues/detail?id=457887) that only happens on Mac OS X due to the way popups are drawn. This affects all extensions that dynamically resizes the popup. (SwitchyOmega does that because it adds one menu item for each profile you configure.)

There does not seem to be a good way to work around the problem in SwitchyOmega right now.