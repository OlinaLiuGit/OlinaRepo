# Reference Common

These test cases covered reference namespace page and reference class type page and total 3 cases currently.Every test case includes check point, steps and expected behavior.

**Below is test cases list:**
* [Search reference function should work well](#Search_reference_function_should_work_well)
* [Verify language selector](#Verify_language_selector)
* [Verify platform selector](#Verify_platform_selector)

## <a id='Search_reference_function_should_work_well'></a>Search reference function should work well
### Check point
* Verify the 'Filter' input is presented
* Verify the TOC Filter can filter out the TOC with input string for per platform

**Steps**
1. Open a sample reference page
2. Find the 'Filter' input
3. Check the 'Filter' input if presented
4. Select a platform, eg: WinRT
5. Input string contain TOC name, eg: Ada
6. Check the TOC list of filter if expected
7. Clear 'Filter' input
8. Input string contain TOC name, eg: Aut
9. Check the TOC list of filter if expected
10. Clear 'Filter' input
11. Select a platform, eg: WinPhoneSilverlight
12. Check the TOC items count if expected

**Expected behavior**
* The 'Filter' input is presented
* The TOC Filter can filter out the TOC with input string for per platform
* Platform item count is expected
* Platform items text is expected
* TOC items count is expected for per platform

## <a id='Verify_language_selector'></a>Verify language selector
### Check point
* Verify language selector is presented
* Verify the language selector work well

**Steps**
1. Open a sample reference page
2. Find the language selector
3. Check the language selector if presented
4. Switch to language C# by click  language selector
5. Check the attribute 'hidden' is null for class 'lang-csharp'
6. Check the attribute 'hidden' is hidden for class 'lang-vb'
7. Check the count of class 'lang-csharp' is expected
8. Switch to language VB by click language selector
9. Check the attribute 'hidden' is null for class 'lang-vb'
10. Check the attribute 'hidden' is hidden for class 'lang-csharp'
11. Check the count of class 'lang-vb' is expected

**Expected behavior**
* Language selector is presented
* Language selector is able to click
* There are two language 'C#' and 'VB'
* The class count for per language is expected in page source
* Switch to C# language, C# code will be show and VB code will be hide
* Switch to VB language, VB code will be show and C# code will be hide

## <a id='Verify_platform_selector'></a>Verify platform selector
### Check point
* Verify platform selector is shown and the list count is expected
* Verify platform selector works 
  * Verify the TOC items change after the platform changes
  * Verify Content change(Fields, Methods) by switch platform

**Steps**
1. Open a sample reference page
2. Find the platform component
3. Check the platform if presented
4. Click the platform component
5. Check the count of platform items if expected
6. Check the platform item name if expected
7. Click a sample platform item, eg: WinPhoneSilverlight
8. Check the TOC list count if expected
9. Check a sample TOC name if expected
10. Check body element items if expected
11. Check a sample body element text if expected

**Expected behavior**
* Platform selector is presented
* Platform component is able to click
* The count of platform is expected
* Platform item is able to click
* Toc list count is expected for per platform item
* Body element count is expected for per platform item