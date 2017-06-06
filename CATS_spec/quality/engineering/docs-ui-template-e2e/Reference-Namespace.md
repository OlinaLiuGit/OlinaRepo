# Reference Namespace

These test cases need to covered by reference namespace page and total 1 case currently.Every test case includes check point, steps and expected behavior.

**Below is test cases list:**
* [Reference namespace page validation](#Reference_namespace_page_validation)

## <a id='Reference_namespace_page_validation'></a>Reference namespace page validation
### Check point
* Verify the content type is expected for per platform
* Verify the content type text is expected for per platform
* Verify the platform component is presented
* Verify the platform items count is expected
* Verify the platform items text is expected
* Verify the platform items are able to click
* Verify the description(below the type classes) content is expected
* Verify the name(below the type classes) is clickable and able to link to expected page

**Steps**
1. Open a reference namespace page
2. Check the content type 'classes' is presented, 'enum' and 'delegate' are not presented
3. Check the text for classes content type is expected
4. Find the platform component
5. Check the platform items count if expected
6. Check the platform items text if expected
7. Switch to 'WinPhoneSilverlight' platform
8.  Check the content type 'classes'  'enum' and 'delegate' are presented
9. Check the text for content type are expected
10. Check the description below classes is expected
11. Click the name 'AdalError' and check if redirect to right page

**Expected behavior**
* The content type is expected for per platform
* The content type text is expected for per platform
* the platform component is presented
* The platform items count is expected
* The platform items text is expected
* The platform items are able to click
* The description(below the type classes) content is expected
* The page title redirect to is expected