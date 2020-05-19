# SetDressing

* Table of contents
{:toc}


## Blocking Validators 
***********************
Those validators need to be fixed manually and the publish can't continue until they are fixed.

##### Reference Is Valid
* <span style="color:red">CAN BLOCK PUBLISH</span>
* severity if test fail: <span style="color:red">error</span>
* validation_is_mandatory: True
* description : Make sure the Reference is / are valid. A Valid Reference is one that was imported correctly through the Shotgun Loader or built by the tools. 


## Non-Blocking Validators To Manually Fix
***********************
Those validators need to be fixed manually, but they won't block the publish.

##### Only Valid Nodes Under Root
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: False
* description : the SCENE_ROOT can contain any transfom (not referenced) and references.

##### Base Groups Validator
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: False
* description : Make sure the basic groups exist : 'All_Grp', 'Render_Grp', 'TexturesShading_Grp', 'RiggingSimulation_Grp', 'Blendshapes_Grp', 'TRASH'

##### Reference Namespace Content
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: False
* description : Test if any namespace comming from a reference contain a node that doesn't belong to a reference

##### Validate No Local Namespace
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: False
* description : Test if the scene contains namespaces not comming from a reference (a local namespace)


## Auto Fixable Validators
***********************
Those validators won't block the publish, and issues will be fixed on the Farm. It is preferrable to prevent those before the publish. 

##### No Transform On Groups
* severity if test fail: <span style="color:orange">warning</span>
* validation_is_mandatory: True
* Auto Fix On Publish


## Cleanup procedures
**********************
Those steps are really about cleaning up the scene, before we save it as an 'mayaBinary' file under the '/data' folder.

##### ValidateLightRigReference
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

##### ValidateUnknownPlugins
* severity if test fail: <span style="color:blue">info</span>
* validation_is_mandatory: False
* Auto Fix On Publish

