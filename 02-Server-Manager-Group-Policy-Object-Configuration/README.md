# Windows Server Configuration

### Project Overview
Essential configuration of Group Policy Objects (`GPOs`) in a `Windows Server` environment. This project involves configuring several `GPOs`. Specifically, you will create `GPOs` to disable the Control Panel, restrict access to the Command Prompt, prevent access to the Registry Editor, and disable the Recycle Bin icon.

### Goals
* Apply `GPOs` to an Organizational Unit (`OU`) to affect specific groups of users.
* Create and configure `GPOs` to manage user settings, including:
  * Disabling the Control Panel.
  * Restricting access to the Command Prompt.
  * Preventing access to the Registry Editor.
  * Disabling the Recycle Bin icon.

### Task Summary
* **Task 1:** Disable Control Panel: On the `Windows Server`, open the `Group Policy Management Console` and create a new `GPO` named "Disable Control Panel" under the Sales `OU` folder.
* **Task 2:** Restrict Control Panel and PC Settings: Edit the "Disable Control Panel" `GPO` and configure it to restrict user access to the Control Panel and PC settings.
* **Task 3:** Disable Command Prompt: Create a new `GPO` named "Disable CMD," link it under the Sales `OU` folder, and configure it to prevent users from accessing the command prompt (`CMD`).
* **Task 4:** Disable Registry Editor: Create a new `GPO` named "Disable Registry Editor," link it under the Sales `OU` folder, and configure the `GPO` to prevent users from accessing the Registry Editor.
* **Task 5:** Disable Recycle Bin Icon: Create a new `GPO` named "Disable Recycle Bin," link it under the Sales `OU` folder, and configure the `GPO` to hide the Recycle Bin icon from the desktop.
* **Task 6:** Apply and Verify `GPO` Settings: Verify the application of the following `GPO` configurations: Absence of the Recycle Bin icon on the desktop, disabled access to `CMD`, restricted access to the registry, and inaccessibility to the Control Panel.

### Step-by-Step Guide

---

### Task 1: Disable Control Panel

![Figure 1 - Disable Control Panel](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/02-Server-Manager-Group-Policy-Object-Configuration/images/Figure01_disable_control_panel.png)

1. On the `Windows Server`, in the `Server Manager` window, clicked the `Tools` tab and selected `Group Policy Management`.
2. In the `Group Policy Management` app, expanded the following path: **Forest: cyber.local > Domains > cyber.local**.
3. Located and right-clicked on the **Sales OU** folder. After right-clicking on the Sales `OU` folder, selected "`Create a GPO in this domain, and Link it here…`"
4. In the name field, entered “Disable Control Panel” as the name for the new `GPO`. Clicked `OK` to create it.

![Figure 2 - Disable Control Panel 2](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/02-Server-Manager-Group-Policy-Object-Configuration/images/Figure02_disable_control_panel_2.png)

### Task 2: Restrict Control Panel and PC Settings

![Figure 3 - Prohibit access to Control Panel and PC settings](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/02-Server-Manager-Group-Policy-Object-Configuration/images/Figure03_prohibit_access_to_control_panel_and_pc_settings.png)

1. Right-clicked the **Disable Control Panel** `GPO` under the Sales `OU` and chose **Edit**.
2. In the `Group Policy Management Editor` window, at the left pane, navigated to **User Configuration > Policies > Administrative Templates > Control Panel**.
3. In the main pane, right-clicked on **Prohibit access to Control Panel and PC settings** and select **Edit**.
4. In the next window, selected **Enabled**, clicked **Apply**, then **OK** to save the changes.

![Figure 4 - Prohibit access to Control Panel and PC settings 2](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/02-Server-Manager-Group-Policy-Object-Configuration/images/Figure04_prohibit_access_to_control_panel_and_pc_settings_2.png)

### Task 3: Disable Command Prompt

![Figure 5 - Prevent access to the command prompt](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/02-Server-Manager-Group-Policy-Object-Configuration/images/Figure05_prevent_access_to_the_command_prompt.png)

