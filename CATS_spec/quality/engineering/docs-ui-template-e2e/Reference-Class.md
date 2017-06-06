# Reference Class

These test cases need to covered by reference class page and total 4 cases currently.Every test case includes check point, steps and expected behavior.

**Below is test cases list:**
* [Code syntax highlight validation on reference page](#Code_syntax_highlight_validation)
* [Verify Member section and delegate](#Verify_Member_section_and_delegate)
* [Verify Type page except delegate](#Verify_Type_page_except_delegate)
* [View Code button should show up on adalErrorClass page and clicking it should jump to the correct source code site](#View_Code_button_validation)

## <a id='Code_syntax_highlight_validation'></a>Code syntax highlight validation on reference page
### Check point
* Verify the TOC is loaded
* Verify the TOC can be expand while choose select a node and the child-item can be shown
* Verify the different Language selector can be selected and clicked
* Verify the code snippet(Declaration, and Sample field)
    * Verify the Key word(Private,  String ) has specified CSS styling
    * Verify the Key word color is expected color
    * Verify the code snippet is as expected code string

**Steps**
1. Open a sample reference page
2. Check the TOC is loaded completed
3. Check item in content is expanded after one TOC item selection
4. Check the item in content is displayed
5. Click Introduction
6. Switch language to VB
7. Switch language to C#
8. Check the C# code style if expected
9. Check the C# code content if expected
10. Switch language to VB
11. Check the VB code style if expected
12. Check the VB code content if expected
13. Check the syntax highlighted on Declaration section

**Expected behavior**
* The TOC list is presented
* The TOC can be expand while choose select a node and the child-item can be shown
* Language selector is presented and able to click
* Language C# and VB are presented and able to switch
* Code snippet style is expected
* Syntax highlighted on Declaration section

## <a id='Verify_Member_section_and_delegate'></a>Verify Member section and delegate
### Check point
* Verify member section and delegate are presented
* Verify summary description is expected
* Verify Declaration syntax highlighted style
* Verify parameters are presented and the text is expected
* Verify the Returns/Exceptions are presented and the text is expected

**Steps**
1. Open a reference page
2. Find summary element
3. Check the summary description if expected
4. Find the Declaration syntax
5. Check the code snippet is presented and the style if expected
6. Find the parameters element
7. Check the parameter text if expected
8. Find return/exception elements
9. Check the element text if expected

**Expected behavior**
* Member section and delegate are presented
* Summary description is expected
* Declaration code snippet is presented
* Declaration syntax style is expected
* Elements parameters are presented and the text is expected 'Parameters'
* Elements return/exception are presented and the text is expected 'Returns'

## <a id='Verify_Type_page_except_delegate'></a>Verify Type page except delegate
### Check point
* Verify type Declaration is presented and the text is expected
* Verify type Inheritance Hierarchy is presented and the text is expected
* Verify type Fields is presented and the text is expected
* Verify the summary description is presented and the text is expected

**Steps**
1. Open a reference page
2. Find type Declaration
3. Check the text if expected
4. Find type Inheritance hierarchy
5. Check the text if expected
6. Find the summary description
7. Check the text if expected
8. Find type Fields 
9. Check the text if expected

**Expected behavior**
* Type Declaration is presented and the text is expected 'Declaration'
* Type Inheritance Hierarchy is presented and the text is expected 'Inheritance Hierarchy'
* Type Fields is presented and the text is expected 'Fields'
* The summary description is presented and the text is expected

## <a id='View_Code_button_validation'></a>View Code button should show up on adalErrorClass page and clicking it should jump to the correct source code site
### Check point
* Verify 'View Code' component is presented
* Verify text of 'View Code' button is expected
* Verify the 'View Code' button is able to click and link to right page

**Steps**
1. Open a reference page
2. Find the 'View Code' component
3. Check the text of this 'View Code' button
4. Click the 'View Code' button
5. Check the page redirect to

**Expected behavior**
* 'View Code' component is presented
* Text of 'View Code' button is expected 'View Code'
* 'View Code' button is able to click
* The url of page redirect to is expected