# Docs Content Test
Docs Content Testing is to test the content in Docs [https://docs.microsoft.com](https://docs.microsoft.com) site. Verifying content format, link functionality and accuracy, and confirming that certain content attributes exist and function as expected.

## Automation Test Cases

|Elements|Test Cases|Description|
|--------|----------|-----------|
|[Breadcrumb](Breadcrumb-Case.md)|[Missing Breadcrumbs](Breadcrumb-Case.md/#missing-breadcrumbs)|Check if any page is missing breadcrumb|
||[Broken Breadcrumb links](Breadcrumb-Case.md/#broken-breadcrumb-links)|Check if any breadcrumb has broken links that return 404|
|[Link](Link-Case.md)|[Broken internal links](Link-Case.md/#broken-internal-links)|Check if any links under Docs.microsoft.com return 404|
||[Broken bookmarks](Link-Case.md/#broken-bookmarks)|Check if any bookmark (anchor) refers to incorrect destination|
||[Broken external links](Link-Case.md/#broken-external-links)|Check if any links external to Docs.microsoft.com return 404|
|[Metadata](Metadata-Case.md)|[Missing BI required metadata](Metadata-Case.md/#missing-bi-required-metadata)|Check if there are any missing metadata that are required by BI team.|
||[Missing or incorrect metadata values](Metadata-Case.md/#missing-or-Incorrect-metadata-values) |Check if any required metadata are missing , or having incorrect values|
|[SEO Rule](SEO-Rule.md)|[SEO rule violation - Title length](SEO-Rule.md/#seo-rule-violation-title-length)|Check if metadata Title exceeds length limit of 83 characters|
||[SEO rule violation - Title ending](SEO-Rule.md/#seo-rule-violation-title-ending)|Check if metadata Title ends with "\| Microsoft Docs"|
|[TOC](TOC-Case.md)|[Broken TOC links](TOC-Case.md/#broken-tOC-links)|Check if any TOC node links return 404|
||[Duplicate TOC](TOC-Case.md/#duplicate-toc)|Check if any TOC node links return 404|
|[Alert](Alert-Case.md)|[Missing alerts](Alert-Case.md/#missing-alerts)|Check if there are any missing alerts|
|[CodeSnippet](Code-Snippet-Case.md)|[Missing code samples](Code-Snippet-Case.md/#missing-code-samples)|Check if there are any missing code samples|
|[HTML](HTML-Case.md)|HTML format validation|Check the page source code based on W3C's HTML validation rules|
|[Image](Image-Case.md)|[Missing images](Image-Case.md/#missing-images)|Check if there are any missing images|
||[Missing "Alt" attributes for images](Image-Case.md/#missing-alt-attributes-for-images)|Check if the page source code is missing any "Alt" attributes for images|
|[List](List-Case.md)|[Empty list bullets](List-Case.md/#empty-list-bullets)|Check if any lists are missing contents|
|[Table](Table-Case.md)|[Empty rows/columns](Table-Case.md/#empty-rows-or-columns)|Check if any table has empty rows/columns|
||[Empty cells](Table-Case.md/#empty-cells)|Check if any table has empty cells|
|[Video](Video-Case.md)|[Missing videos](Video-Case.md/#missing-videos)|Check if there are any missing videos|
||[Unplayable videos](Video-Case.md/#unplayable-videos)|Check if there are any videos that cannot play|
|[Page Width](Page-Width-Case.md)|[Exceeded page width](Page-Width-Case.md/#exceeded-page-width)|Check if any of the following contents are wider than the context (Alert, Image, Code Sample, Table, Video)|
