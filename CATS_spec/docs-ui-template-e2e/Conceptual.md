# Conceptual

These test cases need to covered by conceptual page and total 10 cases currently.Every test case includes check point, steps and expected behavior.

**Below is test cases list:**
* [Verify git contributor information](#Verify_git_contributor_information)
* [All contents on [ATA Deployment Guide] page is loaded completed](#All_contents_on_ATA_Deployment_Guidepage)
* [All contents on [Install_ATA] page is loaded completed](#All_contents_on_Install_ATA_page)
* [Selector on [Conceptual UI Components] page could switch successful](#Selector)
* [Step by step on [Conceptual UI Components] page could navigate successful](#Step_by_step)
* [Verify images validation](#Verify_images_validation)
* [Verify the Alerts validation](#Verify_the_Alerts_validation)
* [Verify the video validation](#Verify_the_video_validation)
* [Edit button on Conceptual page should work well](#Edit_button_on_Conceptual_page_should_work_well)
* [Verify DOM metadata on Conceptual page](#Verify_DOM_metadata_on_Conceptual_page)

## <a id='Verify_git_contributor_information'></a>Verify git contributor information
### Check point
* Verify the date information is presented
* Verify the contributor picture is presented
* Verify the contributor name is presented
* Verify the link of contributor name link to the github page of right writer

**Steps**
1. Open a sample page 
2. Verify the data information is displayed on page
3. Verify the contributor picture is displayed on page
4. Verify the contributor name is displayed on page
5. Click author link and verify the page navigate to target page correctly

**Expected behavior**
* The data date and the time to read is not null
* The data date and the time to read is presented
* The contribute picture is presented
* The title of contribute picture is not null
* The contribute name is presented
* The value of contribute name is not null
* Click contribute link can redirect to the github page of right writer

## <a id='All_contents_on_ATA_Deployment_Guidepage'></a>All contents on [ATA Deployment Guide] page is loaded completed
### Check point
* Verify the topic title is presented
* Verify Link item list in the content is clickable and link to right page
* Verify if test assigned page

**Steps**
1. Open a sample page
2. Find topic title element
3. The value of this element id compare with excepted value
4. Find a sample sub link
5. Click this sample link
6. Compare url with expected
7. Compare the page title with expected

**Expected behavior**
* The topic title is presented
* The sub link is clickable and is able to link to right page
* The page title is expected

## <a id='All_contents_on_Install_ATA_page'></a>All contents on [Install_ATA] page is loaded completed
### Check point
* Verify the topic title is presented
* Verify In this Article list is presented and clickable and navigate to right anchor
* Verify ATA configuration list is presented and the count is expected and clickable and be able to link to right page

**Steps**
1. Open a sample page
2. Find the topic title
3. Find In this Article list
4. Find ATA configuration list 
5. Click In this Article list sub link and verify if navigate to right anchor
6. Click ATA configuration list link and verify if link to right page

**Expected behavior**
* The topic title is presented
* The In this Article list link is presented
* The ATA configuration list link is presented and the count is expected
* The In this Article list link is clickable and is able to link to right anchor
* The ATA configuration list link is clickable and is able to link to right page

## <a id='Selector'></a>Selector on [Conceptual UI Components] page could switch successful
### Check point
* Verify Selector(dropdown list component) item is clickable and link to right page

**Steps**
1. Open a sample page
2. Find a selector element
3. Click a sample sub option
4. Check if link to right page
5. Back to previous page 
6. Click another sample sub option
7. Check if link to right page

**Expected behavior**
* Component selector is presented
* The page title of page switch to is expected

## <a id='Step_by_step'></a>Step by step on [Conceptual UI Components] page could navigate successful
### Check point
* Verify the button of Step-by-Step component works

**Steps**
1. Open a sample page
2. Navigate to the bottom of this topic
3. Find the step-by-step 'PREV' button and click it
4. Check if link to right page
5. Back to previous page
6. Find step-by-step 'NEXT' button and click it
7. Check if link to right page

**Expected behavior**
* Component 'PREV' and 'NEXT' button are presented
* The page title of page link to is expected

## <a id='Verify_images_validation'></a>Verify images validation
### Check point
* Verify the static image display on page
* Verify the linked image is able to clic

**Steps**
1. Open a sample page
2. Find a sample static image
3. Check if the image is display
4. Find a sample linked image
5. Click the image
6. Check if the page redirect

**Expected behavior**
* The attribute 'display' in not none for static image
* The redirect url is expected for linked image

## <a id='Verify_the_Alerts_validation'></a>Verify the Alerts validation
### Check point
* Verify Note alert
* Verify Warning alert
* Verify Tip alert
* Verify Important alert

**Steps**
1. Open a sample page
2. Find 'Note' alert
3. Check the alert name
4. Find 'Warning' alert
5. Check the alert name
6. Find 'Tip' alert
7. Check the alert name
8. Find 'Important' alert
9. Check the alert name

**Expected behavior**
* The 'Note' alert name is expected
* The 'Warning' alert name is expected
* The 'Tip' alert name is expected
* The 'Important' alert name is expected
* These alert is presented

## <a id='Verify the video validation'></a>Verify the video validation
### Check point
* Verify the video is presented
* Verify the video is able to play

**Steps**
1. Open a sample page
2. Find the video element
3. Click play button
4. Check the play time

**Expected behavior**
* The video element is presented
* The time is greater than '0:00' after playing some time

## <a id='Edit_button_on_Conceptual_page_should_work_well'></a>Edit button on Conceptual page should work well
### Check point
* Verify the Edit button is clickable and will jump to right Github source

**Steps**
1. Open a sample page
2. Find Edit button on Conceptual index page and click it
3. Find Edit button on [ATA Deployment Guide] page and click it
4. Find Edit button on [Install ATA] page and click it
5. Find Edit button on [UIComponent] page and click it

**Expected behavior**
* The 'Edit' button is presented on per conceptual page
* The 'Edit' button is able to click and jump to right Github source
* The test pages are correct and expected

## <a id='Verify_DOM_metadata_on_Conceptual_page'></a>Verify DOM metadata on Conceptual page
### Check point
*Verify DOM metadata on Conceptual page, the meta is exist and has a right value*
* ROBOTS
* ms.contentsource
* ms.depotname
* ms.opspagetype
* ms.author
* ms.documentid
* ms.gitcommit
* ms.gitur
* ms.sitename
* ms.publishtime
* ms.locale, ms.lang, ms.loc, ms.contentlang (English\German)

*Verify special metadata is not exist on local page*
* content_git_url
* open_topublish_contributors

**Steps**
1. Open a English conceptual page 
2. Find these metadata of metadata list in  page source
3. Check if exist
4. Check the accuracy of metadata value if exist
5. Switch to local page, eg: German
6. Find metadata ms.locale, ms.lang, ms.loc, ms.contentlang
7. Check if exist
8. Check the accuracy of metadata value if exist
9. Find metadata content_git_url, open_topublish_contributors
10. Check if exist

**Expected behavior**
* These meta is exist on English conceptual page
* These meta has a right value on English conceptual page
* Local meta ms.locale, ms.lang, ms.loc, ms.contentlang are exist on local page
* Local meta ms.locale, ms.lang, ms.loc, ms.contentlang have right value on local page
* Special meta content_git_url, open_topublish_contributors is not exist on local page