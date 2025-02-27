# Unity-HDRP-Vioso-Lablab
Unity HDRP example project with Vioso integration for the Lablab studio.

## Installation

1. Download or clone this project on your computer.

2. Download the Vioso calibration file [here](https://gofile.me/67omf/yH5xHTjiS) and add it to the Assets/Plugins/Vioso/ folder. 


### Merging into your own project (optional)

1. Copy the Plugins, ProjectionSetup and Resources folders from this project to your own project Assets.

2. Add the ViosoWarpBlendPP to the After Post Process section of the HDRP Global Settings.

<img src="https://github.com/Theoriz/Unity-HDRP-Vioso-Template/blob/main/Resources/Documentation/Screenshots/HDRPGlobalSettings.jpg" width="50%" height="50%">

3. Replace the camera in your scene by the ProjectionSetup prefab from the ProjectionSetup/Prefab folder.


## Building your application

After building your application, copy the vioso calibration file (.vwf) and VIOSOWarpBlend.ini files from the Unity Assets/Plugins/Vioso folder to your build folder in [your_build_path..]/[your_application_name]_Data/Plugins/[your_architecture]/ next to the ViosoWarpBlend.dll file.

> When building for Windows 64 bits, the ViosoBuildPostProcessor script should automatically make this copy.

## Usage

### ProjectionSetup prefab

The projection setup for the Lablab studio is created in the ProjectionSetup prefab located in the ProjectionSetup/Lablab/Prefab/ folder.

![](https://github.com/Theoriz/Unity-HDRP-Vioso-Template/blob/main/Resources/Documentation/Screenshots/ProjectionSetupPrefab.jpg)

Add this prefab to your scene and disable other cameras in order to setup your scene for projection in the Lablab studio.

For example in the SampleScene, this projection setup as been added to the First person controller to replace the default camera of the First person controller.

![](https://github.com/Theoriz/Unity-HDRP-Vioso-Template/blob/main/Resources/Documentation/Screenshots/ProjectionSetupInSampleScene.jpg)

### Game View setup

To work with the Lablab video projectors setup, the Unity application creates 3 full screen windows. The window on display 1 is for the wall outputs, the window on display 2 is empty as it is the monitoring display, the window on display 3 is for the floor outputs.

To previsualize this in Unity, you need to set your game view(s) to render the display 1 (for the walls) and 3 (for the floor), at a 3840x2400 resolution.

With this setup, you should see the following output in the sample scene :

![](https://github.com/Theoriz/Unity-HDRP-Vioso-Template/blob/main/Resources/Documentation/Screenshots/OutputsMire.jpg)

### Using the studio model

In the ProjectionSetup prefab, the Lablab object is a 3D model of the studio for debugging purposes. It is enabled to help you visualize the physical space of the studio in your 3D world and validate the outputs. Once it is setup correctly, you can disable the Lablab component of the ProjectionSetup to see the final output of your scene.

![](https://github.com/Theoriz/Unity-HDRP-Vioso-Template/blob/main/Resources/Documentation/Screenshots/ProjectionSetupInSampleSceneMireDisabled.jpg)
![](https://github.com/Theoriz/Unity-HDRP-Vioso-Template/blob/main/Resources/Documentation/Screenshots/Outputs.jpg)
