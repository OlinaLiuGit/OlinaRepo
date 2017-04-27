# How to deploy a test machine

In this section:
* [Update test runner](#update-test-runner)
* [Deploy test runner on new machine](#deploy-test-runner)

## <a id='update-test-runner'></a>Update test runner

### Step1-2: Get the latest code of CATS
Firstly, we need to finish Step1 and Step2 in [Environment configuration](How-to-deploy-CATS-debug-machine.md#environment-configuration).
	
### Step3: Copy the debug files into share path
Copy all build files under debug folder to server machine(eg: csicesvr) folder(eg: E:\CATS\TestRunner\Latest)
	
### Step4: Deploy the test runner on CATS server
The CATS deploy environment refer to CATS Deploy environment, below is deploy steps:
1. Stop CATS Website IIS. 
Launch the **IIS(Internet Information Services(IIS) Manager)** on **CATS** web site deploy server(Test site: csicesvr, Prod site: contentqa_cats), select the **CATS** Site, click in Stop under **Manage Website** section.
2. Open CATS(develop: http://csicesvr/CheckResults Prod: http://contentqa_cats/CheckResults), Search with keyword "Running" if there CATS runs are running, you should **Abort** it first.
3. Log on **CATS** servers with account: **Redmond\APEXTest**.
4. Open **CATS** runner file path (For Test: C:\CATS_Test, For Prod: C:\CATS_Prod)
5. Run **CATSRunnerCopy.bat** as administrator.
6. After the bat script execute completed, the Runner should be opened.
7. Make sure the **CATS** runner execute account is login.
Execute the following tool: C:\CATS_Test\SeleniumTestSeleniumTest.exe, input the Docs stage site(e.g., https://review.docs.microsoft.com/en-us/， https://ppe.docs.microsoft.com/en-us/) if it jump to login page, you should login with account **Redmond/apextest**.
8. Restart the run which abort on step 2
Execute the following SQL update statement:
```
Update ExecutionConfiguration set status = 1 where runid = {Runid(which Abort in step2)}
```
9. Kick off a run on UI, verify the runner could run normally.
	

## <a id='deploy-test-runner'></a>Deploy test runner on new machine

### Step1-2: Get latest build files of CATS TestRunner
Firstly, we need finish the Step1-2 in [Update test runner](#update-test-runner)

### Step3: Copy the debug files into test machine
Copy all build files under debug folder to test machine folder(eg: C:\CATS_Test\TestRunner\)

### Step4: Update the configure file
Edit the configure file(e.g., C:\CATS_Test\TestRunner\TestRunner.exe.config)
- Check connection in **TestRunner.exe.config** under **TestRunner**, update the connect string text if need. For create new DB you can refer to [How to deploy CATS DB](How-to-deploy-CATS-DB.md)

```
<connectionStrings>
    <add name="ContentDataContext" connectionString="Data Source={database srever name};Initial Catalog={database name};Integrated Security=True;MultipleActiveResultSets=true" providerName="System.Data.SqlClient" />
</connectionStrings>
```

- Update the value of MachineName(If the Machine name not exist in Machine table of Database, you need to insert it into DB, refer to [How to deploy CATS DB](How-to-deploy-CATS-DB.md) Step6: Add the test machine name into Machine table of DataBase)

### Step5: Startup test runner
Run **TestRunner.exe** as administrator
