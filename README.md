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

In this task, you will use the Azure portal to create a web app, and then you will test the app by using its public URL.

<br>

✅ If necessary, sign in to **🖥️ Windows 10 - RDP Jumpbox** as ***LabUser*** using ***Passw0rd!*** as the password.

- 💡 Select the ***Type Text*** icon to type the associated text into the virtual machine at the current cursor location.
<br>

<br>

✅ Open Microsoft Edge, and then sign in to http://portal.azure.com as ***admin-42241754*** using ***cDeC3e!0D@*** as the password.

- If you receive an error, select **Try again**.
<br>

<br>

✅ If prompted to take a tour of the Azure portal, select **Maybe later**.

<br>

✅ In the Azure portal, in the upper-left corner, select the **Show portal** menu icon.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Application-Insights-for-a-web-app/assets/172988970/9141f9ba-6014-40b3-9102-325b18b3edc3" height="8%" width="8%" alt="9"/><br />
<br>

<br>

✅ On the Azure portal menu, select **Create a resource** to display the Azure Marketplace.

<br>

✅ In the Popular Azure services list, select **Web App**.

<br>

✅ On the Create Web App blade, on the Basics page, in Resource Group, select **corp-datalod42241754**, and then in Name, enter ***web42241754***.

<br>

✅ In Publish, ensure that **Code** is selected, in Runtime stack, select **ASP.NET V4.8** (or the most recent version), in Operating System, ensure that **Windows** is selected, and then in Region, select **East US**.

<br>

✅ In App Service Plan, in Sku and size, select **Explore pricing plans**.

<br>

✅ On the Select App Service Pricing Plan blade, locate and select **Standard S1**, and then select **Select**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Application-Insights-for-a-web-app/assets/172988970/972bd4bf-f6bf-44ab-9a7d-dfd734176bf4" height="30%" width="30%" alt="9"/><br />
<br>

<br>

✅ On the Basics page, select **Next: Database**, and then select **Next : Deployment**.

<br>

✅ On the Deployment page, in Continuous deployment settings, ensure that **Disable** is selected, and then select **Next : Networking**.

- You will deploy code for the web app in an upcoming task.
<br>

<br>

✅ On the Networking page, in Enable network injection, ensure that **Off** is selected, and then select **Next : Monitoring**.

<br>

✅ On the Monitoring page, in Enable Application Insights, ensure that **No** is selected.

- You will enable Application Insights in an upcoming task.
<br>

<br>

✅ Select **Review + create**, review the configuration, and then select **Create** to deploy the web app.

- The web app deployment will take approximately 1–2 minutes to complete.
<br>

<br>

✅ When you are presented with a **Your deployment is complete** message, select **Go to resource** to display the web42241754 page.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Application-Insights-for-a-web-app/assets/172988970/0f02c7cb-79e1-4f76-9deb-f01737e8a31d" height="40%" width="40%" alt="9"/><br />
<br>

<br>

✅ On the web42241754 page, select the **URL** link to test the deployment.

- You should see the default home page of the web app.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Application-Insights-for-a-web-app/assets/172988970/609747c5-22d9-4c42-936b-06b42155a050" height="80%" width="80%" alt="9"/><br />
<br>


<br>

<br>

<h2>2️⃣ Deploy ASP.NET Code</h2>
<br>

In this task, you will deploy ASP.NET code to your web app, and then you will test the updated app by using the public URL of the web app.

<br>

✅ On the web42241754 resource menu, in Deployment, select **Deployment Center**.

<br>

✅ On the Deployment Center page, on the Settings page, select **SCM basic authentication is disabled for your app. Click here to go to your configuration settings to enable**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Application-Insights-for-a-web-app/assets/172988970/f6d0500b-d75f-4d22-b103-bce7eb6228eb" height="60%" width="60%" alt="9"/><br />
<br>

<br>

✅ On the Configuration blade, in Platform settings, in SCM Basic Auth Publishing Credentials, select **On**, and then on the command bar, select **Save**.

<br>

✅ On the Save changes blade, select **Continue**, and then close the **Configuration** blade.

<br>

✅ On the Deployment Center page, on the Settings page, in Source, select **External Git**.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Application-Insights-for-a-web-app/assets/172988970/3e458bb5-6263-4f5c-9687-b8cb6f64c453" height="50%" width="50%" alt="9"/><br />
<br>

<br>

✅ In External Git, in Repository, enter ***https://github.com/LODSContent/LODSOC_app-service-web-dotnet-get-started***, in Branch, enter ***main***, and then in Repository Type, ensure that Public is selected.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Application-Insights-for-a-web-app/assets/172988970/8efa718d-ea02-4fbf-bb91-5582099ac346" height="50%" width="50%" alt="9"/><br />
<br>

<br>

✅ On the command bar, select **Save** to initiate the deployment.

- It will take approximately 1–2 minutes for the new code to fully deploy.
<br>

<br>

✅ On the web42241754 resource menu, select **Overview**, and then select the **URL** link to display the updated version of the web app.
<p align="center">
<img src="https://github.com/franciscovfonseca/Configure-Application-Insights-for-a-web-app/assets/172988970/96ebae13-3bfa-47b6-9418-e85755362205" height="80%" width="80%" alt="9"/><br />

- If you do not see the updated page, refresh the browser.
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
