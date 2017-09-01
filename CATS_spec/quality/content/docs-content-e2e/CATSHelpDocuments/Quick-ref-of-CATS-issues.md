# Quick ref of CATS issues -- Content Validation
## Summary
All test cases that are a priority in CATS. The message of issues reported is easy-to-understand and will help you navigate to the place quickly where is content issue in one page. And there are also some actions proposed to help you find the content issue. 
- 8 priority 0 test cases (ship-blocking, must fix before release)
- 11 priority 1 test cases (High impact, should fix before release)
- 7 Priority 2 test cases (Low impact, should fix after release)

## P0  test cases

|Test case|	Issue reported|	Actions proposed|
|---------|------------|-----------------|
|Missing breadcrumbs|Breadcrumb is missing||	 
|Broken breadcrumb links|Broken Breadcrumb link <br/>Breadcrumb: {Breadcrumb text}<br/>URL: {URL}|1. Open the link of article, check the link of the breadcrumb that report error on CATS.|
|Broken internal links|	Broken link (internal to Docs)<br/>Link: [Link Text],<br/>URL: {Link URL}|1.Open the link of article and navigate to broken link (could search by {Link Text})|
|Broken bookmarks|	Bookmark not working. <br/>Link: [Bookmark Text],<br/>URL: {Bookmark URL}	|1.	Open the link of article, navigate to broken bookmark (could search by {Link Text})|
|Broken TOC links|	TOC link is broken.<br/>Navigate from page [{Page URL}]By topic name [{article name}]	 |Click the TOC links which report as broken TOC link, if it direct to an invalid page, need fix it.<br/>The {Page URL} is the repo which include the Broken TOC. |
|Required metadata populated by author|Missing Metadata:{Meta Tag},<br>This metadata is required by APEX Data Science team.<br>Required:True||
||The topic has ms.prod but is missing ms.technology.|Excepted: The "ms.service" or "ms.prod + ms.technology" exist in page source “ms.technology” is required for some ms.prod values. Check the list of approved values to see if you can use the product without a technology. If it does not, this tag is mandatory.|
||The topic cannot have both ms.service and ms.prod.|Both ms.service and ms.prod exist on page source.<br>Excepted: The "ms.service" or "ms.prod + ms.technology" exist in page source|
||The topic needs to have either ms.service or ms.prod.|Neither “ms.service” nor “ms.prod” exist on page source.<br>Excepted: The "ms.service" or "ms.prod + ms.technology" exist in page source|
||{Meta Tag} doesn't have a valid value format.|Such as meta ms.date, the format is "mm/dd/yyyy"|
||The value of ms.technology is incorrect.|If there is meta 'ms.prod', the value of ms.technology is specific|
|Required metadata populated by OPS|Missing Metadata:{Meta Tag},<br>This metadata is required by APEX Data Science team.<br>Required:True||
||{Meta Tag} doesn't have a valid value format.|Such as meta ms.publishtime, the format is "yyyy-mm-dd hh:MM AM/PM"|
|APIscan metadata validation|Missing Metadata:{Meta Tag},<br>This metadata is required by APIscan<br>Required:True|Only the meta 'ms.topic' is managed-reference, the case will be executed|
 
