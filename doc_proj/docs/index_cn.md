#Welcome to Swift Motion Toolkit Manual

##Overview

*Swift Motion Toolkit* 是一套集成 mo-cap 资源导入、动画重定向和 Root Motion 处理等功能于一体的角色动画工具。同时它也支持不同角色 AnimSequence 动画资产之间的重定向等等。

##Features

* 导入 BVH 格式的 mo-cap 动画，并提供预览。
* 重定向 mo-cap 动画为AnimSequence资产。
* 重定向AnimSequence资产。
* 支持以IK的方式更精确的调整末端关节的位置。
* 支持将动画同步至IK骨骼。
* 支持将垂直或（和）水平方向的Root位移烘焙至动画。
* 支持有选择性的保留根旋转。
* 支持将带根运动的动画转为原地动画。

##Showcase

<iframe width="560" height="315" src="https://www.youtube.com/embed/G_QuKErWYU4" frameborder="0" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/jM3J4OttxXs" frameborder="0" allowfullscreen></iframe>



##相关资产
###Motion Hierarchy
<span id="motion-hierarchy"></span>
*Motion Hierarchy* 资产记录了 mo-cap 动画使用的的骨架层次结构并包含了一个重定向基础姿势。


###Motion Data
<span id="motion-data"></span>
*Motion Data* 记录了  mo-cap  动画的一系列与时间相关的姿势数据。并持有对一个 Motion Hierarchy 资产的引用。该 Motion Hierarchy 资产可以解释 Motion Data 中每个姿势的拓扑结构。

###Motion Hierarchy Retargetable
<span id="motion-skeleton-hierarchy"></span>
*Motion Hierarchy Retargetable* 持有一个 *Motion Hierarchy* 资产的引用。 该资产允许用户定义若干条骨骼链用于动作重定向，并且允许用户定义新的重定向基础姿势（如果不在 *Motion Hierarchy Retargetable* 中定义重定向基础姿势，则在重定向时将使用 *Motion Hierarchy* 中的重定向基础姿势）。

###Skeleton Hierarchy
<span id="skeleton-hierarchy"></span>
*Skeleton Hierarchy* 持有一个 *USkeleton* 资产的引用。 该资产允许用户定义新的重定向基础姿势（如果不在 *Skeleton Hierarchy* 中定义重定向基础姿势，则在重定向时将使用 *USkeleton*  中的重定向基础姿势）。

###Skeleton Hierarchy Retargetable
<span id="skeleton-hierarchy-retargetable"></span>
*Skeleton Hierarchy Retargetable* 持有一个 *Skeleton Hierarchy* 资产的引用。 该资产允许用户定义若干条骨骼链用于动作重定向，并且允许用户定义新的重定向基础姿势（如果不在 *Skeleton Hierarchy Retargetable* 中定义重定向基础姿势，则在重定向时将使用 *Skeleton Hierarchy* 中的重定向基础姿势）。

###Motion to AnimSeq Retargeter
<span id="motion-to-animseq-retargeter"></span>
*Motion to AnimSeq Retargeter* 持有一对 *Hierarchy Retargetable* 作为重定向的源和目标。 该资产允许用户对源和目标的骨骼链映射表，和FK、IK以及Root Motion进行配置。并提供重定向结果的预览和导出。


##编辑器


###Motion Hierarchy Editor
<span id="motion-hierarchy-editor"></span>
支持对 Motion Hierarchy 的预览和编辑。
![motion_hierarchy_editor_overview](img/motion_hierarchy_editor_overview.png)

####1. Hierarchy Tree Tab

![motion_hierarchy_tree_tab](img/motion_hierarchy_tree_tab.png)

####2. Asset Details

![motion_data_editor_overview](img/motion_date_editor_asset_details.png)

Property | Description
------------ | -------------
Left Joint Identification List| 左边关节标识列表 
Flag| 关节名称中的标识 
Type| 标识类型：1. 前缀  2. 后缀  3. 包含 
Left Joint Display Color | 右边关节显示的颜色
Right Joint Identification List| 右边关节标识列表 
Flag| 关节名称中的标识 
Type| 标识类型：1. 前缀  2. 后缀  3. 包含 
Right Joint Display Color | 右边关节显示的颜色
Other Joint Display Color | 其它关节显示的颜色

(注： 标识列表中允许有多个元素。如果关节名满足其中任一条件则判为“真”。)

####3. Viewport Tab

![hierarchy_viewport_details_tab](img/hierarchy_viewport_details_tab.png)

