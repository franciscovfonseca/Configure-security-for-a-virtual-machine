<br>

<p align="center">
<img width="500" src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/5795419a-3012-4a57-b4b0-155c2dd93fc7" alt="Microsoft Active Directory Logo"/>
<br>
<br>
<br>



<h1> Configure Security for a Virtual Machine</h1>
<br>

In this lab, you will **Configure Security for a Virtual Machine**.

1. First, you will **Create a Virtual Machine**.

2. Next, you will **Configure a Network Security Group**.

3. Finally, you will **Configure Security for the Virtual Machine**.
<br>

<br>

By default, a virtual network, which may contain virtual machines and services, is completely isolated for security reasons ➜ it is up to you to allow access as appropriate.

One way to allow access is to use **Network Security Groups (NSGs)**. 

A NSG allows you to specify **Firewall Rules** to Allow or Deny Access through Ports and Protocols.

<br>
<br>

<h2>1️⃣ Create an Azure Virtual Machine</h2>
<br>

### ✔️ In this task, you will Create a Virtual Machine to Test the Application Security.
<br>

<br>

◻️ On the Azure portal menu, select **Create a resource** to display the Azure Marketplace.

<br>

◻️ In Categories, select **Compute**, and then select **Virtual machine**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-security-for-a-virtual-machine/assets/172988970/4fe8c6ca-024d-4eb8-9803-c21b2f67112b" height="40%" width="40%" alt="9"/><br />
<br>

<br>

◻️ On the Create a virtual machine blade, on the Basics page:
<br>

- in Resource group, select **corp-datalod42241754**

- in Virtual machine name, enter ***🆃 WebVM1***

- and then in Region, ensure that **(US) East US** is selected

<br>

<br>

◻️ In Image, select **Windows Server 2019 Datacenter - Gen2**.

<br>

◻️ In Size, select **See all sizes**.

<br>

◻️ On the Select a VM size page, in VM Size, select ***🆃 B2ms***, and then select **Select**.

<br>

◻️ On the Basics page, in Username, enter ***🆃 AzureAdmin***, and then in Password and Confirm password, enter ***🆃 Az!42241754!***.
<br>
<br>

- 💡 You can press **Tab** to move between fields.
<br>

<br>

◻️ In Public inbound ports, select **None**, and then select **Next : Disks**.

<br>

◻️ On the Disks page, in OS disk type, select **Standard HDD**, and then select **Next : Networking**.

<br>

◻️ On the Networking page, review the default values, and then select **Next : Management**.

<br>

◻️ On the Management page, in Boot diagnostics, select **Disable**.

<br>

◻️ Select **Review + create**, and then review the specifications of the virtual machine.

<br>

◻️ Select **Create** to deploy the virtual machine.
<br>
<br>

- The deployment will take approximately 3–5 minutes.
<br>


<br>
<br>

<h2>2️⃣ Configure a Network Security Group</h2>
<br>

### ✔️ In this task, you will Configure a Network Security Group.
<br>

<br>

◻️ On the Azure portal menu, select **All services**, select **Networking** and then select **Network security groups**.

<br>

◻️ On the Network security groups page, select **WebVM1-nsg**.
<br>

- If the WebVM1-nsg network security group is not listed, refresh the page until it appears.
<br>

<br>

◻️ On the WebVM1-nsg Overview page, review the default inbound and outbound security rules for the network security group.

<br>

◻️ On the WebVM1-nsg resource menu, select **Inbound security rules**, and then on the command bar, select **Add** to add a rule.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-security-for-a-virtual-machine/assets/172988970/37a5f21f-6763-4ee0-81a6-8868ab21e5af" height="15%" width="15%" alt="9"/><br />
<br>

<br>

◻️ On the Add inbound security rule blade, in Destination port ranges, enter ***🆃 3389***, in Name, enter ***🆃 AllowAllRDP***, and then select **Add** to add the new inbound security rule.

- ⚠️ Wait for the new rule to be created.
<br>

<br>

◻️ On the Inbound security rules page, on the command bar, select **Refresh** to see the new rule.

<br>

◻️ On the Inbound security rules page, on the command bar, select **Add** to add another rule.

<br>

◻️ On the Add inbound security rule blade, in Destination port ranges, enter ***🆃 80,443***, in Name, enter ***🆃 AllowAllWeb***, and then select **Add**.

- ⚠️ Wait for the new rule to be created.
<br>

<br>

◻️ On the WebVM1-nsg resource menu, select **Network interfaces**, and then verify that there is a network security group associated to the network interface of **WebVM1**.

- The network interface name begins with ***🆃 webvm1***.
<br>

<br>

◻️ On the WebVM1-nsg resource menu, select **Subnets**, and then verify that there are no subnets displayed.
<br>


<br>
<br>

<br>

<h2>3️⃣ Configure Virtual Machine Security</h2>
<br>

### ✔️ In this task, you will Configure Security for a Virtual Machine.
<br>

1. First, you will **Connect to the Virtual Machine**.
2. Next, you will **Install IIS on the Virtual Machine** by using ***Windows PowerShell®***.
3. Finally, you will **Delete the AllowAllRDP Inbound Port Rule** for security reasons.
<br>

<br>

◻️ On the Azure portal menu, select **All resources**, and then select the **WebVM1** virtual machine.
<br>

- If the virtual machine has not deployed yet, refresh the page until it appears in the list.
<br>

<br>

◻️ On the WebVM1 resource menu, in Settings, select **Networking**.

<br>

