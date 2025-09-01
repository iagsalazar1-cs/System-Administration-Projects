# Windows Server Configuration

### Project Overview
This lab focuses on setting up a `Windows Server` domain and integrating a `Windows client`. This hands-on experience with `Windows Server` configuration simulates real-world scenarios in `Windows Server` administration.

### Goals
* Install and configure `Active Directory Domain Services` (`AD DS`) on `Windows Server`.
* Promote `Windows Server` to a domain controller.
* Configure the `Windows Client` to use the `Windows Server` as its preferred `DNS` server.
* Join the `Windows Client` to the domain.
* Verify the successful integration of the `Windows Client` into the domain.

### Task Summary
* **Task 1:** Install `Active Directory Domain Services` (`AD DS`): Open `Server Manager`, add `Roles and Features` selecting `Active Directory Domain Services`, and install the required features.
* **Task 2:** Promote `Windows Server` to a `Domain Controller`: Locate the notification flag, promote the server to a domain controller, configuring the forest name as `"cyber.local,"` and setting the administrator password.
* **Task 3:** Configure `DNS` Settings: Open `Command Prompt` (`CMD`) and execute the `ipconfig` command to check the server's `IP address`, navigate to the `Windows Client`, search for network adapter properties, select `Ethernet 3`, adjust the `IPv4` (`TCP/IPv4`) `DNS` settings, and enter the `Windows Server IP address` as the preferred `DNS` server.
* **Task 4:** Join `Windows Client` to the Domain: On the `Windows Client`, access the `"Rename this PC"` setting in the “about” page. Join the `"cyber.local"` domain using the provided administrator credentials (`cyber\administrator` and the specified password), and restart the `Windows Client`.
* **Task 5:** Verify Domain Integration: Navigate back to the `Windows Server`, use `Active Directory Users and Computers` to verify that the `Windows Client` is listed under the `"Computers"` tab.

### Step-by-Step Guide

---

### Task 1: Install Active Directory Domain Services (AD DS)

![Figure 1 - Install AD DS](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/01-Windows-Server-Configuration/images/Figure01_install_ad_ds.png)

1. On the `Windows Server`, opened the `Server Manager` and selected `Add Roles and Features`.
2. In the installation wizard, continued clicking `Next` until arriving at the `Server Roles` section.
3. In the `Server Roles` section, selected `Active Directory Domain Services`.
4. After selecting `Active Directory Domain Services`, added the necessary features from the new window and clicked `Add Features`.
5. Continued the installation process by clicking `Next` until the `Confirm installation` selection screen.
6. Clicked `Install` and waited for the installation to complete.

![Figure 2 - Install AD DS 2](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/01-Windows-Server-Configuration/images/Figure02_install_ad_ds_2.png)


### Task 2: Promote Windows Server to a Domain Controller

![Figure 3 - Promote to Domain Controller](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/01-Windows-Server-Configuration/images/Figure03_promote_to_domain_controller.png)

1. From the `Server Manager`, found the flag icon indicating a post-deployment notification. Clicked on the flag, then chose `"Promote this server to a domain controller"`.
2. In the wizard that appeared, selected `"Add a new forest"` and named it `cyber.local` at the `Root domain name` input and clicked `Next`.
3. Set the `Directory Services Restore Mode` (`DSRM`) password at the `Password` and `Confirm password` fields, and clicked `Next`.
4. Continued through the wizard by clicking `Next`, leaving all other settings as their default values until the `Install` button became available and clicked on it.
5. The server automatically restarted once the process completed, arriving at the `"Applying computer settings"` screen.

![Figure 4 - Promote to Domain Controller 2](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/01-Windows-Server-Configuration/images/Figure04_promote_to_domain_controller_2.png)

### Task 3: Configure DNS Settings

![Figure 5 - Configure DNS](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/01-Windows-Server-Configuration/images/Figure05_configure_dns.png)

1. Opened the `Command Prompt` (`CMD`) and executed `ipconfig` command to check the `IP address` of the `Windows Server`.
2. Used the shortcut to switch to the `Windows Client` and searched for the `Network & Internet Settings`. Selected the `Ethernet` tab at the left pane, then clicked `"Change adapter options"`.
3. Located `Ethernet 3`, right-clicked it, and went to `Properties`. In the `Networking` tab, selected `Internet Protocol Version 4` (`TCP/IPv4`) and clicked on `Properties`.
4. Selected `"Use the following DNS server addresses"` option and entered the `Windows Server's IP address` (obtained in the first step) in the `Preferred DNS server` field. Applied the changes by clicking `OK` and then `Close`.

![Figure 6 - Configure DNS 2](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/01-Windows-Server-Configuration/images/Figure06_configure_dns_2.png)

### Task 4: Join Windows Client to the Domain

![Figure 7 - Join Domain](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/01-Windows-Server-Configuration/images/Figure07_join_domain.png)

1. On the `Windows Client`, opened the `File Explorer` window from the taskbar, then right-clicked `"This PC"` and selected `Properties`.
2. At the right pane of the `About` window, click `"Rename this PC (advanced)"`, then clicked on `"Change"` to modify the computer name for the `Windows_Client`.
3. Selected `Domain` and entered `cyber.local` as input. Clicked `OK`, and in the pop-up window clicked `Yes`. When prompted for credentials, entered the domain administrator’s username and password.
4. After confirmation, was prompted to restart the computer. Clicked `"OK"`, closed all open windows, and choose `"Restart Now"`.

![Figure 8 - Join Domain 2](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/01-Windows-Server-Configuration/images/Figure08_join_domain_2.png)


### Task 5: Verify Domain Integration

![Figure 9 - Verify Domain Integration](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/01-Windows-Server-Configuration/images/Figure09_verify_integration.png)

1. Clicked on `"Tools"` in the top-right corner of the `Server Manager` dashboard.
2. Selected `"Active Directory Users and Computers"` from the drop-down menu.
3. In the left-side pane of the `Active Directory Users and Computers` window, expanded the domain tree and navigated to the `Computers` folder.
4. Checked for `Windows_Client` on the list of computers displayed on the right-side pane. Verified that `Windows_Client` is listed under the `Computers` tab of the `cyber.local` domain.

![Figure 10 - Verify Domain Integration 2](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/01-Windows-Server-Configuration/images/Figure10_verify_integration_2.png)
