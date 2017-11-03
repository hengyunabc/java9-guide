
```bash
$ mkdir -p mods/org.astro mods/com.greetings

$ javac -d mods/org.astro \
    src/org.astro/module-info.java src/org.astro/org/astro/World.java

$ javac --module-path mods -d mods/com.greetings \
    src/com.greetings/module-info.java src/com.greetings/com/greetings/Main.java

$ java --module-path mods -m com.greetings/com.greetings.Main
```

Output:

```
Greetings world!
```


## Packaging

```
$ mkdir mlib

$ jar --create --file=mlib/org.astro@1.0.jar \
    --module-version=1.0 -C mods/org.astro .

$ jar --create --file=mlib/com.greetings.jar \
    --main-class=com.greetings.Main -C mods/com.greetings .

$ ls mlib
com.greetings.jar   org.astro@1.0.jar
```

Run:

```
$ java -p mlib -m com.greetings
Greetings world!
```

## Print the module declaration

```
jar --describe-module --file=mlib/org.astro@1.0.jar
```

## Jlink

```
jlink --module-path $JAVA_HOME/jmods:mlib --add-modules com.greetings --launcher start=com.greetings/com.greetings.Main --output greetingsapp
```

Run:

```
cd greetingsapp/bin
cat ./start
./start
```
