# CATS API

## Get the CATS Portal access token in PostMan
You can download PostMan App at: https://www.getpostman.com/
1. In postman, select **Authorization** 
2. Choose **Type: OAuth 2.0**
3. **Get New Access Token**, and in pop-up dialog fill like following, and request a new token
	- **Token Name**: whatever
	- **Grant type**: Client Credentials
	- **Access Token URL**: https://login.microsoftonline.com/72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token
	- **Client ID**: ******
	- **Client Secret**: ******
	- **Scope**: Optional
	- **Client Authentication**: Optional
4. Close the result windows, in the dropdown list **Available Tokens** choose the one you just create.
5. Add Authorization to **Request Headers**
6. **Preview Request** and click **Send** to make your request, if authentication is successful, the API shows a 200/OK response.

> [!Note] 
> For security, we could not publish the Client ID and Client Secret, if you need CATS Portal access token, you can access [CATS Support](catssupport@microsoft.com) to get them. 

## CATS API for triggering run
### Goals
Triggering CATS run via call CATS API

### API
* **Input parameters**: runname, createdBy, testCaseIds and testUrls
* **Output**: RunId in CATS
* **Request URL**: https://contentqacats-dev.azurewebsites.net/api/testcase/ContentValidation/CreateRun_ForOPS
* **HttpMethod**: Post

### Via PostMan call CAPS API
1. On **Authentication** section of PostMan, in the dropdown list **Available Tokens** chose the one you created for CATS portal access.
2. Enter request URL
    - **HttpMethod**: *Post*
    - **URL**: mentioned in [API](#api) part
3. Enter request body
    - Click **Body**, select **raw** and **JSON(application/json)**
    - Input Request body with **JSON** format
    
	|Field    |Required |Format   |Comment  |
	|---------|:--------:|---------|---------|
	|runName  |Y| string  |<=32 chars|
	|createdBy|Y| Domain\\alias |         |
	|testCaseIds |Y|  string(split with ',' if multiple)       | Support multiple testcases, you can get all the CATS cases info from [Get CATS test case list](#get-cats-test-cases-list)  <br> <ul><li>Test case - "IsRequired: true" is required</li><li>Only active cases is allowed - "IsActive: true" </li> </ul>     |
	|testUrls    |Y|  Standard http(s) url, support docs only now |   Support multiple urls      |
	|waitTimeMin  |N| string  |<=30(min)|
	|isSendMail   |N| Bool  |true/false|
	|notification_Subscribers|N|string|Email list for notification|

	- Request body format
	<pre>{
	"runName":"{your run name}",
	"createdBy":"{Domain\\alias}",
	"testCaseIds": "CATS test CaseId1, CATS test CaseId2, …",
	"testUrls":["URL1", "URL2"],
	"waitTimeMin": "Minute need to wait before CATS been trigger after create ",
	"isSendMail": "true/false",
	"notification_Subscribers":["NotificationEmail1","NotificationEmail2"]
	}</pre>
	
	- Request body example
	<pre>{
	"runName":"testOps",
	"createdBy":"Redmond\\APEXTest",
	"testCaseIds": "22,3",
	"testUrls":["https://docs.microsoft.com/en-us/", "https://docs.microsoft.com/en-us/windows/"],
	"waitTimeMin": "0",
	"isSendMail": "true",
	"notification_Subscribers":["APEXTest@microsoft.com"]
	}</pre>
	
4. Click **Send**, runid and resultUrl(report page url) will returned

## Get test case API
Get CATS test case API:
- **HttpMethod**: Get
- **Request URL**: 
	- Content Calidation: https://contentqacats.azurewebsites.net/Api/TestCase/ContentValidation
	- Protocol Validation: https://contentqacats.azurewebsites.net/Api/TestCase/ProtocolValidation

## Get Example link API
Get Example link white list API:
- **HttpMethod**: Get
- **Request URL**: https://contentqacats.azurewebsites.net/api/examplelink

## Get cookie API
Get Docs site cookie API:
- **HttpMethod**: Get
- **Request URL**: https://contentqacats.azurewebsites.net/api/cookie

## Via Code call CAPS API
Sample code for call CATS test case API and call create run API:

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
		Console.WriteLine("All Test Cases:");
		foreach (var c in ListTestCases(client))
			Console.WriteLine(c);

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
		var ClientId = "xxxxxx";
		var ClientSecret = "xxxxxx";
		var Resource = "xxxxxx";

		var clientCredential = new ClientCredential(ClientId, ClientSecret);
		AuthenticationContext context = new AuthenticationContext(Authority, false);
		AuthenticationResult authenticationResult = context.AcquireTokenAsync(Resource, clientCredential).GetAwaiter().GetResult();
		return authenticationResult;
	}
	}
}
```
