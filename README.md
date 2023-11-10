## how to package
jl
First, create a dist folder (totally optional) to put all the jar in, package the jar file with maven with appropriate platform
```shell
mkdir dist
rm -rf dist/*
mvn clean package -Djavafx.platform=mac-aarch64
mv target/PDF*jar dist/
mvn clean package -Djavafx.platform=mac
mv target/PDF*jar dist/
mvn clean package -Djavafx.platform=win
mv target/PDF*jar dist/
mvn clean package -Djavafx.platform=linux
mv target/PDF*jar dist/
```
Then, package the app with jpackage
```
```shell
jpackage --name "PDF Tools" --input ./dist --main-jar YOUR_JAR_NAME_ONLY.jar   --icon FULL_PATH_TO_YOUR_ICON_DIR/icon.icns
```