####4. Details Tab

![edit_retarget_base_pose](img/motion_details.png)

####5. Retarget Base Pose Tab

![edit_retarget_base_pose](img/edit_retarget_base_pose.png)

Control | Description
------------ | -------------
Use Current Pose | 将视口中的姿势写入 *Retarget Base Pose* 
Restore to Base Pose | 将 *Retarget Base Pose* 还原至视口
Reset Pose | 将参考姿势写入 *Retarget Base Pose* 



###Motion Data Editor
<span id="motion-data-editor"></span>
    支持对 Motion Data 的预览。
    
![motion_data_editor_overview](img/motion_data_editor_overview.png)


####1. Hierarchy Tree Tab

![motion_hierarchy_tree_tab](img/motion_hierarchy_tree_tab.png)

####2. Asset Details Tab

![motion_hierarchy_retargetable_asset_details_tab](img/motion_data_asset_details_tab.png)

####3. Viewport Tab

![motion_hierarchy_viewport_details_tab](img/motion_viewport_details_tab.png)

####4. Player Controller Tab

![player_controller_tab](img/player_controller_tab.png)

通过滚轮可以进行缩放
![motion_data_player_controller_zoom](img/motion_data_player_controller_zoom.gif)

右键拖拽可以左右平移时间轴
![motion_data_player_controller_pan](img/motion_data_player_controller_pan.gif)

####5. Details Tab

![edit_retarget_base_pose](img/motion_details.png)

####6. Motion Data Browser Tab

![motion_data_browser](img/motion_data_browser.png)



###Motion Hierarchy Retargetable Editor
<span id="motion-hierarchy-retargetable-editor"></span>
    支持对 Motion Hierarchy Retargetable 的预览和编辑。
    
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
Use Current Pose | 将视口中的姿势写入 *Retarget Base Pose* 
Restore to Base Pose | 将 *Retarget Base Pose* 还原至视口
Reset Pose | 将参考姿势写入 *Retarget Base Pose* 

####6. Retarget Chains Tab

![chain_settings](img/chain_settings.png)

允许复制黏贴

![retarget_chain_copy_paste.gif](img/retarget_chain_copy_paste.gif)



###Skeleton Hierarchy Editor
<span id="skeleton-hierarchy-editor"></span>
    支持对 Skeleton Hierarchy 的预览和编辑。
![skeleton_hierarchy_retargetable_editor_overview](img/skeleton_hierarchy_editor_overview.png)

####1. Hierarchy Tree Tab

![skeleton_hierarchy_tree_tab](img/skeleton_hierarchy_tree_tab.png)

####2. Asset Details

![motion_data_editor_overview](img/motion_date_editor_asset_details.png)

Property | Description
------------ | -------------
Left Joint Identification List| 左边关节标识列表 
Flag| 关节名称中的标识 
Type| 标识类型：1. 前缀  2. 后缀  3. 包含 
Left Joint Display Color | 右边关节显示的颜色
Right Joint Identification List| 右边关节标识列表 
Flag| 关节名称中的标识 
Type| 标识类型：1. 前缀  2. 后缀  3. 包含 
Right Joint Display Color | 右边关节显示的颜色
Other Joint Display Color | 其它关节显示的颜色

(注： 标识列表中允许有多个元素。如果关节名满足其中任一条件则判为“真”。)

####3. Viewport Tab

![skeleton_hierarchy_viewport_details_tab](img/skeleton_hierarchy_viewport_details_tab.png)

####4. Details Tab

![skeleton_hierarchy_details](img/skeleton_hierarchy_details.png)

####5. Retarget Base Pose Tab

![edit_retarget_base_pose](img/edit_retarget_base_pose.png)

Control | Description
------------ | -------------
Use Current Pose | 将视口中的姿势写入 *Retarget Base Pose* 
Restore to Base Pose | 将 *Retarget Base Pose* 还原至视口
Reset Pose | 将参考姿势写入 *Retarget Base Pose* 



###Skeleton Hierarchy Retargetable Editor
<span id="skeleton-hierarchy-retargetable-editor"></span>
    支持对 Skeleton Hierarchy Retargetable 的预览和编辑。
![skeleton_hierarchy_retargetable_editor_overview](img/skeleton_hierarchy_retargetable_editor_overview.png)


####1. Hierarchy Tree Tab

![skeleton_hierarchy_tree_tab](img/skeleton_hierarchy_tree_tab.png)