## P1  test cases
|Test case	|Issue reported	|Actions proposed|
|-----|-----|-----|
|Missing alerts	|Alert is missing content.<br/>Alert type: {Alert Type}	|1.	Open the page URL<br/>2.Find the alter that content is missing. If the article is very long, you could search alert by page source, could follow below step: <br/><ul><li> Open Developer Tools (via press keyboard F12). </li><li> On “Elements” tab, search with the <div class =”{Alert type} alert”> to locate to alert source.</li><li>Right click the source of the alert, select “Scroll into view” and navigate to the alert.</li></ul>3.	Fix the issue on repo.(Click “Edit” link on the panel of right-hand)|
|Breadcrumb links to pages external to Docs	|The breadcrumb [{Breadcrumb text}] is linked to a page [{Page URL}] external to Docs.com.<br/>All breadcrumb links should link to Docs.com pages.|	 All breadcrumb links should link to Docs.com pages|
|Missing code samples	|Code sample is missing content.	|1.	Open the page URL, open Developer Tools (via press keyboard F12). <br/>2.	On “Elements” tab, search with `<code>` and find the code which content is empty.<br/>|
|Missing language specification	|A code sample is missing language specification.<br/>Code content: {Code content}	|1.	Open the page URL, navigate to the code which language specification is missing (could search on page by keyword “{code content}”).<br/>2.	Add language specification for the code on repo and republish the page.|
|Missing videos	|A video is missing.<br/>URL: {source URL of the video}	|1.	Open the page URL, open Developer Tools (via press keyboard F12). <br/>2.	On “Elements” tab, search with the video name (could get video name from source URL) to locate to video source.<br/>3.	Right click the source of the video, select “Scroll into view” and navigate to the video.<br/>4. If it does not display on page, check source URL of the video is valid.|
|Unplayable videos	|A video is not able to play.<br/>URL: {Video URL}|1.	 Open the page URL, open Developer Tools (via press keyboard F12). <br/>2. On “Elements” tab, search with the video name (could get video name from source URL) to locate to video source.<br/>3. Right click the source of the video, select “Scroll into view” and navigate to the video.<br/>4. Click the “Play” button of the video, if the video cannot play.|
|Missing images	|An image is missing.<br/>Image alt: {image alt}<br/>Image source: {image source url}	|1.	Open the page URL, open Developer Tools (via press keyboard F12). <br/>2.	On “Elements” tab, search with the image name (could get image name from source URL) to locate to image source.<br/>3.	Right click the source of the image, select “Scroll into view” and navigate to the image.<br/>4.	If the image does not display on page, check source URL of the image is valid.|
|Empty list bullets	|A List is missing content.<br/>List: {List context}|1.	Open the page URL, search with {List context}, and navigate to the list.|
|PDF download	|PDF download link under TOC is missing.	 |There should be a “PDF download” link at the bottom of TOC.|
|SEO rule violation - Title length	|SEO rule violation - Title length exceeds 95 characters. <br/>Title length: {Title length},<br/>Title: {Page title}	 |The length of title should not exceeds 95 characters|
|SEO rule violation - Title ending	 |SEO rule violation - Title doesn't end with ' \| Microsoft Docs'	 |The page title should end with site identifier: ' \| Microsoft Docs'|
 
## P2 test cases
|Test case	|Issue reported	|Actions proposed|
|-------|--------------|-------------|
|HTML format validation	|For example:<br/>Html Format error:287.5-287.67: error: Attribute "ms.cmpnm" not allowed on element "li" at this point.	|For HTMLFormat case, we use W3C’s html format validation on the backend. Those HTML format violations may not be fixable by the content owners. You can simply ignore them.<br/>It is not suggest user to run this case if not necessary.|
|Missing Alt attributes for images	|An image is missing "Alt" attribute<br/>Image title: {image title}<br/>Image Source: {image source url}	|The “Alt” attribute of image is missing or have empty value.<br/>Need add “Alt” attribute for per image.|
|Broken external links	|Broken link (external to Docs).<br/>Link: [Link text],<br/>URL: {Link URL}	 |Navigate to the broken external links, and fix the broken links on repo and re-publish them.|
|Exceeded page width	|Table width is greater  than page body width<br/>Table: NO:  {Table Number}, <br/>Text: {Partial text of table}<br/>Table width: {Table width}<br/>Page width: {Page width}|	  
||Code Snippet width is greater  than page body width<br/>Code Snippet: {Partial text of Code snippet} <br/>Code Snippet width: {Code width}<br/>Page width:  {Page width}|
||Image width is greater  than page body width<br/>Image Alt: {Text of image alt} <br/>Source: {Image source URL}<br/>Image width: {Image width}<br/>Page width: {Page width}	|
|Empty rows or columns|A table may have empty row or column. <br/>Table No: {Table Number}, <br/>Table text: {Partial text of table}	 |Navigate to table that have empty row/column. (Find the table on page directly or search with keyword `<table>` on page Developer Tools mode)<br/>If there is content missing on empty row/column, need completed it, or delete the empty roe/column.|
||No row nor column in table.	 |Navigate to table that only have a table tag on page source. If the table is necessary, add content for it, or delete the table tag.|
|Empty cells	|A table may have empty cells. <br/>Table No: {Table Number}, <br/>Table text: {Partial text of table}	 |Navigate to table that only have a table tag on page source. Check if all the cell count for each row is not the same|
|Duplicate TOC	|Duplicated TOC node	 |Multiple TOC items direct to the same target topic. |
 
## Note
If you want to know more detail information about test cases in CATS, just visit our [test case api](http://contentqa_cats/Api/TestCase/ContentValidation)
