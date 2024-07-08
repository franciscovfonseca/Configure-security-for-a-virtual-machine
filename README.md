<br>

<p align="center">
<img width="500" src="https://github.com/franciscovfonseca/Configure-Virtual-Network-Connectivity-by-Using-Peering/assets/172988970/5795419a-3012-4a57-b4b0-155c2dd93fc7" alt="Microsoft Active Directory Logo"/>
<br>
<br>
<br>



<h1> Configure Security for a Virtual Machine</h1>
<br>

In this exercise, you will **Configure Security for a Virtual Machine**.

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

In this task, you will create a virtual machine to test the application security.

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

- in Virtual machine name, enter ***WebVM1***

- and then in Region, ensure that **(US) East US** is selected

<br>

<br>

◻️ In Image, select **Windows Server 2019 Datacenter - Gen2**.

<br>

◻️ In Size, select **See all sizes**.

<br>

◻️ On the Select a VM size page, in VM Size, select ***B2ms***, and then select **Select**.

<br>

◻️ On the Basics page, in Username, enter ***AzureAdmin***, and then in Password and Confirm password, enter ***Az!42241754!***.
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

- The deployment will take approximately 3–5 minutes. You can continue to the next task while you wait for the deployment to complete.
<br>


<br>
<br>

<h2>2️⃣ Configure a Network Security Group</h2>
<br>

In this task, you will configure a network security group.

<br>

◻️ On the Azure portal menu, select All services, select Networking, and then select Network security groups.

<br>

◻️ On the Network security groups page, select WebVM1-nsg.
<br>

- If the WebVM1-nsg network security group is not listed, refresh the page until it appears.

<br>

◻️ On the WebVM1-nsg Overview page, review the default inbound and outbound security rules for the network security group.

- The default security rules allow network traffic from within the same virtual network and from a load balancer but prevent access from all other sources.

<br>

◻️ On the WebVM1-nsg resource menu, select Inbound security rules, and then on the command bar, select Add to add a rule.

The Add rule option

◻️ On the Add inbound security rule blade, in Destination port ranges, enter 3389, in Name, enter AllowAllRDP, and then select Add to add the new inbound security rule.

- Wait for the new rule to be created.

◻️ On the Inbound security rules page, on the command bar, select Refresh to see the new rule.

◻️ On the Inbound security rules page, on the command bar, select Add to add another rule.

◻️ On the Add inbound security rule blade, in Destination port ranges, enter 80,443, in Name, enter AllowAllWeb, and then select Add.

- Wait for the new rule to be created.

◻️ On the WebVM1-nsg resource menu, select Network interfaces, and then verify that there is a network security group associated to the network interface of WebVM1.

- The network interface name begins with webvm1.

◻️ On the WebVM1-nsg resource menu, select Subnets, and then verify that there are no subnets displayed.

- When a network security group is associated to a subnet, its rules apply to all virtual machines in that subnet. When a network security group is associated to a network interface, its rules only apply to that specific network interface on that virtual machine.





◻️ In Categories, select **Compute**, and then select **Virtual machine**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-security-for-a-virtual-machine/assets/172988970/4fe8c6ca-024d-4eb8-9803-c21b2f67112b" height="50%" width="50%" alt="9"/><br />
<br>

<br>

◻️ On the Create a virtual machine blade, on the Basics page:
<br>

- in Resource group, select **corp-datalod42241754**

- in Virtual machine name, enter ***WebVM1***

- and then in Region, ensure that **(US) East US** is selected

<br>

<br>

◻️ In Image, select **Windows Server 2019 Datacenter - Gen2**.

<br>

◻️ In Size, select **See all sizes**.

<br>

◻️ On the Select a VM size page, in VM Size, select ***B2ms***, and then select **Select**.

<br>

◻️ On the Basics page, in Username, enter ***AzureAdmin***, and then in Password and Confirm password, enter ***Az!42241754!***.
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

- The deployment will take approximately 3–5 minutes. You can continue to the next task while you wait for the deployment to complete.
<br>


<br>
<br>

<h2>3️⃣ Configure Application Insights</h2>
<br>

In this task, you will configure Application Insights.

<br>

