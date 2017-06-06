# Page Width Cases
This case is to verify all content elements have a width smaller than the page’s width. This case under the influence of screen resolution

**Below is test cases list:**
* [Exceeded page width](#exceeded-page-width)

## <a id='exceeded-page-width'></a>Exceeded page width
### Check point
* Check if any of the following contents are wider than the context (Alert, Image, Code Sample, Table, Video)

**Steps**
1. Open the test URL one by one.
2. If there are Alert / Image / Code Sample / Table / Video on page, compare the width of page and element.

**Expected behavior**
* All the elements do not exceed the width of the page.