####2. Asset Details Tab

![skeleton_hierarchy_retargetable_asset_details_tab](img/skeleton_hierarchy_retargetable_asset_details_tab.png)


####3. IK Settings Tab

![skeleton_hierarchy_retargetable_ik_settings_tab](img/skeleton_hierarchy_retargetable_ik_settings_tab.png)

Control | Control | Description
------------ | ------------ | -------------
1 | Add New Solver | 增加新的求解器 
2 | check box | 启用/禁用求解器
3 | 垃圾桶图标按钮 | 删除对应求解器 

(注： 选中任一求解器，在 Details 标签页中将显示它的配置界面。)


####4. Viewport Tab

![skeleton_hierarchy_retargetable_viewport_tab](img/skeleton_hierarchy_retargetable_viewport_tab.png)

####5. Details Tab

![skeleton_hierarchy_retargetable_details](img/skeleton_hierarchy_retargetable_details.png)

Property | Description
------------ | -------------
Use Pole Vector| 是否使用极向量 
Pole Vector| 极向量 
Target Alpha| 目标应用程度 
Target Alpha| 目标容差量
Tip Bone Keep Local Rot| 末端节点在应用了IK后是否保持Local空间的旋转，还是保持应用IK前Global空间的旋转
Joint Chain Name| 骨骼链名称 

####6. Edit Retarget Base Pose Tab

![edit_retarget_base_pose](img/edit_retarget_base_pose.png)


Control | Description
------------ | -------------
Use Current Pose | 将视口中的姿势写入 *Retarget Base Pose* 
Restore to Base Pose | 将 *Retarget Base Pose* 还原至视口
Reset Pose | 将参考姿势写入 *Retarget Base Pose* 


####7. Retarget Chains Tab

![skeleton_hierarchy_retargetable_chain_settings](img/skeleton_hierarchy_retargetable_chain_settings.png)

允许复制黏贴

![retarget_chain_copy_paste.gif](img/retarget_chain_copy_paste.gif)


###Motion to AnimSeq Retargeter Editor
<span id="motion-to-animseq-retargeter-editor"></span>
    支持对源和目标间的重定向设置和对结果的预览。
![motion_to_animseq_retargeter_editor_overview](img/motion_to_animseq_retargeter_editor_overview.png)

####1. Hierarchy Tree Tab

![skeleton_hierarchy_tree_tab](img/skeleton_hierarchy_tree_tab.png)

####2. Asset Details Tab

![motion_to_animseq_retargeter_asset_details_tab](img/motion_to_animseq_retargeter_asset_details_tab.png)

Property | Description
------------ | -------------
Source| 源 Retargetable 
Target| 目标 Retargetable 
Horizontal Root Offset Scale| 水平方向Root偏移缩放 
Verticle Root Offset Scale| 垂直方向Root偏移缩放 
Convert Motion To Root Bone| 将运动设置到根骨骼
Bake Root Rotation in Animation| 将根节点的旋转烘焙至动画
Keep Root Rotation Around Up Only| 保持Root仅围绕向上方向的的旋转
Bake Root Verticle Translation in Animation| 将根节点的垂直位移烘焙至动画 
Bake Horizontal Translation in Animation| 将根节点的水平位移烘焙至动画 
Convert to In Place Animation| 是否转为原地动画 
IKCorrection Enalbe| 是否开启IK 

####3. Source Viewport Tab & Target_Viewport Tab

![motion_to_animseq_retargeter_src_target_viewport_tab](img/motion_to_animseq_retargeter_src_target_viewport_tab.gif)

####4. Player Controller Tab

![player_controller_tab](img/player_controller_tab.png)

通过滚轮可以进行缩放
![motion_data_player_controller_zoom](img/motion_data_player_controller_zoom.gif)

右键拖拽可以左右平移时间轴
![motion_data_player_controller_pan](img/motion_data_player_controller_pan.gif)

####5. Details Tab

![motion_to_animseq_retargeter_details](img/motion_to_animseq_retargeter_details.png)

Property | Description
------------ | -------------
Source Chain| 源骨骼链 
Target Chain| 目标骨骼链 
Rotation Mode| 选择在源与目标链间建立映射关系的模式

####6. Motion Data Browser Tab

![motion_to_animseq_retargeter_motion_data_browser](img/motion_to_animseq_retargeter_motion_data_browser.png)

####7. Chain Mapping Tab

![motion_to_animseq_chain_mapping](img/motion_to_animseq_chain_mapping.png)

