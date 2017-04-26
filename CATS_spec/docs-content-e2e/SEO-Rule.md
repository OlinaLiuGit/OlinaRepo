# SEO Rule Cases
This case is to test the page metadata **Title** is follow the below SEO rulers: 
- The length of title does not exceed the length limit(Current is 95 characters)
- The metadata Title ends with `| Microsoft Docs`

**Below is test cases list:**
* [SEO rule violation - Title length](#seo-rule-violation-title-length)
* [SEO rule violation - Title ending](#seo-rule-violation-title-ending)

## <a id='seo-rule-violation-title-length'></a>SEO rule violation - Title length
### Check point
* Check if metadata Title exceeds length limit of 95 characters

**Steps**
1. Open the test URL one by one.
2. Press F12, enter into developer mode.
3. Search by keyword `<title>`.
4. Check if metadata Title exceeds length limit of 95 characters.

**Expected behavior**
* The metadata Title should not exceeds 83 characters(For Windows team: 95 characters).

## <a id='seo-rule-violation-title-ending'></a>SEO rule violation - Title ending
### Check point
* Check if metadata Title ends with `| Microsoft Docs`

**Steps**
1. Open the test URL one by one.
2. Press F12, enter into developer mode
3. Search by keyword `<title>`
4. Check if metadata Title ends with `| Microsoft Docs`

**Expected behavior**
* The metadata Title ends with `| Microsoft Docs`