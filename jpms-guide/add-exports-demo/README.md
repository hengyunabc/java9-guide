```bash
$ mkdir -p mods/com.demo

$ javac --add-exports java.base/sun.net.www=com.demo -d mods/com.demo \
   src/com.demo/module-info.java \
   src/com.demo/com/demo/Main.java

$ java --add-exports java.base/sun.net.www=com.demo --module-path mods -m com.demo/com.demo.Main
```

如果没有 `--add-exports java.base/sun.net.www=com.demo` 参数，编绎/运行都会报错。

## 参考

* https://docs.oracle.com/javase/9/tools/javac.htm
