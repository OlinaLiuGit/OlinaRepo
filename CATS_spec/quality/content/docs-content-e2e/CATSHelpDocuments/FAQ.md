# Q&A about CATS

## About CATS run

**<font color='red'>Q:</font>** Which Docsets should I select when using run options “Provide Docsets”? <br/>
**<font color='green'>A:</font>** The Docset name is the value of metadata "search.ms_docsetname" of the articles that you want to test. You can follow below steps to get Docset name.
- Open one article that you want to test on browser.
- Press "F12" to enter into Developer Tools.
- On Elements tab, search by keyword "search.ms_docsetname", navigate to the metadate "search.ms_docsetname", the value of content is the Docset name you need to select.
 
**<font color='red'>Q:</font>** What’s the difference between “Include all pages in the same TOC” and “Include all pages in the same TOC and any referenced TOC (may take long to finish)” under pages to test?<br/>
**<font color='green'>A:</font>** Both “Include all pages in the same TOC” and “Include all pages in the same TOC and any referenced TOC (may take long to finish)” test all pages under the TOC that contain test page. The distinction is if any page link to another repo:
- If selected is the “Include all pages in the same TOC” option, CATS will test the target page but not test all the pages under the TOC that include target page.
- If selected is the “Include all pages in the same TOC and any referenced TOC (may take long to finish)”, CATS will test the target page and all the pages under the TOC that include target page.
 
**<font color='red'>Q:</font>** Can I been notified once my test run has completed?<br/>
**<font color='green'>A:</font>** Yes, CATS support to notify user through email after the run completed. You just need to check "Send Report Email after Run Completed" on "3 Preview Test Run" page of create run wizard when you kick off CATS run.
 
## About CATS run report
**<font color='red'>Q:</font>** What actions should I supposed to take on the issues cats reported?
<br/>
**<font color='green'>A:</font>** It is suggest user to fix P0 & P1 cases before content release, the P2 cases is low impact, should fix after release. The priority of cases and actions propose see below
 
**<font color='red'>Q:</font>** Why only 1 page been tested when I choose “Include subpages (child TOC nodes)”?
<br/>
**<font color='green'>A:</font>** 

**<font color='red'>Q:</font>** Why only 1 page been tested when I choose “include all pages in the same TOC”?
<br/>
**<font color='green'>A:</font>** 
......
 
***Cannot find answer for my question? Please email CATS Support [catssupport@microsoft.com](mailto:catssupport@microsoft.com), you’ll get the response within a working day.***
