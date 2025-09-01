# Windows Server DNS and DHCP Configuration

### Project Overview
This project involves configuring and managing two fundamental network services on a `Windows Server`: Domain Name System (`DNS`) and Dynamic Host Configuration Protocol (`DHCP`). The `DNS` portion focuses on creating and validating `DNS` records, specifically **A** and **CNAME** records. The `DHCP` portion involves installing and authorizing the `DHCP` server role, while creating and activating a new **IPv4 scope**.

### Goals
* Gain practical experience in configuring and managing `DNS` on a `Windows Server`.
* Understand how to create and validate `DNS` **A** and **CNAME** records.
* Learn how to install and authorize the `DHCP Server` role on a `Windows Server`.
* Understand how to create and activate a `DHCP IPv4` scope with specific settings.

### Task Summary
* **Task 1: Check Client IP Address:** Navigate to the `Windows Client` machine and check its IP address using the `ipconfig` command.
* **Task 2: Create DNS A Record on Server:** Switch to the `Windows Server` and create a new `DNS A` record called `test-client`. Associate this A record with the `Windows Client's IP` address and add it to the `cyber.local` Forward Lookup Zone.
* **Task 3: Verify A Record on Client:** Return to the `Windows Client`. In the `CMD` window, utilize the `nslookup` command to verify the successful creation and configuration of the new A record.
* **Task 4: Create CNAME Record on Server:** Use the shortcuts and switch to the `Windows Server`. Using `DNS` management, establish a new `CNAME` record labeled `my-favorite-client` and associate it with the `FQDN` `test-client.cyber.local`.
* **Task 5: Verify CNAME Record on Client:** Navigate to the `Windows Client` instance. Open the `Command Prompt` (`CMD`) and utilize the `nslookup` command to validate the `my-favorite-client CNAME` record.
* **Task 6: Install DHCP Server Role:** Install the `DHCP Server` role on the `Windows Server`.
* **Task 7: Authorize DHCP Server:** Authorize the `DHCP` server.
* **Task 8: Add and Activate a new IPv4 scope:** Name it **Cyber Scope** with its IP address range, subnet mask, and exclusions.

### Step-by-Step Guide

---

### Task 1: Check Client IP Address

![Figure 1 - Check Client IP Address](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/03-Configuring-DNS-and-DHCP-in-Windows-Server/images/Figure01_check_client_ip_address.png)

1. Navigate to the `Windows Client` machine and check its IP address using the `ipconfig` command.
2. On the `Windows Client`, open `Command Prompt` (`CMD`) and execute the `ipconfig` command to check the IP address of the `Windows Client`.

![Figure 2 - Check Client IP Address 2](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/03-Configuring-DNS-and-DHCP-in-Windows-Server/images/Figure02_check_client_ip_address_2.png)

---

### Task 2: Create DNS A Record on Server

![Figure 3 - Create DNS A Record](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/03-Configuring-DNS-and-DHCP-in-Windows-Server/images/Figure03_create_dns_a_record.png)

1. Switch to the `Windows Server` and create a new `DNS A` record called `test-client`. Associate this A record with the `Windows Client's IP` address and add it to the `cyber.local` Forward Lookup Zone.
2. In the `Server Manager`, navigate to **Tools** and select **DNS**.
3. In the `DNS Manager`, progressively expand the **WINDOWS_SERVER** in the left-side pane, open **Forward Lookup Zones** to display `cyber.local`.
4. Right-click on `cyber.local` and select **New Host (A or AAAA)...**.
5. For the name, input `test-client` and designate the `Windows Client's IP` address.
6. Click **Add Host** and press **OK** when the completion prompt appears, and then **Done**.

![Figure 4 - Create DNS A Record 2](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/03-Configuring-DNS-and-DHCP-in-Windows-Server/images/Figure04_create_dns_a_record_2.png)

---

### Task 3: Verify A Record on Client

![Figure 5 - Verify A Record](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/03-Configuring-DNS-and-DHCP-in-Windows-Server/images/Figure05_verify_a_record.png)

1. Return to the `Windows Client`. In the `CMD` window, utilize the `nslookup` command to verify the successful creation and configuration of the new **A** record.
2. Opened the `Command Prompt` (`CMD`) window and executed the following command: `nslookup test-client.cyber.local`.
3. Observe that the server name in the output is **UnKnown**.

![Figure 6 - Verify A Record 2](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/03-Configuring-DNS-and-DHCP-in-Windows-Server/images/Figure06_verify_a_record_2.png)

---

### Task 4: Create CNAME Record on Server

![Figure 7 - Create CNAME Record](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/03-Configuring-DNS-and-DHCP-in-Windows-Server/images/Figure07_create_cname_record.png)

