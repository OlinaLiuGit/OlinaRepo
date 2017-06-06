# Common

These test cases covered hub page,conceptual page,reference namespace page and reference class type page and total 6 cases currently.Every test case includes check point, steps and expected behavior.

**Below is test cases list:**
* [Verify all links of Header and Footer](#Verify_all_links_of_Header_and_Footer)
* [Verify themeSelector](#Verify_themeSelector)
* [Verify sharing button](#Verify_sharing_button)
* [Breadcrumb validation](#Breadcrumb_validation)
* [Verify Toc is presented and links are able to click](#Verify_Toc_is_presented_and_links_are_able_to_click)
* [Verify RedirectUrl work well](#Verify_RedirectUrl_work_well)
* [Verify the rating bar load successfully](#Verify_the_rating_bar_load_successfully)
* [Verify "Yes" button of rating bar work well](#Verify_Yes_button_of_rating_bar_work_well)
* [Verify "No" button of rating bar work well](#Verify_No_button_of_rating_bar_work_well)
* [Verify cross button of rating bar work well](#Verify_cross_button_of_rating_bar_work_well)

## <a id='Verify_all_links_of_Header_and_Footer'></a>Verify all links of Header and Footer
### Check point
* Verify the footer Privacy Statement is existed and the link is expected
* Verify the footer Term Of Use is existed and the link is expected
* Verify the footer Feedback is existed and the link is expected
* Verify the footer Trademarks is existed and the link is expected
* Verify the sequence of these 4 items is accurate

**Steps**
1. Open a sample page
2. Find corresponding link elements 
3. Find corresponding link elements

**Expected behavior**
* These 4 items all reveal on page
* The sequence of these 4 items is accurate on page
* The value of attribute 'href' and expected are consistent for these 4 items

## <a id='Verify_themeSelector'></a>Verify themeSelector
### Check point
* Verify the Theme Selector are shown and can be clicked
* Verify the element: html contain theme_night class when choose dark theme, and non for light theme

**Steps**
1. Open a sample page
2. Find component Theme selector
3. Switch to 'Dark' theme 
4. Check if the class value contains 'theme_night'
5. Switch to 'Light' theme
6. Check if the class value is non

**Expected behavior**
* The Theme Selector are shown and can be clicked
* The theme 'Light' and 'Dark' are reveal
* The theme class value is expected

## <a id='Verify_sharing_button'></a>Verify sharing button
### Check point
* Verify the Sharing button is present
* Verify the Sharing Facebook and Twitter is presented
* Verify the Sharing button can be clicked
* Verify the links of Sharing Facebook and Twitter  is accurate

**Steps**
1. Open a sample conceptual page
2. Find 'Share' button
3. Click the 'Share' button
4. Check element 'Facebook'
5. Check value the attribute 'href' of Facebook link

**Expected behavior**
* The Sharing button is present
* The Sharing button can be clicked
* The Sharing Facebook is presented
* The links of Sharing Facebook is accurate

## <a id='Breadcrumb_validation'></a>Breadcrumb validation
### Check point
* Verify the Breadcrumb is presented on conceptual page

**Steps**
1. Open a sample page
2. Find breadcrumb element on conceptual page
3. Verify the count of breadcrumb element

**Expected behavior**
* The breadcrumb element count is greater than 0

## <a id='Verify_Toc_is_presented_and_links_are_able_to_click'></a>Verify Toc is presented and links are able to click
### Check point
*Reference*
* Verify the TOC List is presented
* Verify the TOC list header is expected

*Conceptual*
* Verify the TOC List is shown
* Verify the particular TOC links to an expected URL

**Steps**
1. Open a sample page
2. Find the TOC items
3. Check the TOC items if presented
4. Click another sample TOC item at the same level
5. Check if redirect to expected page
6. Check the TOC header name if expected

**Expected behavior**
* TOC list is presented
* TOC item at the same level is able to click
* The url of page switch to is expected
* The TOC header items name is expected

## <a id='Verify_RedirectUrl_work_well'></a>Verify RedirectUrl work well
### Check point
* Verify page will go to the assigned page

**Steps**
1. Open a sample page
2. Verify page will go to the assigned page <URL_InstallATA_Conceptual>
3. Verify page will go to the 404 page as invalidAbsoluteUrl
4. Verify page will go to the 404 page as emptyRelativeUrl
5. Verify page will go to the 404 page as invalidRelativeUrl
6. Verify page will go to the RelativePage page

**Expected behavior**
* The value of test page url and expected are consistent
* The page is able to go to assigned 404 page

## <a id='Verify_the_rating_bar_load_successfully'></a>Verify the rating bar load successfully
### Check point
* Verify the rating bar is present once a page is fully loaded
* Verify the message in the rating bar is correct: "Is this page helpful?"
* Verify the rating bar contains 2 buttons "Yes" and "No"

**Steps**
1. Open a sample page
2. Check the rating bar is present once the page is fully loaded
3. Check the 'Yes' and 'No' button are present
4. Check the message is expected

**Expected behavior**
* The rating bar is present once the page is fully loaded
* The button 'Yes' and 'No' are present
* The message is expected 'Is this page helpful?'

## <a id='Verify_Yes_button_of_rating_bar_work_well'></a>Verify "Yes" button of rating bar work well
### Check point
* Verify the rating bar is present once a page is fully loaded
* Verify the 'Yes' button is loading successfully
* Verify that clicking the "Yes" button will show the response message and link, and that the link is working.

**Steps**
1. Open a sample page
2. Check the rating bar is present once the page is fully loaded
3. Check the 'Yes' button is present
3. Click 'Yes' button
4. Check the response message is expected
5. Check the response link 'Tell us here' is present
6. Click the link
7. Check the link is work well

**Expected behavior**
* The rating bar is present once the page is fully loaded
* The button 'Yes' is present
* The 'Yes' button work well
* The response message is expected after click 'Yes' button
* The link 'Tell us here' work well after click 'Yes' button

## <a id='Verify_No_button_of_rating_bar_work_well'></a>Verify "No" button of rating bar work well
### Check point
* Verify the rating bar is present once a page is fully loaded
* Verify the 'No' button is loading successfully
* Verify that clicking the "No" button will show the feedback window, and the window contains: message, check boxes, suggestion input box.

**Steps**
1. Open a sample page
2. Check the rating bar is present once the page is fully loaded
3. Check the 'No' button is present
3. Click 'No' button
4. Check the feedback window is present
5. Check the feedback window contains message, check boxes, suggestion input box.
6. Check the message of feedback window is expected

**Expected behavior**
* The rating bar is present once the page is fully loaded
* The button 'No' is present
* The 'No' button work well
* The feedback window is present after click 'No' button
* The feedback window contain message, check boxes and suggestion input box
* The message of feedback window is expected

## <a id='Verify_cross_button_of_rating_bar_work_well'></a>Verify cross button of rating bar work well
### Check point
* Verify the rating bar is present once a page is fully loaded
* Verify the cross button is loading successfully
* Verify that clicking the Cross button will close the rating bar.

**Steps**
1. Open a sample page
2. Check the rating bar is present once the page is fully loaded
3. Check the cross button is present
4. Click cross button
5. Check the rating bar isn't present on page

**Expected behavior**
* The rating bar is present once the page is fully loaded
* The button cross is present
* The rating bar isn't present on page after click cross button