✅ On the web42241754 resource menu, in Settings, select **Application Insights**, and then select **Turn on Application Insights**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Application-Insights-for-a-web-app/assets/172988970/dc2aa394-96f3-4cf6-953a-d87b8518c703" height="30%" width="30%" alt="9"/><br />
<br>

<br>

✅ In New resource name, ensure that the value is set to ***web42241754***.

<br>

✅ In Log Analytics Workspace, select **laws-42241754 [eastus]**, and then select **Apply**.

<br>

✅ If prompted to Apply monitoring settings, select **Yes**.

- You may have to wait 1–2 minutes for Application Insights to be fully enabled.

✅ On the Application Insights page, select **View Application Insights data**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Application-Insights-for-a-web-app/assets/172988970/80f4f372-db8c-4a2d-bd72-dd9c2ae5dbaa" height="40%" width="40%" alt="9"/><br />
<br>

<br>

✅ On the web42241754 page, on the Overview page, on the command bar, select **Application Dashboard**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Application-Insights-for-a-web-app/assets/172988970/19cc7318-2c5c-4fb3-be35-251bcedb9b86" height="30%" width="30%" alt="9"/><br />
<br>

<br>

✅ On the web42241754 Dashboard, select the **Live Stream** tile to view the Live metrics page.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Application-Insights-for-a-web-app/assets/172988970/b31f3215-683a-458d-b650-78ba64723e4b" height="10%" width="10%" alt="9"/><br />
<br>

<br>

- If the Live metrics page is not initialized, refresh or restart the browser. It may take several minutes for Live Metrics to be initialized.

✅ In a new browser window, go to the URL for the web app at ***https://web42241754.azurewebsites.net***.

<br>

✅ Verify that the application appears, and then refresh the browser five times to generate multiple requests.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Application-Insights-for-a-web-app/assets/172988970/6b2a7550-fb10-4054-9520-40dcae68e62b" height="60%" width="60%" alt="9"/><br />
<br>

<br>

✅ To generate a failed request, go to ***https://web42241754.azurewebsites.net/badrequest*** to access a bad URL for the web app, and then close the new browser window.

<br>

✅ Switch to the **Live metrics** page to view the real-time metrics.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Application-Insights-for-a-web-app/assets/172988970/8cf9bd1e-75e0-4e33-a1be-5abf8f967e38" height="80%" width="80%" alt="9"/><br />
<br>

<br>

✅ On the Live metrics page, if needed, select **<< Show document stream** to see the Sample telemetry pane on the right.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Application-Insights-for-a-web-app/assets/172988970/c77ecc11-69cf-448e-b07c-1741517f13f6" height="50%" width="50%" alt="9"/><br />
<br>

<br>

✅ On the Sample telemetry pane, select **Request** to see more detail about the failed request, and then select **Exception** to see more detail about the resulting exception for troubleshooting.

You can select and drag the vertical sizing control to view more detail.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Application-Insights-for-a-web-app/assets/172988970/22472428-6c10-4edc-bfc3-359b308674c5" height="50%" width="50%" alt="9"/><br />
<br>

<br>

✅ Close the **Live metrics** page to return to the web42241754 Dashboard.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Application-Insights-for-a-web-app/assets/172988970/7a75ce1c-d6ef-4ec9-8f71-f5ff09f7e941" height="50%" width="50%" alt="9"/><br />
<br>

<br>

✅ Select **UTC Time: Past 24 hours**, in Time range, select **Past 30 minutes**, and then select **Apply**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Application-Insights-for-a-web-app/assets/172988970/514624e2-bf62-4b36-a7b4-8bf1dc10daeb" height="45%" width="45%" alt="9"/><br />
<br>

<br>

✅ On the web42241754 Dashboard , select **Save**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Application-Insights-for-a-web-app/assets/172988970/9a6844be-bc6c-424e-913c-2165e2c5b5e9" height="40%" width="40%" alt="9"/><br />
<br>


- It may take a few minutes for telemetry to be updated on the dashboard.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Application-Insights-for-a-web-app/assets/172988970/088e9245-00d6-4bd3-b13e-77fb4b3e7629" height="80%" width="80%" alt="9"/><br />
<br>



<br>
<br>
<br>