1. Right-clicked on the **Sales OU** folder and selected "`Create a GPO in this domain, and Link it here...`"
2. In the name field, entered “Disable CMD” as the name for the new `GPO` and clicked **OK**.
3. Right-clicked the **Disable CMD** `GPO` under Sales `OU` and chose **Edit**.
4. In the `Group Policy Management Editor` window, at the left pane, navigated to **User Configuration > Policies > Administrative Templates > System**.
5. In the main pane, right-clicked on **Prevent access to the command prompt** and selected **Edit**.
6. In the next window, selected **Enabled**, clicked **Apply**, then **OK** to save the changes.

![Figure 6 - Prevent access to the command prompt 2](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/02-Server-Manager-Group-Policy-Object-Configuration/images/Figure06_prevent_access_to_the_command_prompt_2.png)

### Task 4: Disable Registry Editor

![Figure 7 - Prevent access to registry editing tools](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/02-Server-Manager-Group-Policy-Object-Configuration/images/Figure07_prevent_access_to_registry_editing_tools.png)

1. Right-clicked on the **Sales OU** folder and selected "`Create a GPO in this domain, and Link it here…`"
2. In the name field, entered “Disable Registry Editor” as the name for the new `GPO` and clicked **OK**.
3. Right-clicked the **Disable Registry Editor** `GPO` under the Sales `OU` and chose **Edit**.
4. In the left pane of the `Group Policy Management Editor` window, navigated to **User Configuration > Policies > Administrative Templates > System**.
5. In the main pane, right-clicked on **Prevent access to registry editing tools** and selected **Edit**.
6. In the next window, selected **Enabled**, clicked **Apply**, then **OK** to save the changes.

![Figure 8 - Prevent access to registry editing tools 2](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/02-Server-Manager-Group-Policy-Object-Configuration/images/Figure08_prevent_access_to_registry_editing_tools_2.png)

### Task 5: Disable Recycle Bin Icon

![Figure 9 - Remove Recycle Bin icon from desktop](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/02-Server-Manager-Group-Policy-Object-Configuration/images/Figure09_remove_recycle_bin_icon_from_desktop.png)

1. Right-clicked on the **Sales OU** folder and selected "`Create a GPO in this domain, and Link it here…`"
2. In the name field, entered “Disable Recycle Bin” as the name for the new `GPO` and clicked **OK**.
3. Right-clicked the **Disable Recycle Bin** `GPO` under the Sales `OU` and chose **Edit**.
4. In the left pane of the `Group Policy Management Editor` window, navigated to **User Configuration > Policies > Administrative Templates > Desktop**.
5. In the main pane, right-clicked on “**Remove Recycle Bin icon from desktop**” and selected **Edit**.
6. In the next window, selected **Enabled**, clicked **Apply**, then **OK** to save the changes.

![Figure 10 - Remove Recycle Bin icon from desktop 2](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/02-Server-Manager-Group-Policy-Object-Configuration/images/Figure10_remove_recycle_bin_icon_from_desktop_2.png)


### Task 6: Apply and Verify `GPO` Settings

![Figure 11 - Verify GPO Settings](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/02-Server-Manager-Group-Policy-Object-Configuration/images/Figure11_verify_gpo_settings.png)

1. Used the shortcuts to switch to the `Windows Client`. Opened `Command Prompt` (`CMD`) and executed the command `gpupdate /force` in the `CMD` window to update the `GPO` changes.
2. Initiated an RDP connection in the `Windows Client's` Desktop to "**Salesperson1 RDP**" and authenticated using Salesperson1’s credentials.
3. After the system reloaded, validated the new `GPO` rules applied by the Administrator user. Ensured error messages were received when attempting to access the `Command Prompt` (`CMD`), Control Panel, Registry Editor, and confirmed the `Recycle Bin` icon was absent from the desktop.

![Figure 12 - Verify GPO Settings 2](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/02-Server-Manager-Group-Policy-Object-Configuration/images/Figure12_verify_gpo_settings_2.png)

