# GameFeatureTemplateExtension
A plug-and-play Unreal Engine Editor plugin to register project-relative Game Feature templates, fixing path resolution issues without engine modifications.

# Quick Start Guide

## Installation

1. Copy the `GameFeatureTemplateExtension` folder into your project's `Plugins/` directory:
   ```text
   YourProject/
   └── Plugins/
       └── GameFeatureTemplateExtension/
   ```

2. Regenerate your C++ project files and compile the solution.
3. Launch Unreal Engine and ensure the plugin is enabled under **Edit > Plugins**.

    <img width="960" height="122" alt="image" src="https://github.com/user-attachments/assets/e765c02c-c040-440d-8cc4-c4158d0f7fc0" />

### For Blueprint-Only Projects
1. Go to the Releases section of this GitHub repository and download the pre-compiled zip package matching your Unreal Engine version.
2. Extract the `GameFeatureTemplateExtension` plugin folder directly into your project's `Plugins/` directory (create the `Plugins` folder if it doesn't exist).
3. Open your project in Unreal Engine, the pre-compiled plugin will be loaded automatically!

---

## Configuration

1. Open **Project Settings** (**Edit > Project Settings**).

    <img width="499" height="356" alt="image" src="https://github.com/user-attachments/assets/38e17685-e90f-4dcc-b33d-4bd15ec53ee5" />

2. Scroll down to the **Plugins** category and select **Game Feature Template Editor Settings**.

    <img width="369" height="310" alt="image" src="https://github.com/user-attachments/assets/2ea1f718-4e14-40f5-9cb2-c7f14ead1671" />

3. Click the **+** button to add a new item to the **Plugin Templates** array.

    <img width="833" height="134" alt="image" src="https://github.com/user-attachments/assets/3ca19088-594c-4e98-91e9-bf5760a71cdb" />

4. Fill in your template properties:
    * **Path**: Set the path to your custom plugin template directory (e.g., `Plugins/Templates/MyCustomTemplate`). Relative paths are automatically resolved against `FPaths::ProjectDir()`.
    * **Label**: The display name shown in the Plugin Creation Wizard.
    * **Description**: A short summary of what this template contains.
    * **Default Subfolder**: The target subfolder inside `Plugins/` where the new plugin will be generated.
    * **Default Plugin Name**: The default name pre-filled when selecting this template.
    * **Default Game Feature Data Class**: Select your custom `UGameFeatureData` subclass (defaults to base `UGameFeatureData` if empty).
    * **Default Game Feature Data Name**: Default asset name for the created Game Feature Data. If empty, uses the plugin name.
    * **bIsEnabledByDefault**: Check to enable the newly created plugin automatically without editing `.uproject`.
    * **Post Create Python Script Path** *(UE 5.8+)*: Relative path for a Python script to execute immediately after plugin creation.
    * **Post Create Python Script Arguments** *(UE 5.8+)*: Arguments for a Python script to execute immediately after plugin creation.

    
  <img width="922" height="305" alt="image" src="https://github.com/user-attachments/assets/7a566563-c5f2-4ae9-b0e7-04b42a684dd0" />

---

## Usage

1. Open the **Plugins** window (**Edit > Plugins**).

    <img width="290" height="377" alt="image" src="https://github.com/user-attachments/assets/a6bba2c7-9977-4b13-bd07-0a894b0268a9" />

2. Click **+ Add** to open the Plugin Creation Wizard.

    <img width="474" height="129" alt="image" src="https://github.com/user-attachments/assets/5b13e963-f791-413f-afd2-3a4e27b538c4" />

3. Select your custom Game Feature template from the list.

    <img width="825" height="560" alt="image" src="https://github.com/user-attachments/assets/76eeaf2b-ae43-4d2d-a555-c2278d2f6030" />

4. Set your new plugin name and click **Create Plugin**.

    <img width="670" height="228" alt="image" src="https://github.com/user-attachments/assets/eb798afe-d4f8-4fad-87aa-969b212cc1b5" />

> **Note:** Any changes made in *Project Settings* will hot-reload automatically, no editor restart is required when adding, editing, or removing template paths!
