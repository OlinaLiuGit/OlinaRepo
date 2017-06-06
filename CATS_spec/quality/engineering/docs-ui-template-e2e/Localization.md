# Localization

These test cases need to covered by localization page and total 7 cases currently.Every test case includes check point, steps and expected behavior.

**Below is test cases list:**
* [Verify the comments edit share button](#Verify_the_comments_edit_share_button)
* [Local Fallback: Verify the buttons of right hand side are localized](#Verify_the_buttons_of_right_hand_side)
* [Local Fallback: Verify the page show localized content with English token/art](#Verify_the_page_show_localized_content)
* [Verify anchor in the url](#Verify_anchor_in_the_url)
* [Verify EU Banner](#Verify_EU_Banner)
* [Verify localized footer links](#Verify_localized_footer_links)
* [Verify toc and breadcrumb are localized](#Verify_toc_and_breadcrumb_are_localized)

## <a id='Verify_the_comments_edit_share_button'></a>Verify the comments edit share button
### Check point
* Verify *Comments* button is presented on en-us page and not presented on other local page
* Verify *Edit* button is  presented on all page
* Verify *Share* button is presented on all page

**Steps**
1. Open a local conceptual page
2. Validate local name is correct
3. Check *Comments* button if presented
4. Check *Edit* button if presented
5. Check *Share* button if presented
6. Check the Share items count if expected
7. Check the attribute 'href' of Share items if expected
8. Check the text of share items if expected

**Expected behavior**
* *Comments* button is presented on en-us page and not presented on other local page
* *Edit* button is  presented on all page
* *Share* button is presented on all page
* Share items count is expected
* Share items 'href' is expected

## <a id='Verify_the_buttons_of_right_hand_side'></a>Local Fallback: Verify the buttons of right hand side are localized
### Check point
* Verify the page actions component are presented
* Verify the theme selector is localized
* Verify the share button is localized
* Verify the discliamer is presented when switch to another locale page with English content
* Verify the share button is not localized for the locale page with English content 
* Verify the Theme selector is not localized for the locale page with English content 

**Steps**
1. Open a local conceptual page (eg: chinese)
2. Check the page action if presented
3. Check the theme selector if localized
4. Check the share button if localized
5. Find the locale picker at bottom
6. Switch to Magyar page
7. Check the discliamer if presented
8. Check the text of discliamer if expected
9. Check the share button show up in English
10. Check the theme selector show up in English 

**Expected behavior**
* The locale picker is presented
* Select locale picker and click it should be redirect to corresponding locale page 
* The page actions component are presented
* The theme selector is localized
* The share button is localized
* The discliamer is presented when switch to another locale page with English content page
* The text of discliamer  is expected
* The share button is not localized for the locale page with English content
* The Theme selector is not localized for the locale page with English content 

## <a id='Verify_the_page_show_localized_content'></a>Local Fallback: Verify the page show localized content with English token/art
### Check point
* Verify locale page show English token

**Steps**
1. Open a English conceptual page
2. Find the locale picker at bottom
3. Switch to France page
4. Check the token if presented
5. Check the token if show as English
6. Check the text of token if expected

**Expected behavior**
* The locale picker is presented
* Select locale picker and click it should be redirect to corresponding locale page
* The token is presented
* The token is show as English
* The text of token is expected 'Advanced Threat Analytics'

## <a id='Verify_anchor_in_the_url'></a>Verify anchor in the url
### Check point
* Verify anchor list is presented
* Verify anchor link navigate to right place
* Verify 'In this article' is localized

**Steps**
1. Open a English conceptual page
2. Find the locale picker at bottom
3. Switch to Deutsch page
4. Find the anchor list
5. Click the first anchor link
6. Check if navigate to right place
7. Check the 'In this article' if localized

**Expected behavior**
* The locale picker is presented
* Select locale picker and click it should be redirect to corresponding locale page 
* Anchor list is presented
* Anchor link navigate to right place and the url contains expected value
* 'In this article' is localized and expected text is 'In diesem Artikel'

## <a id='Verify_EU_Banner'></a>Verify EU Banner
### Check point
* Verify EU Banner is presented if switch to local(eg:de-de) page from page en-us
* Verify the text of EUBanner
* Verify the EUBanner disappear when click 'X' button

**Steps**
1. Open a English conceptual page
2. Find the locale picker at bottom
3. Switch to Deutsch page
4. Check the  EU Banner if presented at top
5. Check the text of EU Banner if expected
5. Click 'X' button of EU Banner if the EU Banner is presented
6. Check the EU Banner if disappear

**Expected behavior**
* The locale picker is presented
* Select locale picker and click it should be redirect to corresponding locale page 
* EU Banner is presented if switch to locale(eg:de-de) page from page en-us
* The text of EU Banner is expected
* The EU Banner disappear when click 'X' button

## <a id='Verify_localized_footer_links'></a>Verify localized footer links
### Check point
* Verify footer links localized
* Verify footer logo localized

**Steps**
1. Open a English conceptual page
2. Find the locale picker at bottom
3. Switch to Deutsch page
4. Check the 'href' value of footer links if contain locale name
5. Click the footer logo
6. Check the current page url if contain locale name

**Expected behavior**
* The locale picker is presented
* Select locale picker and click it should be redirect to corresponding locale page 
* Footer link privacy&cookies is localized
* Footer link terms is localized
* Footer link impressum is point to en version
* Footer link Trademarks is not localized(always is 'en-us')

## <a id='Verify_toc_and_breadcrumb_are_localized'></a>Verify toc and breadcrumb are localized
### Check point
* Verify TOC list is presented and TOC link is localized
* Verify breadcrumb is presented and link is localized

**Steps**
1. Open a locale page , eg: ja-jp
2. Find the locale picker at bottom
3. Switch to Chinese page
4. Check the TOC list if presented
5. Check the TOC list link if localized
6. Check the breadcrumb if presented
7. Check the breadcrumb link if localized
8. Check the breadcrumb text if expected

**Expected behavior**
* The locale picker is presented
* Select locale picker and click it should be redirect to corresponding locale page 
* TOC list is presented and TOC link is localized
* Breadcrumb is presented and link is localized
* Breadcrumb text is expected