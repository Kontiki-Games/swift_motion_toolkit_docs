#Welcome to Swift Motion Toolkit Manual

##Overview

*Swift Motion Toolkit* is a set of character animation tools that integrates functions such as mo-cap resource import, animation retargeting, and Root Motion processing, etc. At the same time, it also supports retargeting AnimSequence assets between different characters. 

##Features

* Import mo-cap animation in BVH format and provide a preview.
* Retarget mo-cap animation to AnimSequence asset. 
* Retarget mo-cap animation to AnimSequence asset. 
* Supports more precise restoration of the position of end joints using IK.Supports more precise restoration of the position of end joints using IK.
* Supports synchronizing animation to IK bones.v
* Supports baking vertical or (and) horizontal root displacements into animations.
* Support for selectively preserving root rotation.
* Support for converting animations with root motion to in-place animations. 

##Showcase

<iframe width="560" height="315" src="https://www.youtube.com/embed/_p9ttnPKMYI" frameborder="0" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/dRPSrGvM67U" frameborder="0" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/ZWKmjRFj-kE" frameborder="0" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/TycKnmd63KM" frameborder="0" allowfullscreen></iframe>



##Vedio Tutorial
<span id="video-tutorials"></span>

###01 How to import mocap data to Unreal Engine via Swift Motion Toolkit

<iframe width="560" height="315" src="https://www.youtube.com/embed/OiT2JbPOm5s" frameborder="0" allowfullscreen></iframe>

###02 How to create and set motion hierarchy
<iframe width="560" height="315" src="https://www.youtube.com/embed/oA1L-Ih0WnE" frameborder="0" allowfullscreen></iframe>

###03 How to adjust retarget base pose for motion hierarchy
<iframe width="560" height="315" src="https://www.youtube.com/embed/M9h-d7t1A3s" frameborder="0" allowfullscreen></iframe>

###04 How to create skeleton hierarchy and reteragetable assets
<iframe width="560" height="315" src="https://www.youtube.com/embed/bJhmeuPyD9k" frameborder="0" allowfullscreen></iframe>

###05 How to adjust retarget base pose 4 skeleton hierarchy
<iframe width="560" height="315" src="https://www.youtube.com/embed/MRFKUsXDwgM" frameborder="0" allowfullscreen></iframe>

###06 How to setup skeletn hierarchy retargetable joint chain
<iframe width="560" height="315" src="https://www.youtube.com/embed/PZ1GuBCYymU" frameborder="0" allowfullscreen></iframe>

###07 How to create and preview retargeter.
<iframe width="560" height="315" src="https://www.youtube.com/embed/xmt8KIhfWbA" frameborder="0" allowfullscreen></iframe>

###08 How to solve problems via IK
<iframe width="560" height="315" src="https://www.youtube.com/embed/Q3eQNZE9eJw" frameborder="0" allowfullscreen></iframe>

###09 How to solve problem result from IK
<iframe width="560" height="315" src="https://www.youtube.com/embed/XorognIRzGM" frameborder="0" allowfullscreen></iframe>

###10 Retarget mocap to manny
<iframe width="560" height="315" src="https://www.youtube.com/embed/WbsVyfDHA3M" frameborder="0" allowfullscreen></iframe>

###11 Retarget between AnimSequence assets
<iframe width="560" height="315" src="https://www.youtube.com/embed/CsU8S36i52Y" frameborder="0" allowfullscreen></iframe>

##Related assets
###Motion Hierarchy
<span id="motion-hierarchy"></span>
*Motion Hierarchy* asset contains the skeleton hierarchy used in mo-cap animation and a retarget base pose.
    

###Motion Data
<span id="motion-data"></span>
*Motion Data* contains a series of pose data related to time in mo-cap animations. And hold a reference to a Motion Hierarchy asset. This Motion Hierarchy asset can explain the hierarchy of each pose in Motion Data. 

###Motion Hierarchy Retargetable
<span id="motion-skeleton-hierarchy"></span>
*Motion Hierarchy Retargetable* holds a reference to a *Motion Hierarchy* asset. This asset allows users to define several bone chains for action retarget, and allows users to define new retarget base poses (if the retarget base pose is not defined in *Motion Hierarchy Retargetable*, the retarget base pose in *Motion Hierarchy* will be used). 

