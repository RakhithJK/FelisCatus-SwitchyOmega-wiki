As of Chromium 52, the full URLs of the `https://` scheme are [no longer provided to PAC scripts](https://bugs.chromium.org/p/chromium/issues/detail?id=619097). As a result, **URL wildcard** and **URL regex** conditions may not work properly in SwitchyOmega.

The update is done on Chromium's side and cannot be fixed in SwitchyOmega. Please, do not complain about this on GitHub issue tracker since there is nothing that we can do.

Changes
-------

If your URL wildcard/regex conditions rely on the **path** part of the URL (e.g. `/abc/def` in `https://www.example.com/abc/def`), then those conditions will not work for `https://` URLs. Host wildcard conditions and other conditions still works fine though.

Precisely, when visiting a web page under the URL `https://www.example.com/abc/def`, it is treated as if the path part does not exist at all. The result would be the same as if the URL `https://www.example.com/` is visited.

In some cases, the SwitchOmega extension icon could show wrong colors/tooltips because the icon changing algorithm has not been updated to the new behavior yet and would not agree with the actual proxy used. We are currently looking for a fix for the icon display.

Workarounds
-----------

The first and simplest workaround is avoiding the URL rules altogether. This would ensure everything works as intended. It also silences all related warnings on the SwitchyOmega options page as a bonus.

Some URL conditions may still work if the **path** part is not required. For example, `https://*.example.com/*` would still work well since it does not matter whether the path part is `/abc/def` or simply `/` in this case. Both are covered with the `*` on the end. You can try to modify your conditions in a non-path-sensitive way. Also, keep in mind that plain `http://` (non-secure) URLs still work just like before.

It is [still possible to switch off the new behavior](https://bugs.chromium.org/p/chromium/issues/detail?id=619097#c4) with a command flag or policy. However, the Chromium project wishes to completely remove support for such options in the long term. Also, doing so would expose you to [a security problem](https://bugs.chromium.org/p/chromium/issues/detail?id=593759), which could leak the full address of the URL you are visiting under certain circumstances even if you are using HTTPS. I would recommend against using the method **unless you are fully aware of the consequences and willing to take the risk**.

Also, as a last resort, you may downgrade to Chromium <= 51. Again, **doing so would introduce security problems** as mentioned in the last paragraph. Please also keep in mind that downgrading would void all other security fixes, new features, etc. introduced after Chromium 52, leaving you more vulnerable to hackers.