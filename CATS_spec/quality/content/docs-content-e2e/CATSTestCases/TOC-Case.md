# TOC Cases
This case is to verify if there are any TOC node return to 404 page or there are multiple TOC nodes point to the same target.

**Below is test cases list:**
* [Broken TOC links](#broken-tOC-links)
* [Duplicate TOC](#duplicate-toc)

## <a id='broken-tOC-links'></a>Broken TOC links
### Check point
* Check if any TOC node links return 404

**Steps**
1. Open the test URL one by one.
2. Check if any TOC node links return 404.

**Expected behavior**
* No TOC node links return 404.

## <a id='duplicate-toc'></a>Duplicate TOC
### Check point
* Check if there are multiple TOC nodes point to the same target

**Steps**
1. Open the test URL one by one.
2. Check if there are multiple TOC nodes point to the same target.

**Expected behavior**
* There are only one TOC point to one topic.