◻️ Review the inbound port rules in the WebVM1-nsg network security group, and then in the **AllowAllRDP** rule, note the warning icon ⚠️
<br>

- You will correct the warning in an upcoming task.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-security-for-a-virtual-machine/assets/172988970/d6482a5a-6292-48aa-893e-a2a731863c95" height="80%" width="80%" alt="9"/><br />
<br>

<br>

◻️ On the WebVM1 resource menu, select **Overview**.

◻️ On the command bar, select **Connect**, and then select **RDP**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-security-for-a-virtual-machine/assets/172988970/cfd8f133-4fec-481d-abee-c7e2dd7edf60" height="40%" width="40%" alt="9"/><br />
<br>

<br>

◻️ Select **Download RDP File**.

<br>

◻️ Open the RDP file, and then select **Connect**.

<br>

◻️ In the Enter your credentials window, in User name, enter ***🆃 AzureAdmin***, in Password, enter ***🆃 Az!42241754!***, and then select OK.

<br>

◻️ In the Remote Desktop Connection warning message, select **Yes** to connect.

- You may need to wait for the desktop profile to initialize.
<br>

<br>

◻️ If prompted to allow network discovery, select **No**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-security-for-a-virtual-machine/assets/172988970/03876040-2c93-4a01-bd93-4a2fa84f6e62" height="50%" width="50%" alt="9"/><br />
<br>

<br>

◻️ Wait for Server Manager to start, and then close **Server Manager**.

<br>

◻️ In the Remote Desktop Connection window, on the Start menu, select **Windows PowerShell**.

- You may need to scroll down in the Remote Desktop Connection window to see the Windows Start button.
<br>

<br>

◻️ At the PowerShell command prompt, run the following command to install IIS on the virtual machine:


```commandline
Install-WindowsFeature -name Web-Server -IncludeManagementTools
```
<br>

<br>

◻️ Wait for the IIS installation to finish.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-security-for-a-virtual-machine/assets/172988970/7f39e53b-3f9f-4d22-b6a7-d6fecdbe864f" height="50%" width="50%" alt="9"/><br />
<br>

<br>

- The IIS installation will take approximately 1–2 minutes.
<br>

<br>

◻️ Close the **Remote Desktop Connection** window, and then select **OK** to disconnect.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-security-for-a-virtual-machine/assets/172988970/614b0f2f-7518-453c-a241-c12faaf5fbf3" height="60%" width="60%" alt="9"/><br />
<br>

<br>

◻️ On the WebVM1 resource menu, select **Overview**, locate the **Public IP address**, and then type it into the following **WebVM1 Public IP Address** text box:
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-security-for-a-virtual-machine/assets/172988970/a5557e42-7da0-4f6a-b643-987d1830a735" height="40%" width="40%" alt="9"/><br />
<br>

<br>

◻️ Open a new browser window, and then go to the public IP address of WebVM1 at ***🆃 http://<*PublicIP*>***.

- You should see the default IIS web page. This verifies that web traffic has been routed correctly by using a network security group.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-security-for-a-virtual-machine/assets/172988970/c220e2bf-3f88-4deb-866f-d60f6bf71565" height="60%" width="60%" alt="9"/><br />
<br>

<br>

◻️ Close the browser window that contains the default IIS web page.

<br>

◻️ On the WebVM1 resource menu, in Settings, select **Networking**.

<br>

◻️ Review the inbound port rules.

- Note the warning symbol beside the AllowAllRDP rule.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-security-for-a-virtual-machine/assets/172988970/75e284e8-dd14-4a2a-a274-bf211b40feec" height="60%" width="60%" alt="9"/><br />
<br>

<br>

◻️ Select the **AllowAllRDP** inbound port rule to view the specifications of the rule.

◻️ On the AllowAllRDP blade, review the warning message at the bottom of the page.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-security-for-a-virtual-machine/assets/172988970/c5d75c22-1f5f-43d8-a167-9be4a60f430a" height="60%" width="60%" alt="9"/><br />
<br>

<br>

◻️ On the command bar, select **Delete**, and then when prompted, select **Yes** to delete the security rule.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-security-for-a-virtual-machine/assets/172988970/c8ee4c30-983b-4310-a1df-68c8e49fce4c" height="60%" width="60%" alt="9"/><br />
<br>

- Wait for the rule to be deleted. It may take a few minutes for the change to take effect.
<br>


<br>
<br>

<br>

<h2>4️⃣ Test Virtual Machine Security</h2>
<br>

### ✔️ In this task, you will Verify that RDP Access is no longer allowed but that HTTP Access remains.
<br>

<br>

◻️ On the WebVM1 resource menu, select **Overview**, select Connect, and then select **RDP**.

<br>

◻️ Select **Download RDP File**, open the RDP file, and then select **Connect**.

- This should now fail with an error. If it does not, cancel, and then try again. The deleted rule may take a few minutes to take effect.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-security-for-a-virtual-machine/assets/172988970/397621da-1638-45dc-b67b-827e05978d27" height="60%" width="60%" alt="9"/><br />
<br>

<br>

◻️ Select **OK** to dismiss the error message.

<br>

◻️ Open a new browser window, and then go to the public IP address of WebVM1 at ***🆃 http://<*PublicIP*>***.

- You should see the default IIS web page again. The AllowAllWeb rule remains in effect.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-security-for-a-virtual-machine/assets/172988970/054418fc-c029-4eeb-a956-d1d70be23ce8" height="60%" width="60%" alt="9"/><br />
<br>

<br>

◻️ Close the browser window that contains the default IIS web page.



<br>
<br>
<br>
