## How to compile

First, download [Dart SDK][dartsdk] and install it. The `Makefile`s in this project assume the binaries (including `dart2js` and `pub`) are installed in `~/dart/dart-sdk/bin`.

**TODO(catus)**: Maybe we can use a environment variable for the Dart binary path.

Next, checkout the source code, install the dependencies and compile them.
```bash
git clone https://github.com/FelisCatus/SwitchyOmega.git
cd SwitchyOmega
pub install
make
```
(Note: `pub` is the Dart package manager which can be found in Dart SDK.)

After a successful make, the directory `SwitchyOmega/` can be loaded as an [unpacked extension][unpacked] in Chromium.

## Types of Compilation
There are two kinds of compilation process in this project: `dart2js` and `dwc`.

### dart2js
dart2js compiles Dart code to JavaScript that runs in every modern browser. This step can be omitted if the target browser (e.g. Dartium) has a Dart VM.

dart2js comes with the Dart SDK.

### dwc
This project uses [Dart Web UI][dartwebui], which enables templating, binding and web components in Dart + HTML. `dwc.dart` is a compiler that translates special tags and attributes in HTML to supporting Dart code.

`dwc.dart` takes HTML entry files as input. It reads the Dart scripts referenced in them and generates both HTML and Dart files accordingly. The resulting Dart scripts can be further compiled by `dart2js` to JavaScript.

`dwc.dart` comes with the Dart Web UI package, which should be installed by running `pub install`.

[dartsdk]: http://www.dartlang.org/docs/sdk/
[unpacked]: http://developer.chrome.com/extensions/getstarted.html#unpacked
[dartwebui]: http://www.dartlang.org/articles/web-ui/