###Skeleton Hierarchy
<span id="skeleton-hierarchy"></span>
*Skeleton Hierarchy* holds a reference to a *USkeleton* asset. This asset allows users to define a new retarget base pose (if the retarget base pose is not defined in *Skeleton Hierarchy*, the retarget base pose in *USkeleton* will be used). 

###Skeleton Hierarchy Retargetable
<span id="skeleton-hierarchy-retargetable"></span>
*Skeleton Hierarchy Retargetable* holds a reference to a Skeleton Hierarchy * asset. This asset allows users to define several bone chains for action retarget, and a new retarget base pose (if the retarget base pose is not defined in *Skeleton Hierarchy Retargetable*, the retarget base pose in *Skeleton Hierarchy* will be used). 

###Motion to AnimSeq Retargeter
<span id="motion-to-animseq-retargeter"></span>
*Motion to AnimSeq Retargeter* holds a pair of *Hierarchy Retargetable* as the source and target for retarget. This asset allows users to configure the bone chain mapping tables of the source and target, as well as FK, IK, and Root Motion. And provide a preview and export of the retarget results. 


##Editor


###Motion Hierarchy Editor
<span id="motion-hierarchy-editor"></span>
Support preview and editing of Motion Hierarchy. 

![motion_hierarchy_editor_overview](img/motion_hierarchy_editor_overview.png)

####1. Hierarchy Tree Tab

![motion_hierarchy_tree_tab](img/motion_hierarchy_tree_tab.png)

####2. Asset Details

![motion_data_editor_overview](img/motion_date_editor_asset_details.png)

Property | Description
------------ | -------------
Left Joint Identification List| Left Joint Identification List 
Flag| The identifier in the joint name
Type| Identification type: 1. Prefix 2. Suffix 3. Contain 
Left Joint Display Color | The color displayed for the left joint
Right Joint Identification List| Right Joint Identification List
Flag| The identifier in the joint name
Type| Identification type: 1. Prefix 2. Suffix 3. Contain 
Right Joint Display Color | The color displayed for the right joint
Other Joint Display Color | The color displayed for other joints

(Note: Multiple elements are allowed in the identification list. If the joint name meets any of these conditions, it is judged as 'TRUE'.)

####3. Viewport Tab

![hierarchy_viewport_details_tab](img/hierarchy_viewport_details_tab.png)

####4. Details Tab

![edit_retarget_base_pose](img/motion_details.png)

####5. Retarget Base Pose Tab

![edit_retarget_base_pose](img/edit_retarget_base_pose.png)

Control | Description
------------ | -------------
Use Current Pose | Write the pose in the viewport to *Retarget Base Pose* 
Restore to Base Pose | Restore *Retarget Base Pose* to a viewport
Reset Pose | Write the reference pose to *Target Base Pose*



###Motion Data Editor
<span id="motion-data-editor"></span>
    Support preview of Motion Data.
    
![motion_data_editor_overview](img/motion_data_editor_overview.png)


####1. Hierarchy Tree Tab

![motion_hierarchy_tree_tab](img/motion_hierarchy_tree_tab.png)

####2. Asset Details Tab

![motion_hierarchy_retargetable_asset_details_tab](img/motion_data_asset_details_tab.png)

####3. Viewport Tab

![motion_hierarchy_viewport_details_tab](img/motion_viewport_details_tab.png)

####4. Player Controller Tab

![player_controller_tab](img/player_controller_tab.png)

Zoom can be done through the scroll wheel
![motion_data_player_controller_zoom](img/motion_data_player_controller_zoom.gif)

Right click drag to pan the timeline left and right
![motion_data_player_controller_pan](img/motion_data_player_controller_pan.gif)

####5. Details Tab

![edit_retarget_base_pose](img/motion_details.png)

####6. Motion Data Browser Tab

![motion_data_browser](img/motion_data_browser.png)



