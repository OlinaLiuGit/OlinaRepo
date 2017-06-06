# Image Cases
This case is to verify if there are any image cannot display on page or missing **alt** attribute.
This test cases covered hub page,conceptual page,reference namespace page and reference class type page and total 2 cases currently.

**Below is test cases list:**
* [Missing images](#missing-images)
* [Missing "Alt" attributes for images](#missing-alt-attributes-for-images)

## <a id='missing-images'></a>Missing images
### Check point
* Check if there are any missing images

**Steps**
1. Open the test URL one by one.
2. If there are image on page, check the each image display on page well.

**Expected behavior**
* The image display on page well.

## <a id='missing-alt-attributes-for-images'></a>Missing "Alt" attributes for images
### Check point
* Check if the page source code is missing any "Alt" attributes for images

**Steps**
1. Open the test URL one by one.
2. If there are image on page, check the src of the image.

**Expected behavior**
* The source url of the image do not return 404.