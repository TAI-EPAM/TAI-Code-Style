# TAI-Code-Style

## How to set up

Copy ```intellij-java-tai-style.xml``` into your ```config/codestyles``` folder in your IntelliJ settings folder. 

Under ```Settings (Preferences) -> Editor -> Code Style``` open ```Scheme -> Setting Wheel -> Import Scheme -> Intellij IDEA code style XML``` and then select our XML code style file.

Press ```Apply -> OK``` and simply enjoy with a single press of ```Ctrl (Cmd) + Alt + L``` :)

## Package naming convention

* Companies use their reversed Internet domain name to begin their package names.
 For example, ```com.epam.cucumber```.
* Package names are all lowercase, with consecutive words simply concatenated together (no underscores).
 For example, ```com.example.deepspace```, not ```com.example.deepSpace``` or ```com.example.deep_space```.
* Names for packages with homogeneous contents should be plural and with heterogeneous contents
 should be singular.
 For example, a package named ```com.epam.task``` does not mean that each contained class is an instance of
   a task. There might be a ```TaskHandler```, a ```TaskFactory```, etc.
   A package named ```com.epam.tasks```, however, would contain different types that are all tasks:
   ```TakeOutGarbageTask```, ```DoTheDishesTask```.
* The highest level packages in the project should reflect the various application "layers". It is
 called *package-by-layer* style.
  For example, ```com.epam.services```, ```com.epam.dao```, ```com.epam.util```.

## Useful links

* Where to find raw xml code style file: https://raw.githubusercontent.com/TAI-EPAM/TAI-Code-Style/master/intellij-java-tai-style.xml

* Where to find config folder: https://intellij-support.jetbrains.com/hc/en-us/articles/206544519-Directories-used-by-the-IDE-to-store-settings-caches-plugins-and-logs
