Compiling wildcards to JavaScript can be [several times faster][performance] than using the built-in `shExpMatch`, which uses `RegExp` internally.

However, compiled JavaScript is longer and more difficult to read.

[performance]: http://jsperf.com/shexpcompile/3