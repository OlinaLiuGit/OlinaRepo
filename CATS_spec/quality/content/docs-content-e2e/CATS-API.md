# CATS API

## Triggering content validation run via API

- **Input parameters**: runname, createdBy, testCaseIds and testUrls
- **Output**: RunId in CATS
- **Request header**
    - **Method**: Post
    - **Request URL**: https://contentqacats.azurewebsites.net/api/ContentValidation/CreateRun_ForOPS

    **Parameters details**:
    
	|Field    |Required |Format   |Comment  |
	|---------|:--------:|---------|---------|
	|runName  |Y| string  |<=32 chars|
	|createdBy|Y| Domain\\alias |         |
	|testCaseIds |Y|  int array(split with ',' if multiple) | Support multiple testcases, you can get all the CATS cases info from [Get CATS test case API](#get-cats-test-case-info)  <br> <ul><li>Test case - "IsRequired: true" is required</li><li>Only active cases is allowed - "IsActive: true" </li> </ul>     |
	|testUrls    |Y|  Standard http(s) url, support docs only now |   Support multiple urls(split with ',' if multiple)    |
	|waitTimeMin  |N| int  |<=30(min)|
	|isSendMail   |N| Bool  |true/false|
	|notification_Subscribers|N|string|Email list for notification(split with ',' if multiple)|

### Step1: Get the CATS Portal access token in PostMan

If you want to call CATS API, you need to get the access token to CATS at first. 
1. In postman App(You can download PostMan App at: https://www.getpostman.com/), select **Authorization** 
![Get Token](../Images/GetToken.png)
2. Choose **Type: OAuth 2.0**
3. **Get New Access Token**, and in pop-up dialog fill like following, then click **Request Token** to request a new token
	- **Token Name**: whatever
	- **Grant type**: Client Credentials
	- **Access Token URL**: https://login.microsoftonline.com/72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token
	- **Client ID**: f85c7238-6754-424b-9a89-6345648a49ed
	- **Client Secret**: ******
	- **Scope**: Optional
	- **Client Authentication**: Optional
    ![Get Token](../Images/RequestToken.png)
4. After token request succeed, in the **MANAGER ACCESS TOKENS** windows, click **Use Token**. Screenshot as below:
![Use Token](../Images/UseToken.png)


> [!Note] 
> For security, we could not publish the **Client Secret**, if you need call CATS Portal API, you can contact [CATS Support](catssupport@microsoft.com) to get it. 

### Step2: Fill request body, send request and get response
After authoried in step1, input your request body with formatted json under section “Body” and send request
Request body:
- Option: raw, Json
- Request body format
    <pre>{
    "runName":"{your run name}",
    "createdBy":"{Domain\\alias}",
    "testCaseIds": "Id1, Id2, …",
    "testUrls":["URL1", "URL2"],
    "waitTimeMin": "Minute need to wait before CATS been trigger after create",
    "isSendMail": "true/false",
    "notification_Subscribers":["NotificationEmail1","NotificationEmail2"]
    }</pre>

    Screenshot for an example:
    ![Trigger run](../Images/CreateRun.png)


## Get CATS test case info
**Request header**
- **Method**: Get
- **Request URL**: https://contentqacats.azurewebsites.net/Api/TestCase/ContentValidation


## Get Example link white list
**Request header**
- **Method**: Get
- **Request URL**: https://contentqacats.azurewebsites.net/api/examplelink

## Code sample of CATS API 
Sample code as below:

```C#
using Newtonsoft.Json.Linq;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Microsoft.IdentityModel.Clients.ActiveDirectory;

namespace CATSApiSample
{
	class Program
	{
	static void Main(string[] args)
	{
		try
		{
		var client = CreateClient(new Uri("https://contentqacats-dev.azurewebsites.net/"));

		//Get test cases
        var activedTCIds = ListTestCases(client);
		
		//Create run
		client.DefaultRequestHeaders.Accept.Clear();
		client.DefaultRequestHeaders.Accept.Add(new MediaTypeWithQualityHeaderValue("application/json"));

		var response = client.PostAsJsonAsync("/Api/ContentValidation/CreateRun_ForOPS",
			new
			{
			runName = "test create from API",
			createdBy = "YourAlias",
			testUrls = new[] { "https://docs.microsoft.com/en-us/" },
			testCaseIds = "22, 3",
			notification_subscribers = new string[] { "YourEmailAddress" },
			isSendEmail = false,
			waitTimeMin = 0
			}).GetAwaiter().GetResult();

		var responseBody = response.Content.ReadAsStringAsync().GetAwaiter().GetResult();
		Console.WriteLine(JObject.Parse(responseBody)["runId"].ToString());
		Console.ReadLine();
		}
		catch (Exception ex)
		{
		Console.Write(ex.ToString());
		Console.ReadLine();
		}
	}

	static HttpClient CreateClient(Uri Baseurl)
	{
		var handler = new HttpClientHandler { UseDefaultCredentials = true };
		var client = new HttpClient(handler);
		client.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue("Bearer", GetS2SAccessToken().AccessToken);
		client.BaseAddress = Baseurl;
		client.Timeout = TimeSpan.FromMinutes(5);
		return client;
	}

	static int[] ListTestCases(HttpClient client)
	{
		var responseBody = client.GetStringAsync("/api/testcase/ContentValidation").GetAwaiter().GetResult();
		var ActivedtestCaseIds = JArray.Parse(responseBody).Where(x => Convert.ToInt32(x["IsActive"]) == 1).Select(x => Convert.ToInt32(x["Id"])).ToArray();
		return ActivedtestCaseIds;
	}

	static AuthenticationResult GetS2SAccessToken()
	{
		var Authority = "https://login.microsoftonline.com/72f988bf-86f1-41af-91ab-2d7cd011db47";
		var ClientId = "f85c7238-6754-424b-9a89-6345648a49ed";
		var ClientSecret = "xxxxxx"; //Contact CATS Support(catssupport@microsoft.com) to get ClientSecret
		var Resource = "f85c7238-6754-424b-9a89-6345648a49ed";

		var clientCredential = new ClientCredential(ClientId, ClientSecret);
		AuthenticationContext context = new AuthenticationContext(Authority, false);
		AuthenticationResult authenticationResult = context.AcquireTokenAsync(Resource, clientCredential).GetAwaiter().GetResult();
		return authenticationResult;
	}
	}
}
```
