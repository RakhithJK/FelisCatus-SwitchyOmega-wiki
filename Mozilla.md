English
-------

This project is being ported to Mozilla WebExtensions platform, which allows installing in Firefox.

***Warning: Firefox support is highly experimental!***

To test, please build the project under branch `feature/webextension`. Then use Firefox's Debugging Tools to `Load Temporary Add-on` with `omega-target-chromium-extension/build/manifest.json`.

Packed extension does not work yet.

<!--
To test, please install the latest build from https://addons.mozilla.org/en-US/firefox/addon/switchyomega/
-->

***Firefox Nightly build with version number >= 55 required! Otherwise it won't work!**

### Known Issues

1. `HTTP` proxies are wrongly treated as `HTTPS` proxies.
  * This is a known bug in Mozilla: https://bugzilla.mozilla.org/show_bug.cgi?id=1359417
  * There is no workaround right now. So your HTTP proxies probably won't work.
1. PAC Profiles are not working either applied directly or through Switch Profiles.
  * For requests that ends up switched to PAC Profiles, an error is raised and direct connection is used instead.
1. Options syncing is disabled by default behind a Firefox flag and has not been tested yet.
  * You may enable syncing in flags if you want, but please do report any issues you encounter.

NOTE: In case of other issues, please right click on the extension icon and select "Report Issue" from the menu so that I can locate and fix the issue more quickly.

中文
---

此项目正在迁移到 Mozilla WebExtensions 平台，目前已经支持在 Firefox 中安装.

***注意！ Firefox 支持目前还处于早期实验阶段！***

要进行测试, 请编译 `feature/webextension` 分支下的项目. 然后使用 Firefox 的 Debugging Tools 中的 `Load Temporary Add-on`，选择 `omega-target-chromium-extension/build/manifest.json`.

<!--
要进行测试，请在这里安装最新的版本： https://addons.mozilla.org/en-US/firefox/addon/switchyomega/
-->

***必须使用 Firefox Nightly 版本大于 55 方可安装！否则根本无法运行！**

### 已知问题

1. `HTTP` 代理服务器会被错误地当成 `HTTPS` 代理服务器处理。
  * 这是 Mozilla 的已知问题: https://bugzilla.mozilla.org/show_bug.cgi?id=1359417
  * 目前没有可以绕过这个的办法，所以您的 `HTTP` 代理应该没办法正常工作。
1. PAC 情景模式无法使用。无论是单独使用 PAC 情景模式还是自动切换中使用都不能工作。
  * 如果某个请求切换到了 PAC 情景模式，会出错，然后那个请求会变成使用直接连接。
1. 选项同步默认无法使用，因为同步存储在 Firefox 的 flags 中默认禁用。此功能未经过测试！
  * 您可以自行在 flags 中启用，但遇到问题请及时反馈。

注：如您遇到了其他问题，请使用图标右键菜单的“反馈问题”功能提交错误报告，以便开发者及时修复，谢谢。