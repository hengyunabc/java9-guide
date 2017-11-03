
```bash
$ mkdir -p mods/com.greetings

$ javac -d mods/com.greetings \
   src/com.greetings/module-info.java \
   src/com.greetings/com/greetings/Main.java

$ java --module-path mods -m com.greetings/com.greetings.Main
```
