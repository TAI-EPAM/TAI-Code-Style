# TAI-Code-Style

## How to set up

Copy ```intellij-java-tai-style.xml``` into your ```config/codestyles``` folder in your IntelliJ settings folder. 

Under ```Settings (Preferences) -> Editor -> Code Style``` open ```Scheme -> Setting Wheel -> Import Scheme -> Intellij IDEA code style XML``` and then select our XML code style file.

Press ```Apply -> OK``` and simply enjoy with a single press of ```Ctrl (Cmd) + Alt + L``` :)

## Tests naming convention

Test method names should follow this naming convention: **MethodName_StateUnderTest_ExpectedBehavior**

For example:
* login_CorrectCredentials_StatusOk
* login_IncorrectEmail_StatusBadRequest
* save_SimpleCase_Saved
* delete_SimpleStep_Deleted
* getSuit_SimpleSuit_ReturnExpectedSuitDTO
* getSuit_NullSuit_NotFoundException
* visit_CommonWebElementGroupWithWrongValue_Invalid
* visit_ComplexWebElementGroupWithOneUniquenessValue_Valid

## Useful links

* Where to find raw xml code style file: https://raw.githubusercontent.com/TAI-EPAM/TAI-Code-Style/master/intellij-java-tai-style.xml

* Where to find config folder: https://intellij-support.jetbrains.com/hc/en-us/articles/206544519-Directories-used-by-the-IDE-to-store-settings-caches-plugins-and-logs