###Motion Hierarchy Retargetable Editor
<span id="motion-hierarchy-retargetable-editor"></span>
    Support preview and editing of Motion Hierarchy Retargetable. 
    
![motion_hierarchy_retargetable_overview](img/motion_hierarchy_retargetable_overview.png)

####1. Hierarchy Tree Tab

![motion_hierarchy_tree_tab](img/motion_hierarchy_tree_tab.png)

####2. Asset Details Tab

![motion_hierarchy_retargetable_asset_details_tab](img/motion_hierarchy_retargetable_asset_details_tab.png)

####3. Viewport Tab

![motion_hierarchy_viewport_details_tab](img/motion_hierarchy_viewport_details_tab.png)

####4. Details Tab

![edit_retarget_base_pose](img/motion_details.png)

####5. Edit Retarget Base Pose Tab

![edit_retarget_base_pose](img/edit_retarget_base_pose.png)

Control | Description
------------ | -------------
Use Current Pose | Write the pose in the viewport to *Retarget Base Pose* 
Restore to Base Pose | Restore *Retarget Base Pose* to a viewport
Reset Pose | Write the reference pose to *Target Base Pose*

####6. Retarget Chains Tab

![chain_settings](img/chain_settings.png)

Allow copy and paste

![retarget_chain_copy_paste.gif](img/retarget_chain_copy_paste.gif)



###Skeleton Hierarchy Editor
<span id="skeleton-hierarchy-editor"></span>
    Supports preview and editing of Skeleton Hierarchy.
![skeleton_hierarchy_retargetable_editor_overview](img/skeleton_hierarchy_editor_overview.png)

####1. Hierarchy Tree Tab

![skeleton_hierarchy_tree_tab](img/skeleton_hierarchy_tree_tab.png)

####2. Asset Details

![motion_data_editor_overview](img/motion_date_editor_asset_details.png)

Property | Description
------------ | -------------
Left Joint Identification List| Left Joint Identification List 
Flag| Left Joint Identification List 
Type| Identification type: 1. Prefix 2. Suffix 3. Contain 
Left Joint Display Color | The color displayed for the left joint
Right Joint Identification List| Right Joint Identification List
Flag| The identifier in the joint name
Type| Identification type: 1. Prefix 2. Suffix 3. Contain 
Right Joint Display Color | The color displayed for the right joint
Other Joint Display Color | The color displayed for other joints

(Note: Multiple elements are allowed in the identification list. If the joint name meets any of these conditions, it is judged as 'TRUE'.)

####3. Viewport Tab

![skeleton_hierarchy_viewport_details_tab](img/skeleton_hierarchy_viewport_details_tab.png)

####4. Details Tab

![skeleton_hierarchy_details](img/skeleton_hierarchy_details.png)

####5. Retarget Base Pose Tab

![edit_retarget_base_pose](img/edit_retarget_base_pose.png)

Control | Description
------------ | -------------
Use Current Pose | Write the pose in the viewport to *Retarget Base Pose* 
Restore to Base Pose | Restore *Retarget Base Pose* to a viewport
Reset Pose | Write the reference pose to *Target Base Pose*



###Skeleton Hierarchy Retargetable Editor
<span id="skeleton-hierarchy-retargetable-editor"></span>
    Support for preview and editing of Skeleton Hierarchy Retargetable.
![skeleton_hierarchy_retargetable_editor_overview](img/skeleton_hierarchy_retargetable_editor_overview.png)


####1. Hierarchy Tree Tab

![skeleton_hierarchy_tree_tab](img/skeleton_hierarchy_tree_tab.png)



####2. Asset Details Tab

![skeleton_hierarchy_retargetable_asset_details_tab](img/skeleton_hierarchy_retargetable_asset_details_tab.png)


####3. IK Settings Tab

![skeleton_hierarchy_retargetable_ik_settings_tab](img/skeleton_hierarchy_retargetable_ik_settings_tab.png)

Control | Control | Description
------------ | ------------ | -------------
1 | Add New Solver | Add New Solver 
2 | Check box | Enable/Disable solver
3 | Trash can icon button | Delete corresponding solver

(Note: Select any solver , and its configuration interface will be displayed in the Details tab.)


