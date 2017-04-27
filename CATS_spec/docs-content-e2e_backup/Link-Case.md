# Link Cases
This case is to verify if there are any link(Contain: Docs internal link, Docs internal bookmark, Docs External link) return to 404 page or Docs internal bookmark not locate to correct place.
This test cases covered hub page,conceptual page,reference namespace page and reference class type page and total 3 cases currently.

**Below is test cases list:**
* [Broken internal links](#broken-internal-links)
* [Broken bookmarks](#broken-bookmarks)
* [Broken external links](#broken-external-links)

## <a id='broken-internal-links'></a>Broken internal links
### Check point
* Check if any links under Docs.microsoft.com return 404

**Steps**
1. Open the test URL one by one.
2. For each page: Go through all the links on main content and right-hand bookmark.
3. Click on the links whose host contain "docs.microsoft.com" 
4. Check if any links return 404.

**Expected behavior**
* No broken links that return 404 for each page.

## <a id='broken-bookmarks'></a>Broken bookmarks
### Check point
* Check if any bookmark (anchor) refers to incorrect destination

**Steps**
1. Open the test URL one by one.
2. For each page: Go through all the links on main content and right-hand bookmark.
3. Click on the links whose host contain "docs.microsoft.com" and contain "#"
4. Check if any links return 404.

**Expected behavior**
* No broken bookmarks that return 404 for each page

## <a id='broken-external-links'></a>Broken external links
### Check point
* Check if any links external to Docs.microsoft.com return 404

**Steps**
1. Open the test URL one by one.
2. For each page: Go through all the links on main content and right-hand bookmark.
3. Click on the links whose host do not contain "docs.microsoft.com" 
4. Check if any links return 404.

**Expected behavior**
* No broken links that return 404 for each page