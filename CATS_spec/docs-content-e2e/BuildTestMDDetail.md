# Build Detail Testing

## Verify checkmark-bulleted lists should display well with empty item
###	The first item is empty

> [!div class="checklist"]
> * 
> * Create a resource group
> * Prepare the configuration
> * Create a virtual machine
> * Configure the firewall
> * Snapshot the virtual machine
> * Run management tasks

### The middle item is empty

> [!div class="checklist"]
> * Log in to Azure
> * Create a resource group
> * Prepare the configuration
> * 
> * Configure the firewall
> * Snapshot the virtual machine
> * Run management tasks

### The last item is empty

> [!div class="checklist"]
> * Log in to Azure
> * Create a resource group
> * Prepare the configuration
> * Create a virtual machine
> * Configure the firewall
> * Snapshot the virtual machine
> * 

## Nest font format Bold and italics

> [!div class="checklist"]
> * **This line is Bold format with '*'**
> * *This line is italic format with '*'*
> * ***This line is Bold and italic format with '*'***
> * __This line is Bold format with '_'__
> * _This line is italic format with '_'_
> * ___This line is Bold and italic format with '_'___
> * This line is **Bold** format with '*'
> * This line is *italic* format with '*'
> * This line is ***Bold and italic*** format with '*'

## Verify lists item could nest order/unorder list

> [!div class="checklist"]
> * This is order list
    1. Order list first line
    2. Order list second line
> * This is under list with *
    * unorder list first line with *
    * unorder list second line with *
> * This is unorder list with +
    + unorder list first line with +
    + unorder list second line with +

## Verify each item support link

> [!div class="checklist"]
> * Internal Link: [Internal link BuildTest](BuildTest.md).
> * Inline External Link: This is [Baidu](http://baidu.com/ "Baidu").
> * Referenced external link: This is an [baidu][1] page.
> * This is bookmark to [*Nest font format Bold and italics*](#Nest-font-format-Bold-and-italics).

[1]: http://baidu.com/

## Verify each item support image

> [!div class="checklist"]
> * Inline image: [Inline image](../Images/IIS.png).
> * Reference image: [Inline image][2].
> * External image: ![Image](http://pica.nipic.com/2008-01-09/200819134250665_2.jpg "Title")

[2]: ../Images/IIS.png

## Verify each item support alert

> [!div class="checklist"]
> * > [!NOTE] 
    > This is Note alert
> * > [!WARNING] 
    > This is Warning alert
> * > [!TIP] 
    > This is Tip alert
> * > [!IMPORTANT] 
    > This is Important alert
> * > [!CAUTION] 
    > This is Caution alert

## Verify each item support alert2
> [!div class="checklist"]
> * > [!NOTE] This is Note alert
> * > [!WARNING] This is Warning alert
> * > [!TIP] This is Tip alert
> * > [!IMPORTANT] This is Important alert
> * > [!CAUTION] This is Caution alert

## Verify checkmark list in alert
> [!NOTE]
> abc I am a checkmark list
> > [!div class="checklist"]
> > * Create a resource group
> > * Prepare the configuration
> > * Create a virtual machine

> [!WARNING]
> abc I am a checkmark list
> > [!div class="checklist"]
> > * Create a resource group
> > * Prepare the configuration
> > * Create a virtual machine

> [!TIP]
> abc I am a checkmark list
> > [!div class="checklist"]
> > * Create a resource group
> > * Prepare the configuration
> > * Create a virtual machine

> [!IMPORTANT]
> abc I am a checkmark list
> > [!div class="checklist"]
> > * Create a resource group
> > * Prepare the configuration
> > * Create a virtual machine

> [!CAUTION]
> abc I am a checkmark list
> > [!div class="checklist"]
> > * Create a resource group
> > * Prepare the configuration
> > * Create a virtual machine

## Verify each item support token
> [!div class="checklist"]
> * [!INCLUDE[ATA](../token/ATA.md)]
> * For token

## Verify each item support table

> [!div class="checklist"] 
> * Next line is table with MD format
> * |Row1|Row2|<br>|---|---|<br>|Column1|Column2|

## Verify table contains checkmark list
| I am a table contains checkmark | Description|
| ------------- | ----------- |
| aaaa  |  bbbbb|
|  > [!div class="checklist"] <br/> > * Check item 1 <br/> > * Check item 2 <br/> > * Check item 3 | 1. item1 <br> 2. Item2 <br> 3.    | 


## Verify each item support code snippet 
### For code sample 

> [!div class="checklist"] 
> * This item contains a keyword `Hello word`
> * Here is a code sample ```using System;```
> * Here is another code sample
> * ``` <br> using System; <br> using Microsoft.AnalysisServices.AdomdClient;<br>```

### For inline code

> [!div class="checklist"] 
> * The next line is code sample
> * For `inline code`.

### For code snippet
> [!div class="checklist"] 
> * The next line is code snippet
> * [!Code-fsharp[snippetGetActions_fsharp](../CodeSnippets/Testcode.c)] 

## Verify each item support video
### External Video 
> [!div class="checklist"]
> * The next line is external video
> * > [!VIDEO https://sec.ch9.ms/ch9/f882/07d5474f-4235-4d89-90bc-ed008b98f882/WAMFAAnnimated_high.mp4] 
> * > [!VIDEO https://www.youtube.com/embed/iyT1uILEI2U]

### Internal video
> [!div class="checklist"]
> * The next line is external video
> * [!VIDEO ../Videos/Testvideo.mp4] 

## Verify items could support Mix embedded elements
### Mix Order list and external link
> [!div class="checklist"]
> * 1. Order list *first* line
    2. Order list [ExternalLink](http://baidu.com/)
> * The previous line is **mix embedded element**.

### Mix alert and external link
> [!div class="checklist"]
> * > [!NOTE] 
    > This is [externallink](http://baidu.com/) in Note alert
> * > [!WARNING] 
    > This is Warning alert

### Mix table and external link
> [!div class="checklist"] 
> * Next line is table with MD format
> * |Row1|Row2|
    |Column1|[ExternalLink](http://baidu.com/)|


### Checklist in table (MD systax)
|Row1|Row2|  
|--|--|
|> [!div class="checklist"] <br> > * Next line is table with MD format|Column2|    


