

```
$ mkdir mods
$ javac -d mods --module-source-path src $(find src -name "*.java")

$ java -p mods -m com.greetings/com.greetings.Main
```

Output:

```
class org.fastsocket.FastNetworkSocket
```