Control | Description
------------ | -------------
Auto-Map Chains | 尝试按名称自动配对。
Source Chain列中的下拉选单 | 手动选择源关节链


##Quick Start

在这份 quick start guide 中我们将向您展示，如何将存储为 bvh 格式的 mo-cap 文件导入 Unreal Engine Editor，并将其重定向为已有角色的骨骼动画。 同时也向您展示如何在两个骨骼层级结构不同的角色间进行动画的转换，例如将 mixamo.com 网站上下载的动画重定向至标准的 Unreal Engine 蒙皮角色上。 更详细的使用请参考视频教程
[视频教程](#video-tutorials)

####开启插件
下载并确保在编辑器中开启插件。


![open_plugins_panel](img/open_plugins_panel_.png)



![swift_motion_toolkit_in_plugins_panel](img/swift_motion_toolkit_in_plugins_panel.png)


### mo-cap  动画重定向至 AnimSequence资产
####导入动作捕捉资源。

将 bvh 格式的  mo-cap  资源文件拖拽至 Unreal Engine 的 Content Browser 中。

![lafan_bvh_files_in_explorer](img/lafan_bvh_files_in_explorer.png)

可以选择仅导入 Hierarchy 资产或同时导入 Motion Data 资产。若需要导入 Motion Data 资产，则必须选择与之兼容的 Hierarchy 资产。可以勾选导入 Hierarchy 资产或选择已有 Hierarchy 资产。 

![bvh_importer_option_ui](img/bvh_importer_option_ui.png)

如果选择导入两者，则结果如下图所示：

![mocap_related_assets](img/mocap_related_assets.png)

其中（1）是 [Motion Data](#motion-data) , (2) 是 [Motion Hierarchy](#motion-hierarchy)

可以双击资产，分别在 [Motion Data Editor](#motion-data-editor) 和 [Motion Hierarchy Editor](#motion-hierarchy-editor) 中打开查看。


####将 Motion Hierarchy 资产中的 Base Retarget Pose 调整为 TPose。

![retarget_base_pose_edit_before](img/retarget_base_pose_edit_before.png)

调整前

![retarget_base_pose_edit_after](img/retarget_base_pose_edit_after.png)

调整后

在 *Edit Retarget Base Pose* 面板中:

* 点击 *Use Current Pose* 按钮可以将视口中的姿势设置为 *Retargetable* 资产所使用的 *Retarget Base Pose*.
* 点击 *Restore to Base Pose* 按钮可以将视口中的姿势还原为 *Retarget Base Pose*.
* 点击 *Reset Pose* 按钮可以将视口中的姿势还原为当前 *Retargetable* 依赖的 *Hierarchy* 资产所使用的 *Retarget Base Pose*.


####创建 Motion Hierarchy Retargetable 资产。

通过选择 Content Browser 上下文菜单 Swift Motion Toolkit 分类中 Motion Hierarchy Retargetable 选项创建对应资产。

![create_motion_hierarchy_retargetable_asset](img/create_motion_hierarchy_retargetable_asset.png)

在弹出窗口中选择作为重定向源的 Motion Hierarchy 资产。

![create_motion_hierarchy_retargetable_asset_pick_hierarchy](img/create_motion_hierarchy_retargetable_asset_pick_hierarchy.png)

如下为创建的 [Motion Hierarchy Retargetable](#motion-hierarchy-retargetable) 资产：

![motion_hierarchy_retargetable_in_content_browser](img/motion_hierarchy_retargetable_in_content_browser.png)

双击资产可以打开对应编辑器：


在 *Joint Chain Settings* 面板中，可以为当前 *Retargetable* 定义 *Joint Chain* 和 *重定向根骨骼*.

![motion_bone_chain_edit](img/motion_bone_chain_edit.png)

####创建 Skeleton Hierarchy 资产。

通过选择 Content Browser 上下文菜单 Swift Motion Toolkit 分类中 Skeleton Hierarchy 选项创建对应资产。

![create_skeleton_hierarchy](img/create_skeleton_hierarchy.png)


在弹出窗口中选择作为重定向目标的 Skeletal Mesh 资产。

![create_skeleton_hierarchy_pick_mesh](img/create_skeleton_hierarchy_pick_mesh.png)

如下为创建的 Skeleton Hierarchy 资产：

![skeleton_hierarchy_asset_in_content_browser](img/skeleton_hierarchy_asset_in_content_browser.png)


双击资产可以打开对应编辑器：

![open_skeleton_hierarchy_editor](img/open_skeleton_hierarchy_editor.png)


在视口中编辑 *Retarget Base Pose* (建议将其调整为 T Pose)。

![skeleton_retarget_base_pose_edit_before](img/skeleton_retarget_base_pose_edit_before.png)
调整前

![skeleton_retarget_base_pose_edit_after](img/skeleton_retarget_base_pose_edit_after.png)
调整后


在 *Edit Retarget Base Pose* 面板中:

* 点击 *Use Current Pose* 按钮可以将视口中的姿势设置为 *Retargetable* 资产所使用的 *Retarget Base Pose*.
* 点击*Restore to Base Pose* 按钮可以将视口中的姿势还原为 *Retarget Base Pose*.
* 点击*Reset Pose* 按钮可以将视口中的姿势还原为当前 *Retargetable* 依赖的 *Hierarchy* 资产所使用的 *Retarget Base Pose*.

![skeleton_retarget_use_current_pose](img/use_current_pose.png)



####创建 Skeleton Hierarchy Retargetable 资产。

通过选择 Content Browser 上下文菜单 Swift Motion Toolkit 分类中 Skeleton Hierarchy Retargetable 选项创建对应资产。

![create_skeleton_hierarchy_retargetable](img/create_skeleton_hierarchy_retargetable.png)


在弹出窗口中选择作为重定向目标的 Skeleton Hierarchy 资产。

![create_skeleton_hierarchy_retargetable_pick_mesh](img/create_skeleton_hierarchy_retargetable_pick_mesh.png)


如下为创建的 [Skeleton Hierarchy Retargetable](#skeleton-hierarchy-retargetable)  资产：

![skeleton_hierarchy_retargetable_in_content_browser](img/skeleton_hierarchy_retargetable_in_content_browseer.png)


双击资产可以打开对应编辑器：

![open_skeleton_hierarchy_retargegtable_editor](img/open_skeleton_hierarchy_retargegtable_editor.png)


在 *Joint Chain Settings* 面板中，可以为当前 *Retargetable* 定义 *Joint Chain* 和 *重定向根骨骼*.

![skeleton_retarget_bone_chain_edit](img/skeleton_retarget_bone_chain_edit.png)

####创建 Motion to AnimSeq Retargeter


通过选择 Content Browser 上下文菜单 Swift Motion Toolkit 分类中 Motion to AnimSeq Retargeter 选项创建对应资产。

![create_motion_2_seq_retargetable](img/create_motion_2_seq_retargetable.png)


在弹出窗口中选择分别作为重定向源的 Motion Hierarchy Retargetable 和重定向目标的 Skeleton Hierarchy Retargetable 资产。

![create_create_motion_2_seq_retargetable_pick_src_target](img/create_create_motion_2_seq_retargetable_pick_src_target.png)


如下为创建的 [Motion to AnimSeq](#motion-to-animseq-retargeter)  资产：

![motion_2_seq_retargeter_in_content_browser](img/motion_2_seq_retargeter_in_content_browseer.png)


双击资产可以打开对应编辑器：

![open_motion_2_seq_retargeter_editor](img/open_motion_2_seq_retargeter_editor.png)


在 *Chain Mapping* 面板中我们可以设置重定向源和目标的 *Joint Chains* 间的映射关系。

![source_and_target_chain_mapping](img/source_and_target_chain_mapping.png)


然后在 *Motion Data Browser* 中双击相应资产即可在视口中预览重定向结果。

![motion_retargeter_browser](img/motion_retargeter_browser.png)

![mocap_to_ue_mesh_preview](img/mocap_to_ue_mesh_preview.gif)

###AnimSequence资产间的重定向

将 *AnimSequence* 资产作为重定向源与将  mo-cap  资产作为重定向源的工作流程是类似的。我们首先需要基于重定向源的 *Skeletal Mesh* 资产创建 *Hierarchy* 资产和 *Hierarchy Retargetable* 资产。然后通过 *Retargeter* 资产为两者间建立映射关系进行重定向。因为我们的工具可以对根关节和IK关节进行合适的处理，所以转换后的资产可以在 *Unreal Engine* 中开箱即用。

####从 mixamo.com 网站下载得源动画

####创建源动画的 Skeleton Hierarchy 资产。

通过选择 Content Browser 上下文菜单 Swift Motion Toolkit 分类中 Skeleton Hierarchy 选项创建对应资产。

![create_mixamo_skeleton_hierarchy](img/create_mixamo_skeleton_hierarchy.png)

在弹出窗口中选择作为重定向源的 Skeletal Mesh 资产。

![create_mixamo_skeleton_hierarchy_pick_mesh](img/create_mixamo_skeleton_hierarchy_pick_mesh.png)

如下为创建的 Skeleton Hierarchy 资产：

![mixamo_skeleton_hierarchy_asset_in_content_browser](img/mixamo_skeleton_hierarchy_asset_in_content_browser.png)


双击资产可以打开对应编辑器：

![open_smixamo_keleton_hierarchyeditor](img/open_mixamo_skeleton_hierarchyeditor.png)



在 *Edit Retarget Base Pose* 面板中:

* 点击 *Use Current Pose* 按钮可以将视口中的姿势设置为 *Retargetable* 资产所使用的 *Retarget Base Pose*.
* 点击*Restore to Base Pose* 按钮可以将视口中的姿势还原为 *Retarget Base Pose*.
* 点击*Reset Pose* 按钮可以将视口中的姿势还原为当前 *Retargetable* 依赖的 *Hierarchy* 资产所使用的 *Retarget Base Pose*.

![skeleton_retarget_use_current_pose](img/use_current_pose.png)


####创建源动画的 Skeleton Hierarchy Retargetable 资产。

通过选择 Content Browser 上下文菜单 Swift Motion Toolkit 分类中 Skeleton Hierarchy Retargetable 选项创建对应资产。

![create_mixamo_skeleton_hierarchy_retargetable](img/create_mixamo_skeleton_hierarchy_retargetable.png)

在弹出窗口中选择作为重定向目标的 Skeleton Hierarchy 资产。

![create_mixamo_skeleton_hierarchy_retargetable_pick_mesh](img/create_mixamo_skeleton_hierarchy_retargetable_pick_mesh.png)

如下为创建的 Skeleton Hierarchy Retargetable 资产：

![mixamo_skeleton_hierarchy_retargetable_in_content_browser](img/mixamo_skeleton_hierarchy_retargetable_in_content_browseer.png)

双击资产可以打开对应编辑器：

![open_smixamo_keleton_hierarchy_retargegtable_editor](img/open_mixamo_skeleton_hierarchy_retargegtable_editor.png)



因为其它 *Retargetable* 中已经存在完全一致的 Joint Chains 定义，所以我们可以从哪里拷贝过来.(即便不一致，也可以进行拷贝。我们的工具会忽略不能正确匹配 *Hierarchy* 的 Joint Chains.)

![copy_motion_bone_chain_mapping](img/copy_motion_bone_chain_mapping.png)
复制

![paste_motion_bone_chain_mapping](img/paste_motion_bone_chain_mapping.png)
黏贴


设置重定向根骨骼

![set_mixamo_retargetable_root_bone](img/set_mixamo_retargetable_root_bone.png)



####创建 Motion to AnimSeq Retargeter（复用之前创建的 Target Skeleton Hierarchy Retargetable）。

通过选择 Content Browser 上下文菜单 Swift Motion Toolkit 分类中 Motion to AnimSeq Retargeter 选项创建对应资产。

![create_mixamo_motion_2_seq_retargeter](img/create_mixamo_motion_2_seq_retargeter.png)

在弹出窗口中选择分别作为重定向源的 Motion Hierarchy Retargetable 和重定向目标的 Skeleton Hierarchy Retargetable 资产。

![create_create_mixamo_motion_2_seq_retargeter_pick_src_target](img/create_create_mixamo_motion_2_seq_retargeter_pick_src_target.png)

如下为创建的 Motion to AnimSeq Retargeter 资产：

![mixamo_motion_2_seq_retargeter_in_content_browser](img/mixamo_motion_2_seq_retargeter_in_content_browseer.png)

双击资产可以打开对应编辑器：

![open_mixamo_motion_2_seq_retargeter_editor](img/open_mixamo_motion_2_seq_retargeter_editor.png)


在 *Chain Mapping* 面板中我们可以设置重定向源和目标的 *Joint Chains* 间的映射关系。

![source_and_target_chain_mapping](img/source_and_target_chain_mapping.png)


然后在 *Motion Data Browser* 中双击相应资产即可在视口中预览重定向结果。

![mixamo_motion_retargeter_browser](img/mixamo_motion_retargeter_browser.png)

![mixamo_to_ue_mesh_preview](img/mixamo_to_ue_mesh_preview.gif)