####4. Viewport Tab

![skeleton_hierarchy_retargetable_viewport_tab](img/skeleton_hierarchy_retargetable_viewport_tab.png)

####5. Details Tab

![skeleton_hierarchy_retargetable_details](img/skeleton_hierarchy_retargetable_details.png)

Property | Description
------------ | -------------
Use Pole Vector| Whether to use pole vector 
Pole Vector| Pole Vector 
Target Alpha| Target application level 
Target Alpha| Target tolerance amount
Tip Bone Keep Local Rot| Whether the end node keeps the rotation of the Local space after applying IK, or keeps the rotation of the Global space before applying IK
Joint Chain Name| Bone chain name 

####6. Edit Retarget Base Pose Tab

![edit_retarget_base_pose](img/edit_retarget_base_pose.png)


Control | Description
------------ | -------------
Use Current Pose | Write the pose in the viewport to *Retarget Base Pose* 
Restore to Base Pose | Restore *Retarget Base Pose* to a viewport
Reset Pose | Write the reference pose to *Target Base Pose*


####7. Retarget Chains Tab

![skeleton_hierarchy_retargetable_chain_settings](img/skeleton_hierarchy_retargetable_chain_settings.png)

Allow copy and paste

![retarget_chain_copy_paste.gif](img/retarget_chain_copy_paste.gif)


###Motion to AnimSeq Retargeter Editor
<span id="motion-to-animseq-retargeter-editor"></span>
    Supports retarget settings between source and target and preview of results.
![motion_to_animseq_retargeter_editor_overview](img/motion_to_animseq_retargeter_editor_overview.png)

####1. Hierarchy Tree Tab

![skeleton_hierarchy_tree_tab](img/skeleton_hierarchy_tree_tab.png)

####2. Asset Details Tab

![motion_to_animseq_retargeter_asset_details_tab](img/motion_to_animseq_retargeter_asset_details_tab.png)

Property | Description
------------ | -------------
Source| Source Retargetable 
Target| Target Retargetable 
Horizontal Root Offset Scale| Root offset scaling in the horizontal direction 
Verticle Root Offset Scale| Root offset scaling in the vertical direction
Convert Motion To Root Bone| Set motion to root bone
Bake Root Rotation in Animation| Bake the rotation of the root node to the animation
Keep Root Rotation Around Up Only| Keep Root only around the rotation in the upward direction
Bake Root Verticle Translation in Animation| Bake the vertical displacement of the root node to the animation 
Bake Horizontal Translation in Animation| Bake the horizontal displacement of the root node to the animation 
Convert to In Place Animation| Whether to convert to in-place animation 
IKCorrection Enalbe| Whether to enable IK 

####3. Source Viewport Tab & Target_Viewport Tab

![motion_to_animseq_retargeter_src_target_viewport_tab](img/motion_to_animseq_retargeter_src_target_viewport_tab.gif)

####4. Player Controller Tab

![player_controller_tab](img/player_controller_tab.png)

Zoom with scroll wheel
![motion_data_player_controller_zoom](img/motion_data_player_controller_zoom.gif)

Right-click and drag to pan the timeline left and right
![motion_data_player_controller_pan](img/motion_data_player_controller_pan.gif)

####5. Details Tab

![motion_to_animseq_retargeter_details](img/motion_to_animseq_retargeter_details.png)

Property | Description
------------ | -------------
Source Chain| Source bone chain
Target Chain| Target joint chain
Rotation Mode| Select the mode for establishing the mapping relationship between the source and target chains.

####6. Motion Data Browser Tab

![motion_to_animseq_retargeter_motion_data_browser](img/motion_to_animseq_retargeter_motion_data_browser.png)

####7. Chain Mapping Tab

![motion_to_animseq_chain_mapping](img/motion_to_animseq_chain_mapping.png)

Control | Description
------------ | -------------
Auto-Map Chains | Attempt to automatically pair by name.
Drop-down menu in the Source Chain column | Manually select the source joint chain


##Quick Start

