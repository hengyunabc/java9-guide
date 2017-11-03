
```
$ mkdir -p mods/org.astro mods/com.greetings

$ javac -d mods/org.astro \
    src/org.astro/module-info.java src/org.astro/org/astro/World.java

$ javac --module-path mods -d mods/com.greetings \
    src/com.greetings/module-info.java src/com.greetings/com/greetings/Main.java

```

报错信息：

```
src/com.greetings/com/greetings/Main.java:2: 错误: 程序包 org.astro 不可见
import org.astro.World;
          ^
  (程序包 org.astro 已在模块 org.astro 中声明, 但模块 com.greetings 未读取它)
1 个错误
```
