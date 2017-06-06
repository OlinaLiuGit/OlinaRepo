# Metadata Cases
This case is to verify if there are any page is missing required metadatas which are required by BI team or the value of required metadata with incorrect format.
This test cases covered hub page,conceptual page,reference namespace page and reference class type page and total 2 cases currently.
Note: Conceptual and Reference pages have different required metadata. Hub pages are treated as conceptual pages.

**Below is test cases list:**
* [Missing BI required metadata](#missing-bi-required-metadata)
* [Missing or incorrect metadata values](#missing-or-Incorrect-metadata-values)

## <a id='missing-bi-required-metadata'></a>Missing BI required metadata
### Check point
* Check if there are any missing metadata that are required by BI team.

**Steps**
1. Open the test URL one by one.
2. Press F12, enter into developer mode
3. Check if there are any missing metadata that are required by BI team( refer to the metadata spec)

**Expected behavior**
* The following required metadata is exist: title, author, ms.author, ms.date, ms.topic,ms.lang, ms.loc, ms.publishtime, ms.gitcommit(Only required on reference page) 
* The topic contain ms.service and ms.prod, and just contain one. If the topic has "ms.prod", it should also have "ms.technology".

## <a id='missing-or-Incorrect-metadata-values'></a>Missing or incorrect metadata values
### Check point
* Check if any required metadata are missing , or having incorrect values

**Steps**
1. Open the test URL one by one.
2. Press F12, enter into developer mode
3. Check if there are any metadata whoes value is missing or incorrect(refer to metadata spec)

**Expected behavior**
* The value should meet the required of metadata spec