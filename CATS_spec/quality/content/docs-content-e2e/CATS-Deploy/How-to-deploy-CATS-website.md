# How to deploy CATS to website

### Step1-2: Get the latest code of CATS
Firstly, we need to finish Step1 and Step2 in [Environment configuration](How-to-deploy-CATS-debug-machine.md#environment-configuration).

### Step3. Publish web project CEWebPortal
1. On **Solution Explorer** of **VS**, right-click the project name **CEWebPortal**, click **Publish…** on the pop right click menu.
2. On pop Publish Web window, Select the Connection section, set the Target location to the path that you want to put the published file in.
	- Path for Test: \\csicesvr\CATS_Deploy 
	- Path for Prod: \\contentqa_cats\Cats_deploy 
	![Publish Web Window](../../Images/Publish_Web_Window.png) 
3. Keep default on the Publish Web wizard, click "Publish" 
4. After publish success, restart the IIS on web deploy server(csicesvr)
    ![Publish Web Window](../../Images/IIS.png)
		
