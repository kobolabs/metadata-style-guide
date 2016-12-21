![background sidebar image](https://github.com/kobolabs/metadata-style-guide/blob/Testing/banner-MSG3.png)

# Kobo Metadata Style Guide

## Table of Contents
 ### Required fields
* [eISBN](#eisbn) </br>
* [Title](#title) </br>
* Publisher</br>
* Contributor (Author, Editor, etc.)</br>
* Language</br>
* Subject Code</br>
* Sales Rights</br>
* Price/Price Type Code (ONIX only)</br>
* Price Date Role (ONIX only)</br>
* Publishing Status</br>

 ### Strongly Recommended
* Publication Date</br>
* On Sale Date (ONIX 2.1) / Embargo Date (ONIX 3.0)</br>
* Related Product</br>
* Series Name/Series Number</br>
* Audience Age Range - From/Audience Age Range - To</br>
* Product Availability</br>
* Master Brand</br>

 ### Recommended if applicable
* Subtitle</br>
* Imprint</br>




</br></br>

## eISBN 
```ruby
Required 
```
### Definition</br>
``Required field``: Your eBook's electronic ISBN. Must be 13 digits in length.
  
### Best Practice	</br>
In ONIX the ISBN must be unhyphenated.

### Correct Usage (example)	</br>
  * **Excel**</br>
eBook ISBN: 9780007322596  

  * **ONIX 2.1 and 3.0** </br>
    Reference Name:</br>
`<ProductIdentifier>`</br>
`<ProductIDType>03</ProductIDType>`</br>
`<IDValue>9780826110077</IDValue>`</br>
`</ProductIdentifier>`</br>    

    Short Tag:</br>
`<productidentifier>`</br>
`<b221>03</b221>`</br>
`<b244>9780826110077</b244>`</br>
`</productidentifier>` </br>   
    
</br>
### Common Errors (example)	</br>
  * 9781780000
  * 978-1443424523
  
### Character Limits	</br>
13 digits

### Notes</br>
ONIX: `ProductIDType` 03 is mandatory as it represents how your books will be identified in universal trading transactions.  

Multiple Product Identifers are allowed per title. We parse `ProductIDs` of product types in this order: ‘03’, ‘15’, ‘02’, ‘01.’ Please note we will only use type ‘02’ in cases where neither type ‘03’, nor type ‘15’ is provided. 

When supplying ISBNs to the library sector, the ISBN-13 `ProductIDType` 15 should be labelled distinctively.   
</br>
02 - ISBN-10 </br>
03 - EAN-13 (GTIN-13) </br>
04 - UPC </br>
13 - LCCN </br>
15 - ISBN-13</br>

</br></br>
## Title
_**Required**_

### Definition</br>
 Your eBook's title as it should appear on the Kobo store.
  
  
### Best Practice	</br>
Please refrain from appending "A" or "The" to the end of the title as it might interfere with search functions. Also, please refrain from adding the subtitle in the title field and use the appropriate Excel field or ONIX tag.

### Correct Usage (example)	</br>
  * **Excel**</br>
Title: The Shark in the Park
  * **ONIX 2.1** </br>
    Reference Name:</br>
`<Title>`</br>
`<TitleType>01</TitleType>`</br>
`<TitleText>The Shark In The Park</TitleText>`</br>
`</Title>`</br>

  * **ONIX 3.0** </br>
   Reference Name:</br>   
`<TitleDetail>`</br>
`<TitleType>01</TitleType>`</br>
`<TitleElement>`</br>
`<TitleElementLevel>01</TitleElementLevel>`</br>
`<TitlePrefix>The</TitlePrefix>`</br>
`<TitleWithoutPrefix>Shark In The Park</TitleWithoutPrefix>`</br>
`<Subtitle>Left Shark's Park Lark</Subtitle>`</br>
`</TitleElement>`</br>
`</TitleDetail>`</br>

   Short Tag:</br>
`<titledetail>`</br>
`<b202>01</b202>`</br>
`<titleelement>`</br>
`<x409>01</x409>`</br>
`<b030>The</b030>`</br>
`<b031>Shark In The Park</b031>`</br>
`<b029>Left Shark’s Park Lark</b029>`</br>
`</titleelement>`</br>
`</titledetail>`</br>
</br>


### Common Errors (example)	</br>
Incorrect: Fellowship of the Ring, The

### Character Limits	</br>
250


--- template --- 

## Field	
### Definition</br>
### Best Practice	</br>
### Correct Usage (example)	</br>
  * **Excel**</br>
  * **ONIX 2.1 and 3.0** </br>
    Reference Name:
    
    Short Tag:
</br>
### Common Errors (example)	</br>
### Character Limits	</br>
### Notes</br>

--- template --- 
