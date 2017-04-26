# Breadcrumb Cases
Breadcrumb is required for each page, including hub page, reference page and conceptual page.
This case is to verify if the breadcrumb is display on each page and the link of the breadcrumb does not link to 404 page. 
This test cases covered hub page,conceptual page,reference namespace page and reference class type page and total 2 cases currently.

**Below is test cases list:**
* [Missing Breadcrumbs](#missing-breadcrumbs)
* [Broken Breadcrumb links](#broken-breadcrumb-links)

## <a id='missing-breadcrumbs'></a>Missing Breadcrumbs
### Check point
* Check if any page is missing breadcrumb

**Steps**
1. Open the test URL one by one.
2. For each page: Check the breadcrumb exist or not.

**Expected behavior**
* The breadcrumb exist on each page.

## <a id='broken-breadcrumb-links'></a>Broken Breadcrumb links
### Check point
* Check if any breadcrumb has broken links that return 404

**Steps**
1. Open the test URL one by one.
2. For each page: If the breadcrumb exist, click on each link on breadcrumb.
3. Check if the breadcrumb has broken links that return 404

**Expected behavior**
* No links on breadcrumb that return 404 for each page