In this quick start guide we will show you how to import a mo-cap file saved in bvh format into Unreal Engine Editor and retarget it to skeletal animation of an existing character. It also shows how to convert animations between two characters with different bone hierarchies, such as retargeting animations downloaded from the mixamo.com website to standard Unreal Engine skinned characters. For more detailed use, please refer to the [Video Tutorials](#video-tutorials)

####Enable plugin
Download and make sure to enable the plugin in the editor.

![open_plugins_panel](img/open_plugins_panel_.png)


![swift_motion_toolkit_in_plugins_panel](img/swift_motion_toolkit_in_plugins_panel.png)


### Retarget mo-cap to AnimSequence asset
####Import motion capture resources

Drag and drop the Mocap resource file in bvh format to the Content Browser of Unreal Engine.

![lafan_bvh_files_in_explorer](img/lafan_bvh_files_in_explorer.png)

You can choose to import Hierarchy assets only or Motion Data assets as well. If you need to import a Motion Data asset, you must select a compatible Hierarchy asset. You can check to import Hierarchy assets or select existing Hierarchy assets. 

![bvh_importer_option_ui](img/bvh_importer_option_ui.png)

If you choose to import both, the result is shown in the image below:

![mocap_related_assets](img/mocap_related_assets.png)

(1) is [Motion Data](#motion-data), (2) is [Motion Hierarchy](#motion-hierarchy)

Assets can be double-clicked to open them for viewing in the [Motion Data Editor](#motion-data-editor) and [Motion Hierarchy Editor](#motion-hierarchy-editor) respectively.


####Adjust the Base Retarget Pose in the Motion Hierarchy asset to TPose
![retarget_base_pose_edit_before](img/retarget_base_pose_edit_before.png)

Before

![retarget_base_pose_edit_after](img/retarget_base_pose_edit_after.png)

After


In the *Edit Retarget Base Pose* panel:

* Click the *Use Current Pose* button to set the pose in the viewport to the *Retarget Base Pose* used by the *Retargetable* asset.
* Click the *Restore to Base Pose* button to restore the pose in the viewport to *Retarget Base Pose*.
* Click the *Reset Pose* button to reset the pose in the viewport to the *Retarget Base Pose* used by the *Hierarchy* asset that the *Retargetable* depends on.


####Create the Motion Hierarchy Retargetable asset

by selecting the Motion Hierarchy Retargetable option in the Swift Motion Toolkit category of the Content Browser context menu.

![create_motion_hierarchy_retargetable_asset](img/create_motion_hierarchy_retargetable_asset.png)

In the popup select the Motion Hierarchy asset as the retarget source.

![create_motion_hierarchy_retargetable_asset_pick_hierarchy](img/create_motion_hierarchy_retargetable_asset_pick_hierarchy.png)

The following is the [Motion Hierarchy Retargetable](#motion-hierarchy-retargetable) asset created:

![motion_hierarchy_retargetable_in_content_browser](img/motion_hierarchy_retargetable_in_content_browser.png)

Double-click an asset to open the corresponding editor:


In the *Joint Chain Settings* panel, the *Joint Chain* and the *Retargetable Root Bone* for the current *Retargetable* can be defined.

![motion_bone_chain_edit](img/motion_bone_chain_edit.png)

####Create the Skeleton Hierarchy asset.

Via selecting the Skeleton Hierarchy option in the Swift Motion Toolkit category of the Content Browser context menu.

![create_skeleton_hierarchy](img/create_skeleton_hierarchy.png)


Select the Skeletal Mesh asset in the popup .

![create_skeleton_hierarchy_pick_mesh](img/create_skeleton_hierarchy_pick_mesh.png)

The [Skeleton Hierarchy](#skeleton-hierarchy) asset created is as follows :

![skeleton_hierarchy_asset_in_content_browser](img/skeleton_hierarchy_asset_in_content_browser.png)


Double-click an asset to open the corresponding editor:

![open_skeleton_hierarchy_editor](img/open_skeleton_hierarchy_editor.png)


Edit *Retarget Base Pose* in the viewport (recommend adjusting it to T Pose).

![skeleton_retarget_base_pose_edit_before](img/skeleton_retarget_base_pose_edit_before.png)
Before

![skeleton_retarget_base_pose_edit_after](img/skeleton_retarget_base_pose_edit_after.png)
After


In the *Edit Retarget Base Pose* panel:

* Click the *Use Current Pose* button to set the pose in the viewport to the *Retarget Base Pose* used by the *Retargetable* asset.
* Click the *Restore to Base Pose* button to restore the pose in the viewport to *Retarget Base Pose*.
* Click the *Reset Pose* button to reset the pose in the viewport to the *Retarget Base Pose* used by the *Hierarchy* asset that the *Retargetable* depends on.

![skeleton_retarget_use_current_pose](img/use_current_pose.png)


####Create the Skeleton Hierarchy Retargetable asset.

Via selecting the Skeleton Hierarchy Retargetable option in the Swift Motion Toolkit category of the Content Browser context menu.

![create_skeleton_hierarchy_retargetable](img/create_skeleton_hierarchy_retargetable.png)


Select the Skeleton Hierarchy asset in the popup .

![create_skeleton_hierarchy_retargetable_pick_mesh](img/create_skeleton_hierarchy_retargetable_pick_mesh.png)


The following is the created [Skeleton Hierarchy Retargetable](#skeleton-hierarchy-retargetable) asset:

![skeleton_hierarchy_retargetable_in_content_browser](img/skeleton_hierarchy_retargetable_in_content_browseer.png)


Double-click an asset to open the corresponding editor:

![open_skeleton_hierarchy_retargegtable_editor](img/open_skeleton_hierarchy_retargegtable_editor.png)


In the *Joint Chain Settings* panel, it is possible to define the *Joint Chain* and the *Retargetable Root Bone* for the current *Retargetable*.

![skeleton_retarget_bone_chain_edit](img/skeleton_retarget_bone_chain_edit.png)



####Create Motion to AnimSeq Retargeter


By selecting Motion to AnimSeq from the Swift Motion Toolkit category in the Content Browser context menu The Retargeter option creates corresponding assets.

![create_motion_2_seq_retargetable](img/create_motion_2_seq_retargetable.png)


In the pop-up window select the Motion Hierarchy Retargetable asset for the source and the Skeleton Hierarchy Retargetable asset for the target respectively.

![create_create_motion_2_seq_retargetable_pick_src_target](img/create_create_motion_2_seq_retargetable_pick_src_target.png)


The [Motion to AnimSeq](#motion-to-animseq-retargeter) created is as follows Retargeter assets:

![motion_2_seq_retargeter_in_content_browser](img/motion_2_seq_retargeter_in_content_browseer.png)


Double-click an asset to open the corresponding editor:

![open_motion_2_seq_retargeter_editor](img/open_motion_2_seq_retargeter_editor.png)


In the *Chain Mapping* panel, we can set the mapping relationship between the retarget source and target *Joint Chains*.

![source_and_target_chain_mapping](img/source_and_target_chain_mapping.png)


Then double-click on the asset in the *Motion Data Browser* to preview the retargeting result in the viewport.

![motion_retargeter_browser](img/motion_retargeter_browser.png)

![mocap_to_ue_mesh_preview](img/mocap_to_ue_mesh_preview.gif)

###Retarget between AnimSequence assets

for using an *AnimSequence* asset as a retarget source is similar to using a Mocap asset as a retarget source. We first need to create a *Hierarchy* asset and a *Hierarchy Retargetable* asset based on the *Skeletal Mesh* asset of the retarget source. Then use the *Retargeter* asset to create a mapping between the two for retarget. Converted assets can be used out of the box in *Unreal Engine* because our tool does proper handling of root joints and IK joints.

####Source animation download from mixamo.com

![source_anim_download_from_mixamo](img/source_anim_download_from_mixamo.png)

####Create the Skeleton Hierarchy asset for the source animation.

Via selecting the Skeleton Hierarchy option in the Swift Motion Toolkit category of the Content Browser context menu.

![create_mixamo_skeleton_hierarchy](img/create_mixamo_skeleton_hierarchy.png)

In the popup select the Skeletal Mesh asset as the retarget source.

![create_mixamo_skeleton_hierarchy_pick_mesh](img/create_mixamo_skeleton_hierarchy_pick_mesh.png)

The Skeleton Hierarchy asset created is as follows :

![mixamo_skeleton_hierarchy_asset_in_content_browser](img/mixamo_skeleton_hierarchy_asset_in_content_browser.png)

Double-click an asset to open the corresponding editor:

![open_mixamo_skeleton_hierarchy_editor](img/open_mixamo_skeleton_hierarchy_editor.png)



In the *Edit Retarget Base Pose* panel:

* Click the *Use Current Pose* button to set the pose in the viewport to the *Retarget Base Pose* used by the *Retargetable* asset.
* Click the *Restore to Base Pose* button to restore the pose in the viewport to *Retarget Base Pose*.
* Click the *Reset Pose* button to reset the pose in the viewport to the *Retarget Base Pose* used by the *Hierarchy* asset that the *Retargetable* depends on.

![skeleton_retarget_use_current_pose](img/use_current_pose.png)

####Create the Skeleton Hierarchy Retargetable asset for the source animation.

Via selecting the Skeleton Hierarchy Retargetable option in the Swift Motion Toolkit category of the Content Browser context menu.

![create_mixamo_skeleton_hierarchy_retargetable](img/create_mixamo_skeleton_hierarchy_retargetable.png)

Select the Skeleton Hierarchy asset in the popup .

![create_mixamo_skeleton_hierarchy_retargetable_pick_mesh](img/create_mixamo_skeleton_hierarchy_retargetable_pick_mesh.png)

The following is the created Skeleton Hierarchy Retargetable asset:

![mixamo_skeleton_hierarchy_retargetable_in_content_browser](img/mixamo_skeleton_hierarchy_retargetable_in_content_browseer.png)

Double-click an asset to open the corresponding editor:

![open_smixamo_keleton_hierarchy_retargegtable_editor](img/open_mixamo_skeleton_hierarchy_retargegtable_editor.png)


Because there is already a fully consistent Joint Chains definition in other *Retargetable*, we can copy it from there. (Even if it is not consistent, it can be copied. Our tool will ignore the Joint Chains that do not match the *Hierarchy* correctly.)

![copy_motion_bone_chain_mapping](img/copy_motion_bone_chain_mapping.png)
Copy

![paste_motion_bone_chain_mapping](img/paste_motion_bone_chain_mapping.png)
Paste


Set retarget root bone

![set_mixamo_retargetable_root_bone](img/set_mixamo_retargetable_root_bone.png)



####Create Motion to AnimSeq Retargeter(reuse the previously created Target Skeleton Hierarchy Retargetable)

Via selecting Motion to AnimSeq from the Swift Motion Toolkit category in the Content Browser context menu The Retargeter option creates corresponding assets.

![create_mixamo_motion_2_seq_retargeter](img/create_mixamo_motion_2_seq_retargeter.png)

In the pop-up window select the Motion Hierarchy Retargetable asset for the source and the Skeleton Hierarchy Retargetable asset for the target respectively.

![create_create_mixamo_motion_2_seq_retargeter_pick_src_target](img/create_create_mixamo_motion_2_seq_retargeter_pick_src_target.png)

The Motion to AnimSeq created is as follows Retargeter assets:

![mixamo_motion_2_seq_retargeter_in_content_browser](img/mixamo_motion_2_seq_retargeter_in_content_browseer.png)

Double-click an asset to open the corresponding editor:

![open_mixamo_motion_2_seq_retargeter_editor](img/open_mixamo_motion_2_seq_retargeter_editor.png)


In the *Chain Mapping* panel, we can set the mapping relationship between the source and target *Joint Chains*.

![source_and_target_chain_mapping](img/source_and_target_chain_mapping.png)


Then double-click on the asset in the *Motion Data Browser* to preview the retargeting result in the viewport.

![mixamo_motion_retargeter_browser](img/mixamo_motion_retargeter_browser.png)

![mixamo_to_ue_mesh_preview](img/mixamo_to_ue_mesh_preview.gif)




