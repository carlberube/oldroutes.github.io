# Surface

* Table of contents
{:toc}

## Blocking Validators 
***********************
Those validators need to be fixed manually and the publish can't continue until they are fixed.

##### Each Mesh Has Valid Shaders
* <span style="color:red">CAN BLOCK PUBLISH</span>
* severity if test fail: <span style="color:red">error</span>
* validation_is_mandatory: True
* description : Check whether or not the meshes have a shader assigned, a shader that's not referenced and a shader of those types : 'RedshiftMaterial', 'RedshiftMaterialBlender', 'surfaceShader' and 'RedshiftCarPaint'

##### Each Shape Is Referenced
* <span style="color:red">CAN BLOCK PUBLISH</span>
* severity if test fail: <span style="color:red">error</span>
* validation_is_mandatory: True
* description : Check whether or not all the shapes are referenced (e.g. : they come from a Reference.)

##### Each Shape Has No Local History
* <span style="color:red">CAN BLOCK PUBLISH</span>
* severity if test fail: <span style="color:red">error</span>
* validation_is_mandatory: True
* description : Check whether or not the shapes have Local History. 


## Auto Fixable Validators
***********************
Those validators won't block the publish, and issues will be fixed on the Farm. It is preferrable to prevent those before the publish. 

##### Rstexbin Check
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: True
* description : Check whether or not the RSTexBin file is valid.
* Auto Fix On Publish

##### Variant Sets Are Unchanged
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: True
* description : Make sure the Variant Sets has not been modified. 
* Auto Fix On Publish

##### Shape Has No Reference History
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: False

##### Variant Root Is Child Of World
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: True
* Auto Fix On Publish

##### Mesh Has Valid Shaders Assignation
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: True
* Auto Fix On Publish

##### Mesh Has Valid Shader Name
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: True
* Auto Fix On Publish

##### Tessellation Validator
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: True
* description : Make sure the 'rsEnableSubdivision' attribute is enabled. 
* Auto Fix On Publish


## Cleanup procedures
**********************
Those steps are really about cleaning up the scene, before we save it as an 'mayaBinary' file under the '/data' folder.

##### Root Has Zero Transform
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* Auto Fix On Publish

##### Reference Is Not Moved
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* description : Check whether or not the Reference is moved. For the 'Surface' step, the transforms will be removed. For the 'TurnTable' step, the transforms will be maintained.
* Auto Fix On Publish

##### ValidateCleanExportVariations
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: True
* Auto Fix On Publish

##### ValidateLightRigReference
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* Auto Fix On Publish

##### ValidateImportAllReferences
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* Auto Fix On Publish

##### ValidateGroomingRedshiftProxy
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* Auto Fix On Publish

##### ValidateTrashGroup
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* Auto Fix On Publish

##### ValidateUnwantedNodes
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* Auto Fix On Publish

##### ValidateUnwantedAlembicNodes
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* Auto Fix On Publish

##### ValidateUnknownPlugins
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* Auto Fix On Publish

