English
-------

When using SOCKS proxy with Chromium, some DNS requests may go NOT through the proxy. This is caused by DNS prefetching. Quote from the Chromium browser proxy info page:

>     Note that some traffic such as DNS prefetching will NOT go through the proxy
>     server. To prevent the browser from doing local DNS resolves try adding this
>     command line flag:

>     --host-resolver-rules="MAP * ~NOTFOUND , EXCLUDE 127.0.0.1"

To prevent DNS leaking, you may use the command line flag as described above, **with `127.0.0.1` replaced with the IP address of your proxy host**. Or you can disable DNS prefetching completely by **unchecking** the following option in your Chromium settings (under "Show advanced settings..."):

    [ ] Predict network actions to improve page load performance

Note: This topic is completely unrelated with this project, but the wiki page is kept here for reference.

中文
----

在 Chromium 浏览器（以及基于 Chromium 的所有浏览器）中使用 SOCKS 代理时，部分 DNS 请求不会经过服务器发送。这是由 DNS 预加载造成的。以下引用 Chromium 浏览器代理信息页面的文字：

>     Note that some traffic such as DNS prefetching will NOT go through the proxy
>     server. To prevent the browser from doing local DNS resolves try adding this
>     command line flag:

>     --host-resolver-rules="MAP * ~NOTFOUND , EXCLUDE 127.0.0.1"

要防止DNS请求泄露，请使用以上命令行参数（**请将 `127.0.0.1` 替换成您使用的代理主机地址**）。或者您也可以在Chromium选项中完全禁止DNS预加载。请在选项的"Show advanced settings..."下方**取消选择**此选项：

    [ ] Predict network actions to improve page load performance

提示：此主题与本项目完全无关。但请保留此wiki页面以供作为参考。