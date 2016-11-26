Before adding a new language
----------------------------

**Please make sure the language you are trying to add is one of [the supported locales by Chrome Web Store](https://developer.chrome.com/webstore/i18n?csw=1#localeTable).**

Otherwise, we cannot make SwitchyOmega in available in that language.

For example, the only supported locales under the Chinese family are `zh_CN` (`Chinese (China)`) and `zh_TW` (`Chinese (Taiwan)`). Please do not create `zh`/`zh_HK`/`zh_Hans`/`zh_Hant` translations on Weblate since there is no point doing so.

**特别注意：谷歌应用商店只支持大陆简体中文(zh_CN)和台湾正体中文(zh_TW)两种中文资源。因此，请勿在 Weblate 上创建 `zh`/`zh_HK`/`zh_Hans`/`zh_Hant` 等等本地化内容。**

RTL Support
-----------

Right-to-left locales can be translated without any problem on Weblate. They are also partially supported in SwitchyOmega web interfaces. However, the layouts of options pages, etc. are not fully RTL-compatible. In some strings with mixed English and RTL text, there might be issues that could cause the text to flow in the wrong direction. Please help us to improve SwitchyOmega if you are familiar with RTL languages.

After the translation is finished
---------------------------------

Please [create a new issue](https://github.com/FelisCatus/SwitchyOmega/issues/new) on GitHub and request for publishing SwitchyOmega on Chrome Web Store with that locale enabled. Please note that in order to do so, there could be a few additional paragraphs for description on CWS that needs to be translated besides those on Weblate.

Releasing packaged CRX files (in Releases on GitHub) does not require additional strings. New languages are still manually enabled in the build process upon request though.