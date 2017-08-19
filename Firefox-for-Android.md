## English

SwitchyOmega supports **Firefox for Android [Nightly build](https://www.mozilla.org/en-US/firefox/android/nightly/all/) >= 57.1a ONLY!!** Alternatively, get the [Firefox Nightly on Google Play Store](https://play.google.com/store/apps/details?id=org.mozilla.fennec_aurora). Please don't even try with earlier builds.

Once you have Nightly, please install SwitchyOmega from [Mozilla Add-Ons](https://addons.mozilla.org/en-US/firefox/addon/switchyomega/).

The `chrome.browserAction` API is [not fully supported](https://bugzilla.mozilla.org/show_bug.cgi?id=1330159) in Firefox for Android right now. Specifically, popup is [not implemented](https://bugzilla.mozilla.org/show_bug.cgi?id=1387026).

To open the popup, please select the `Omega: ...` Item in the menu and it will open popup as a tab. The menu item is shown in the hamburger menu, on the very bottom, with [NO ICON](https://bugzilla.mozilla.org/show_bug.cgi?id=1370303) associated. There is no way to close the popup so the page just reloads when you select something.

As for the good news, the switching part and proxy settings actually work. Once the proxy has been selected via the popup, you can visit a website to confirm. You will probably need to refresh the page manually.

SwitchyOmega also tries to show you the actual profile used for each tab when you use auto switch, but such changes are not reflected immediately upon navigation (probably due to some menu caching). For now, please just switch to another tab and switch back to see the updated text.

### Debugging on Firefox for Android

To get the error log, please open the options page by clicking on the menu item, click on SwitchyOmega link on the very top, and then click on the `Save error log` button. Thanks!

To debug, please enable `Debugging over WiFi` 
(or USB if you prefer) in `Menu > Settings > Advanced > Developer tools`. Then, open `Menu > Web developer > WebIDE` on your desktop Firefox Nightly and click on your device. You can type `localStorage.log` in the console to get the error log if the options page won't work.

## 中文

SwitchyOmega **只支持 [Firefox for Android Nightly build](https://www.mozilla.org/en-US/firefox/android/nightly/all/) >= 57.1a !!** 您也可以 [在 Google Play 上下载 Firefox Nightly](https://play.google.com/store/apps/details?id=org.mozilla.fennec_aurora). 请不要尝试更旧的版本。

安装了 Nightly 以后，请从 [Mozilla Add-Ons](https://addons.mozilla.org/en-US/firefox/addon/switchyomega/) 安装 SwitchyOmega.

目前 `chrome.browserAction` API is [还未被 Firefox for Android 完全支持](https://bugzilla.mozilla.org/show_bug.cgi?id=1330159). 尤其是，弹出窗口的功能 [没有实现](https://bugzilla.mozilla.org/show_bug.cgi?id=1387026).

要打开弹出菜单，请在主菜单中选择 `Omega: ...` 那一项。主菜单是汉堡样式的菜单， Omega 那项在最底部，[没有图标](https://bugzilla.mozilla.org/show_bug.cgi?id=1370303). 点击后会在一个新标签页中显示弹出菜单。由于弹出菜单关不掉，所以选择后，只会刷新下页面。

好消息是，切换和代理设置功能等可以正常工作。在弹出菜单中选择代理后，可以访问其他网站来确认。您可能需要手动刷新网页。

如果您使用自动切换， SwitchyOmega 会尝试在每个标签页显示实际使用的情景模式，但标签的更新似乎有缓存，所以可以试试看切换到其他标签，然后再切换回来，再观察菜单中 `Omega: ...` 中显示的文字。

### 在 Firefox for Android 上调试

要获取错误日志，请点击汉堡菜单中的 `Omega: ...` 项，然后选择打开选项页，然后点击最上方的 SwitchyOmega 字样的链接。之后，点击`保存错误日志`按钮即可。

要调试，请在 `Menu > Settings > Advanced > Developer tools` 中启用 `Debugging over WiFi`. 之后，在桌面版的 Firefox Nightly 上打开 `Menu > Web developer > WebIDE` 然后选择您的设备。如果上述导出错误日志的方式不能用，您可以在控制台中输入 `localStorage.log` 来获取错误日志。