1. Use the shortcuts and switch to the `Windows Server`. Using `DNS` management, establish a new `CNAME` record labeled `my-favorite-client` and associate it with the `FQDN` `test-client.cyber.local`.
2. In the `Server Manager`, click on **Tools**, then select **DNS**.
3. Navigate to **WINDOWS_SERVER > Forward Lookup Zones > cyber.local**.
4. Right-click on `cyber.local`, choose **New Alias (CNAME)...**. In the Alias name field, input `my-favorite-client`.
5. Input `test-client.cyber.local` into the "Fully qualified domain name for target host" field. Click **OK** to finalize the process.

![Figure 8 - Create CNAME Record 2](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/03-Configuring-DNS-and-DHCP-in-Windows-Server/images/Figure08_create_cname_record_2.png)

---

### Task 5: Verify CNAME Record on Client

![Figure 9 - Verify CNAME Record](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/03-Configuring-DNS-and-DHCP-in-Windows-Server/images/Figure09_verify_cname_record.png)

1. Navigate to the `Windows Client` instance. Open the `Command Prompt` (`CMD`) and utilize the `nslookup` command to validate the `my-favorite-client CNAME` record.
2. Opened the `Command Prompt` (`CMD`) and executed the following command: `nslookup my-favorite-client.cyber.local`.
3. The output displayed `my-favorite-client.cyber.local` in the aliases field, confirming the successful creation of the `CNAME` record.

![Figure 10 - Verify CNAME Record 2](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/03-Configuring-DNS-and-DHCP-in-Windows-Server/images/Figure10_verify_cname_record_2.png)

---

### Task 6: Install DHCP Server Role

![Figure 11 - Install DHCP Server Role](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/03-Configuring-DNS-and-DHCP-in-Windows-Server/images/Figure11_install_dhcp_role.png)

1. Select **Add Roles and Features** in the `Server Manager`.
2. In the installation wizard pop-up, click **Next** until you arrive at the **Server Roles** section.
3. In the **Server Roles** section, select **DHCP Server**. Upon selecting `DHCP Server`, select **Add Features** and on the pop-up window **Continue**.
4. Continue the installation process by clicking **Next** until the **Confirm installation selection** screen.
5. Finally, click **Install**. Once completed, click **Close**.

![Figure 12 - Install DHCP Server Role 2](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/03-Configuring-DNS-and-DHCP-in-Windows-Server/images/Figure12_install_dhcp_role_2.png)

---

### Task 7: Authorize DHCP Server

![Figure 13 - Authorize DHCP Server](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/03-Configuring-DNS-and-DHCP-in-Windows-Server/images/Figure13_authorize_dhcp_server.png)

1. On the `Server Manager` window, navigate to the top-right corner and click the **Notifications** flag icon to view pending notifications.
2. Click the **Complete DHCP configuration** option within the notifications.
3. Upon reaching the authorization window, select **Commit**.
4. Ensure that the server administrator's credentials are being used for this procedure, then click **Close**.

![Figure 14 - Authorize DHCP Server 2](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/03-Configuring-DNS-and-DHCP-in-Windows-Server/images/Figure14_authorize_dhcp_server_2.png)

---

### Task 8: Add and Activate a new IPv4 scope

![Figure 15 - Add New IPv4 Scope](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/03-Configuring-DNS-and-DHCP-in-Windows-Server/images/Figure15_add_new_ipv4_scope.png)

1. Navigate to **Tools** and select **DHCP** to access the `DHCP` management tool. Inside `DHCP`, expand the node `Windows_Server.cyber.local` at the left-side pane. Expand and right-click **IPv4**, and choose "**New Scope...**".
2. In the `New Scope Wizard` window, click **Next**, then name the scope **Cyber Scope**, and click **Next** again.
3. Define the IP range as `192.168.0.1--192.168.0.200`, and set the subnet mask to `255.255.255.0`, and click **Next**. Specify the exclusion range: `192.168.0.1 -- 192.168.0.10`, click **Add** and **Next**.
4. Configure the lease duration to last **7 days**, and click **Next**.
5. Continue with the setup process until the section for **Domain Name and DNS Servers**. In this section, specify the parent domain as `cyber.local`. Assign the IP address of the domain to `192.168.0.1`. Click the **Add** button, **Yes** to confirm, and **Next**.
6. Opt to activate the scope immediately.
7. Complete the process and exit the wizard. Finally, revisit the `DHCP` management tool to confirm your scope's successful creation and activation.

![Figure 16 - Add New IPv4 Scope 2](https://github.com/iagsalazar1-cs/System-Administration-Projects/blob/main/03-Configuring-DNS-and-DHCP-in-Windows-Server/images/Figure16_add_new_ipv4_scope_2.png)

