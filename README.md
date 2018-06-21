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

## DB constraint naming convention

Constraint names in changeSet should follow this naming convention: **PrefixForConstraint_TableWithConstraint_ObjectRelatedToConstraint**

List of prefixes:
* fk_ - foreign key
* idx_ - index
* nn_ - not null
* pk_ - primary key
* ck_ - check
* uq_ - unique

For example:
* fk_suitCase_case - prefix, table with foreign key, table with referenced column
* idx_suitCase_id - prefix, table with index, indexed column 

## REST API naming convention

To describe your resources (URIs), use ```concrete names``` and ```not action verbs```. Because the action is described by the HTTP
methods.

For example:
* ```POST```   /cases/{caseId}/tags
* ```GET```    /projects/{projectId}/suits/{suitId}
* ```DELETE``` /projects/{projectId}/user

There are several approaches to separate several words in the endpoint name (CamelCase, snake_case, spinal-case), they all have some
pros and cons, but we have chosen the ```spinal-case``` which uses ```hyphens "-"``` to separate words (since it's highlighted by
RFC3986 and this case is used by Google, PayPal etc.)

For example:
* /step-suggestion
* /admin/jira-settings
* /feature-file

If you still need to write some action in URI, actually the correct choice is to use the query parameters, not write in the endpoint.
But we have some problems with this, since the main tool for displaying our API is the Swagger, which doesn't support the demonstration
of several paths with the same paths, but different parameters. As a result, we decided ```to write the actions in the endpoint```.

For example:
* /jenkins/job/execute
* /user/change-password
* /user/validate-reset-token

## DTO naming convention

EntityName + action + "DTO" where action is one of CRUD operations (Create, Read, Update, Delete).
If action is non-crud operation, try to express action in CRUD way.
i.e. instead of /updateUserRole use /updateUser with new role passed as parameter.

DTO would be named "UserUpdateDTO",
"UserCreateDTO", "UserReadDTO" (UserDeleteDTO might be only necessary
when passing additional parameters i.e. reason).
And for non-crud operations (if any) "UserRefreshDTO"
(action here is as an example Refresh )

## Useful links

* Where to find raw xml code style file: https://raw.githubusercontent.com/TAI-EPAM/TAI-Code-Style/master/intellij-java-tai-style.xml

* Where to find config folder: https://intellij-support.jetbrains.com/hc/en-us/articles/206544519-Directories-used-by-the-IDE-to-store-settings-caches-plugins-and-logs

* Where to read more information about REST API design guidelines: https://blog.restcase.com/5-basic-rest-api-design-guidelines/
