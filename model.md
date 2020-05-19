# Model

* Table of contents
{:toc}

## Blocking Validators 
***********************
Those validators need to be fixed manually and the publish can't continue until they are fixed.

##### Validate Mesh Integrity
* <span style="color:red">CAN BLOCK PUBLISH</span>
* severity if test fail: <span style="color:red">error</span>
* validation_is_mandatory: True
* description : Make sure the Mesh has more than 3 vertices, 3 edges and at least 1 face.

##### Validate Scene Object Type
* <span style="color:red">CAN BLOCK PUBLISH</span>
* severity if test fail: <span style="color:red">error</span>
* validation_is_mandatory: True
* description : Make sure the Objects to export are only of those types : 'transform', 'mesh', 'locator', 'nurbsCurve', 'nurbsSurface', 'selectionSet'.

##### Validate Node Naming
* <span style="color:red">CAN BLOCK PUBLISH</span>
* severity if test fail: <span style="color:red">error</span>
* validation_is_mandatory: True
* description : Should start with 'C','R' or 'L' for Center,Right and Left, followed by an underscore.
    The name that follows should always start with an upper case letter.
    If it contains multiple words, just use an upper case letter at the start of every word.
    The name can have somme upper case letter before the "Mesh" suffix.
    Examples: C_PoliceHat_Mesh, R_PoliceHat02_Mesh, C_PoliceHat02_IP_Mesh.


## Non-Blocking Validators To Manually Fix
***********************
Those validators need to be fixed manually, but they won't block the publish.

##### Validate Duplicate Node Name
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: False
* description : The scene shouldn't have nodes with the same name. 


## Auto Fixable Validators
***********************
Those validators won't block the publish, and issues will be fixed on the Farm. It is preferrable to prevent those before the publish. 

##### Validate No Unwanted Attributes
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: True
* Auto Fix On Publish

##### Validate Transform Has Only One Mesh Shape
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: True
* Auto Fix On Publish

##### Validate Transform Unlocked
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: True
* Auto Fix On Publish

##### No Transform Input Connections
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: True
* Auto Fix On Publish

##### Validate Transform Rotate Order
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: True
* Auto Fix On Publish

##### Mesh Names Matches Transform
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: True
* Auto Fix On Publish

##### Mesh Has No Vertex Color
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: True
* description : Test if the mesh has any vertex color (colorSet)
* Auto Fix On Publish

##### Transform Has No Transform
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* Auto Fix On Publish

##### Transform Pivot Is On Origin
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* Auto Fix On Publish

##### Mesh History
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* description : If the mesh has deformer history
* Auto Fix On Publish

#####  Mesh UV Set Name
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* description: UV Set name is "map1"
* Auto Fix On Publish


## Cleanup procedures
**********************
Those steps are really about cleaning up the scene, before we save it as an 'mayaBinary' file under the '/data' folder.

##### ValidateLightRigReference
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* Auto Fix On Publish

##### ValidateImportAllReferences
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* validate function: validate_import_all_references()
* Auto Fix On Publish

##### ValidateTrashGroup
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* validate function: validate_no_trash_group()
* Auto Fix On Publish

##### ValidateUnwantedNodes
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* validate function: validate_no_unwanted_nodes()
* Auto Fix On Publish

##### ValidateUnwantedAlembicNodes
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* validate function: validate_no_unwanted_alembic_nodes()
* Auto Fix On Publish

##### ValidateUnknownPlugins
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* validate function: validate_no_unknown_plugins()
* Auto Fix On Publish

##### ValidateNoUnwantedShaders
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* validate function: validate_no_unwanted_shaders()
* Auto Fix On Publish

##### ValidateDeleteAllButRoot
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* validate function: validate_nothing_but_root()
* Auto Fix On Publish

