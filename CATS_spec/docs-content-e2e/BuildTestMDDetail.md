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
> * 1. Order list first line
    2. Order list second line
> * * unorder list first line with *
    * unorder list second line with *
> * + unorder list first line with +
    + unorder list second line with +

## Verify each item support link

> [!div class="checklist"]
> * Internal Link: [Internal link BuildTest](BuildTest.md).
> * Inline External Link: This is [Baidu](http://baidu.com/ "Baidu").
> * Referenced external link: This is an [baidu][1] page.
> * This is bookmark to [*Nest font format Bold and italics*](#Nest font format Bold and italics).

[1]: http://baidu.com/

## Verify each item support image

> [!div class="checklist"]
> * Inline image: [Inline image](..\Images\IIS.png).
> * Reference image: [Inline image][2].
> * External image: ![Image](http://pica.nipic.com/2008-01-09/200819134250665_2.jpg "Title")

[2]: (..\Images\IIS.png)

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
    
## Verify each item support token
TBD

## Verify each item support table

> [!div class="checklist"] 
> * Next line is table with MD format
> * |Row1|Row2|
    |Column1|Column2|

## Verify each item support code snippet 
### For code sample 

> [!div class="checklist"] 
> * The next line is code sample
> * 
```
using System;

  public class Demo
{
 public void Main()
 {
        Console.WriteLine("Hello World");
 }
}
> * The previous line is code sample 

### For inline code

> [!div class="checklist"] 
> * The next line is code sample
> * For `inline code`.

### For code snippet
TBD

## Verify each item support video
### External Video 
> * The next line is external video
> * [DemoVideo](https://sec.ch9.ms/ch9/4ce4/817a99cc-24da-4689-83a8-bd5aa1c54ce4/VSToolboxContainers_high.mp4)

### Internal video
TBD

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
|> [!div class="checklist"] 
> * Next line is table with MD format
|Column2|    
