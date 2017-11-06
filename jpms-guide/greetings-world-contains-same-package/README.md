
## compile

```bash
javac -d mods --module-source-path src $(find src -name "*.java")

```

## describe-module

```
java -p mods --describe-module org.astro
```

Output:

```
exports org.astro
requires java.base mandated
contains com.samepackage
```


## Run

```
java --module-path mods -m com.greetings/com.greetings.Main
```

Output:

```
Error occurred during initialization of boot layer
java.lang.LayerInstantiationException: Package com.samepackage in both module com.greetings and module org.astro
```
