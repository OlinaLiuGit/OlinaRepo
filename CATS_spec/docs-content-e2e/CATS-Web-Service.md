# CATS Web Service for broken links check
In this article
* [Contacts](#contacts)
* [Overview](#overview)
* [Functional Requirements](#requirement)
* [Call Web Service via UI tool or code](#usage)

## <a id='contacts'></a> Contacts
|Role|Name; Alias|
|-----|----------|
|Program Manager|Ke Xu (kexu@microsoft.com)|
|Developer|Bin Zhou (v-bzho@microsoft.com)|
|Quality|cpebystest@microsoft.com;<br>Kalyan C Kesireddy(kalyanke@microsoft.com)|

## <a id='overview'></a>Overview
### Goals

* To enable CATS and SkyEye get broken links with input url list
* Provide high accuracy rate and performance

### Dependencies and Risks
* The input urls count of this web service is limited to 1000
* The performance of the web service is depend on network and host machine performance

## <a id='requirement'></a> Functional Requirements
List the requirements that the web service should satisfy in order of priority:
|Must-Have Requirements (P1)|Desired Requirements (P2 – P3)|
|--------|-----------|
|Ability to handle any exception|Able to export outputs to a local file or database|
|Ability to output accurate broken links|Host on Azure web service|
|Ability to provide high performance||

## <a id='usage'></a> Usage
### <a id='host'></a> Host
The web service access url would be: http://10.213.224.35/api/link/getbrokenlink

### Call
User could call the web service either via UI tool or via code

* Via UI Tool, recommended tool is Chrome [PostMan](https://www.getpostman.com/), it’s a Chrome app that operation easily
    1. Launch **PostMan** from Chrome (Open blank page in chrome, click Apps in the upper left corner then click PostMan)
    2. Entry access url mentioned in [Host](#host) part. Select *HttpMethod* as **Post**
    3. Click Body, select **raw** and **JSON(application/json)**
    4. In request body, input url list with **JSON** format.
        + Single Input Url
            - Format: ["URL1"] 
		    - For example ["https://docs.microsoft.com/en-us/"]
        + Multiple input URLs, the input urls count of this web service is limited to 1000.
            - Format: ["URL1","UrL2","URL3"] 
		    - For example
    ```
    ["https://docs.microsoft.com/es-es/windows/manage/group-policies-for-enterprise-and-education-editions",https://docs.microsoft.com/en-us/windows-server-essentials/use/work-remotely-in-windows-server-essentials"]
    ```

    5. Click **Send** to get output broken links
    ![Call Web Service Througn PostMan image](../Images/Call_Web_Service_Througn_PostMan.png)
    6. Check Result
        In response body, select Json format.
        - **Url**: the request URL        
        - **BrokenLinks**: Broken Link list in request test pages. If no broken links, the value is null
        - **ResponseCode**: The response status of URL request.
            - 201, Success
            - 404, Input url is not a validate http url( not starts from http or https)
            - 401, Can get http response, but IsSuccessStatusCode of http response is false
            - 400, Can't get http response

* Via code
    1. Define a class named `LinkServiceResponse` which contains Url (type is string), BrokenLinks (type is List<string>, broken link collection) and Success(type is string, a flag to determine if input url itself is a broken link)
    ```C#
    public class LinkServiceResponse
    {
            public string Url { get; set; }
            public List<string> BrokenLinks { get; set; } = new List<string>();
            public bool Success { get; set; }
    }
    ```
    2. Define a method to send httprequest with request url is http://10.213.224.35/, accepted header should be `application/json`. Sample code would be as following:
    ```C#
    public static async Task<ConcurrentDictionary<string, LinkServiceResponse>> GetBrokenLinks(IList<string> inputUrls, string requestUrl)
        {
            var result = new ConcurrentDictionary<string, LinkServiceResponse>();
            Httpclient.BaseAddress = new Uri(requestUrl);
            Httpclient.DefaultRequestHeaders.Accept.Clear();
            Httpclient.DefaultRequestHeaders.Accept.Add(new MediaTypeWithQualityHeaderValue("application/json")); 
            var content = new StringContent(JsonConvert.SerializeObject(inputUrls), Encoding.UTF8, "application/json");
            // HTTP POST
            HttpResponseMessage response = await Httpclient.PostAsync("api/link/getbrokenlink", content);
            if (response.IsSuccessStatusCode)
            {
                string data = await response.Content.ReadAsStringAsync();
                result = JsonConvert.DeserializeObject<ConcurrentDictionary<string, LinkServiceResponse>>(data);
            }
            return result;
        }
    }
    ```
    3. Specific input urls and get broken links
        Sample code would be as following:
        ```C#
        var requestUrl = "http://10.213.224.35/";
        var inputUrlList = new List<string>
        {
            "https://docs.microsoft.com/es-es/windows/manage/group-policies-for-enterprise-and-education-editions",
            "https://docs.microsoft.com/en-us/windows-server-essentials/use/work-remotely-in-windows-server-essentials"
        }; 
        var brokenLinks = GetBrokenLinks(inputUrlList, requestUrl).GetAwaiter().GetResult();
        ```
    4. Verify output result
        Output result would be as following:
        ![Call_Web_Service_Via_Code](../Images/Call_Web_Service_Via_Code.jpg)
    5. Completed Sample code:
```C#
    		using Newtonsoft.Json;
		using System;
		using System.Collections.Concurrent;
		using System.Collections.Generic;
		using System.IO;
		using System.Linq;
		using System.Net;
		using System.Net.Http;
		using System.Net.Http.Headers;
		using System.Text;
		using System.Threading.Tasks;
		 
		namespace CallWebService
		{
		    class Program
		    {
		        public static readonly HttpClient Httpclient = new HttpClient();
		 
		        static void Main(string[] args)
		        {
		            var requestUrl = " http://10.213.224.35/";
		            var inputUrlList = new List<string>
		            {
		                "https://docs.microsoft.com/es-es/windows/manage/group-policies-for-enterprise-and-education-editions",
		                "https://docs.microsoft.com/en-us/windows-server-essentials/use/work-remotely-in-windows-server-essentials"
		            };
		 
		            var brokenLinks = GetBrokenLinks(inputUrlList, requestUrl).GetAwaiter().GetResult();
		 
		            Console.ReadKey();
		        }
		 
		        public static async Task<ConcurrentDictionary<string, LinkServiceResponse>> GetBrokenLinks(IList<string> inputUrls, string requestUrl)
		        {
		            var result = new ConcurrentDictionary<string, LinkServiceResponse>();
		            Httpclient.BaseAddress = new Uri(requestUrl);
		            Httpclient.DefaultRequestHeaders.Accept.Clear();
		            Httpclient.DefaultRequestHeaders.Accept.Add(new MediaTypeWithQualityHeaderValue("application/json"));
		 
		            var content = new StringContent(JsonConvert.SerializeObject(inputUrls), Encoding.UTF8, "application/json");
		            // HTTP POST
		            HttpResponseMessage response = await Httpclient.PostAsync("api/link/getbrokenlink", content);
		            if (response.IsSuccessStatusCode)
		            {
		                string data = await response.Content.ReadAsStringAsync();
		                result = JsonConvert.DeserializeObject<ConcurrentDictionary<string, LinkServiceResponse>>(data);
		            }
		            return result;
		        }
		    }
		 
		    public class LinkServiceResponse
		    {
		        public string Url { get; set; }
		        public List<string> BrokenLinks { get; set; } = new List<string>();
		        public bool Success { get; set; }
		    }
}
```




    


