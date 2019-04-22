# hello-jlink
Code from here:
https://openjdk.java.net/projects/jigsaw/quick-start
with tiny changes, and help from
https://stackoverflow.com/questions/46413299/how-do-i-run-images-generated-by-jdk-9-jlink

to compile:
`javac -d mods/greet src/greet/module-info.java src/greet/uk/co/littlestickyleaves/Main.java`

to run:
`java --module-path mods -m greet/uk.co.littlestickyleaves.Main`

to run jlink:
`jlink --module-path %JAVA_HOME%/jmods;mods/greet --add-modules greet --output greetingsapp`
(delete the directory `greetingsapp` if it already exists)

to run the custom JRE made by jlink, go to the `greetingsapp/bin` folder and run:
`java -p mods -m greet/uk.co.littlestickyleaves.Main`

