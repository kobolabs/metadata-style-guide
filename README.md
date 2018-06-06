![background sidebar image](https://github.com/kobolabs/metadata-style-guide/blob/Testing/banner-MSG3.png)

*Last update: April 2018*

# Kobo Metadata Style Guide

## Table of Contents
### Required Field
* [ISBN](#isbn) </br>
* [Title](#title) </br>
* [Publisher](#publisher)</br>
* [Contributor (Author, Editor, etc.)](#contributor-author-editor-etc)</br>
* [Language](#language)</br>
* [Subject Code](#subject-code)</br>
* [Sales Rights](#sales-rights)</br>
* [Price/Price Type Code (ONIX only)](#priceprice-type-code-onix-only)</br>
* [Price Effective Date & Price Date Role (ONIX only)](#price-effective-date--price-date-role-onix-only)</br>
* [Publishing Status](#publishing-status)</br>

### Strongly Recommended
* [Publication Date](#publication-date)</br>
* [On Sale Date (ONIX 2.1) / Embargo Date (ONIX 3.0)](#on-sale-date-onix-21--embargo-date-onix-30)</br>
* [Related Product](#related-product)</br>
* [Series Name/Series Number](#series-nameseries-number) (When applicable)</br>
* [Audience Age Range - From/Audience Age Range - To](#audience-age-range---fromaudience-age-range---to) (especially for children's, teenage and school books)</br>
* [Product Availability](#product-availability)</br>
* [Imprint](#imprint)</br>

### Recommended if applicable
* [Subtitle](#subtitle)</br>
* [Master Brand](#master-brand) (If applicable)</br>


### Audiobooks Specific Metadata
* [Product Form](#product-form)</br>
* [AudioBook Edition](#audiobook-edition)</br>
* [Contributor Type](#contributor-type) (Especially “reader” role E07) </br>
* [Duration](#duration)</br>
* [File Size](#filesize)</br>



</br></br>

## ISBN 

### Definition</br>
Your eBook's electronic ISBN. Must be 13 digits in length.
  
### Best Practice	</br>
> In ONIX the ISBN must be unhyphenated.

### Correct Usage (example)	</br>
Info | Excel                                   | ONIX 2.1 and 3.0
-------------- | --------------------------------------- | --------------------------------------- 
**Reference Name** |eBook ISBN: 9780007322596| `<ProductIdentifier>`</br>`<ProductIDType>15</ProductIDType>`</br>`<IDValue>9780826110077</IDValue>`</br>`</ProductIdentifier>`</br> 
**Short Tag**      | N/A                                     | `<productidentifier>`</br>  `<b221>03</b221>`</br>`<b244>9780826110077</b244>`</br>`</productidentifier>` </br>       
**Character Limits**	|13 digits|13 digits
    
### :warning: Common Errors (example)	</br>
  * 9781780000
  * 978-1443424523

### Notes</br>
ONIX: `ProductIDType` 03 is mandatory as it represents how your books will be identified in universal trading transactions.  

Multiple Product Identifers are allowed per title. We parse `ProductIDs` of product types in this order: ‘03’, ‘15’, ‘02’, ‘01.’ Please note we will only use type ‘02’ in cases where neither type ‘03’, nor type ‘15’ is provided. 

When supplying ISBNs to the library sector, the ISBN-13 `ProductIDType` 15 should be a distinct ISBN.   
</br>
02 - ISBN-10 </br>
03 - EAN-13 (GTIN-13) </br>
04 - UPC </br>
13 - LCCN </br>
15 - ISBN-13</br>


<sub>:back: [Table of Contents](#table-of-contents)</sub>
</br>

## Title

### Definition</br>
 Your eBook's title as it should appear on the product page.
 
### Best Practice	</br>
> Please refrain from appending "A" or "The" to the end of the title as it might interfere with search functions. Also, please refrain from adding the subtitle in the title field and use the appropriate Excel field or ONIX tag.

### Correct Usage (example)	</br>
Info               | Excel                                   | ONIX 2.1                                | ONIX 3.0
-------------- | --------------------------------------- | --------------------------------------- |---------------------------------------
**Reference Name** |Title: The Shark in the Park| `<Title>`</br>`<TitleType>01</TitleType>`</br>`<TitleText>The Shark In The Park</TitleText>`</br>`</Title>`</br> |`<TitleDetail>`</br>`<TitleType>01</TitleType>`</br>`<TitleElement>`</br>`<TitleElementLevel>01</TitleElementLevel>`</br>`<TitlePrefix>The</TitlePrefix>`</br>`<TitleWithoutPrefix>Shark In The Park</TitleWithoutPrefix>`</br>`<Subtitle>Left Shark's Park Lark</Subtitle>`</br>`</TitleElement>`</br>`</TitleDetail>`</br>
**Short Tag**      | N/A|`<title>`</br>`<b202>01</b202>`</br>`<b203>Shark In The Park</b203>`</br>`</title>`</br>|`<titledetail>`</br>`<b202>01</b202>`</br>`<titleelement>`</br>`<x409>01</x409>`</br>`<b030>The</b030>`</br>`<b031>Shark In The Park</b031>`</br>`<b029>Left Shark’s Park Lark</b029>`</br>`</titleelement>`</br>`</titledetail>`</br>      
**Character Limits**	|250|250|250

### :warning: Common Errors (example)	</br>
Incorrect: Fellowship of the Ring, The

### Notes</br>
Book titles, subtitles, series titles or author fields that include extraneous words that are not actually part of the official title, subtitle, series title or author name are not acceptable and lead to confusion and the corruption of metadata standards. We respectfully request that you ensure your catalog of titles does not include such details so that the overall Kobo catalog can offer the purest experience for our customers around the world.

Please consult [BIC Statement on Best Practice for Subtitle Field in Metadata Feeds](http://www.bic.org.uk/files/pdfs/BIC%20Statement%20on%20Best%20Practice%20for%20Sub-title%20field%20FINAL%209th%20March%202018.pdf).

<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>

## Publisher	

### Definition</br>
Your publisher name as it should appear on the Kobo store.

### Correct Usage (example)	</br>
Info               | Excel                       | ONIX 2.1 and 3.0
-------------- | --------------------------- | --------------------------- 
**Reference Name** |Publisher: Left Shark Editions|`<Publisher>`</br>`<PublishingRole>01</PublishingRole>`</br>`<PublisherName>Left Shark Editions</PublisherName>`</br>`</Publisher>`</br>
**Short Tag**      | N/A                            |`<publisher> `</br>`<b291>01</b291>`</br>`<b081>Left Shark Editions</b081>`</br>`</publisher>`</br>   
**Character Limits**	|250|250
### Notes</br>
We read `<PublishingRole>` 01 and 04.
 


<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>


## Contributor (Author, Editor, etc.)

### Definition</br>
The author and/or editor name(s)

### Best Practice	</br>
> Please use the format: First Name + Last Name for this field. No commas or name order reversal.
>
> ONIX: If your title does not have a contributor, you can now use the field `<NoContributor/>` or `<n339/>` in your ONIX. We will instead list the imprint or publisher name as the byline.

### Correct Usage (example)	</br>
Info               | Excel                       | ONIX 2.1 and 3.0
-------------- | --------------------------- | --------------------------- 
**Reference Name** |Contributor 1: David Shubert</br>Contributor Type: A01|`<Contributor>`</br>`<SequenceNumber>1</SequenceNumber>`</br>`<ContributorRole>A01</ContributorRole>`</br>`<PersonName>David Shubert PhD</PersonName>`</br>`<PersonNameInverted>Shubert, David, PhD</PersonNameInverted>`</br>`<NamesBeforeKey>David</NamesBeforeKey>`</br>`<KeyNames>Shubert</KeyNames>`</br>`<LettersAfterNames>PhD</LettersAfterNames>`</br>`</Contributor>`</br>  
**Short Tag**      |N/A                             |`<contributor>`</br>`<b034>1</b034>`</br>`<b035>A01</b035>`</br>`<b036>Ben Byrne</b036>`</br>`<b037>Byrne, Ben</b037>`</br>`<b039>Ben</b039>`</br>`<b040>Byrne</b040>`</br>`</contributor>`</br>   
**Character Limits**	|250|250
### :warning: Common Errors (example)	</br>
Incorrect: Shubert, David

### Notes</br>
Excel: This is where you can list the names of your eBook's contributors. If the contributors are the same type (i.e. more than one author, or editor, etc), you can put them in the same cell separated by a comma.


<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>

## Language	
### Definition</br>
Excel: The language code that indicates the language in which your eBook is written (two characters).
ONIX: Language role (language of text, language of original text, etc) and the three-character language code. 
</br>
### Correct Usage (example)	</br>
Info               | Excel                       | ONIX 2.1 and 3.0
-------------- | --------------------------- | --------------------------- 
**Reference Name** | Language: EN                            | `<Language>`</br>`<LanguageRole>01</LanguageRole>`</br>`<LanguageCode>eng</LanguageCode>`</br>`</Language>`</br> 
**Short Tag**      | N/A                            |`<language>`</br>`<b253>01</b253>`</br>`<b252>eng</b252>`</br>`</language>`</br>    
**Character Limits**	|2|3
### :warning: Common Errors (example)	</br>
Excel: BRL, English, Eng 

### Notes</br>
Please note that currently we don't support multiple language codes for a single title. Please choose one specific language code for the text and include information about the bilingual nature of the text in the description. We suggest selecting the language code for the audience the title most widely serves. 


<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>

## Subject Code	
### Definition</br>
A subject category code from the scheme identified (BISAC, BIC, etc), which will help catalogue ebooks.

### Best Practice	</br>
> Please always include a subject code so customers can more easily find your ebooks. Category codes help discoverability on site. Your chosen codes correspond to our category stores on site, so the more specific you can be, the better.
> 
> While it's beneficial to have a main subject, you can include additional subject codes with increasing precision so your target audience will find your books.

 
 Info              | Excel                       | ONIX 2.1                   | ONIX 3.0
-------------- | --------------------------- | ---------------------------|---------------------------
**Reference Name** |Categorization Code:JNF001100</br>Categorization Type: BISAC                           |BISAC</br>`<BASICMainSubject>JNF001100</BASICMainSubject>`</br>`<Subject>`</br>`<SubjectSchemeIdentifier>10</SubjectSchemeIdentifier>`</br>`<SubjectCode>JNF028000</SubjectCode>`</br>`</Subject>`</br>BIC</br>`<BICMainSubject> YNU</BICMainSubject>`</br>                            |`<Subject>`</br>`<MainSubject/>`</br>`<SubjectSchemeIdentifier>10</SubjectSchemeIdentifier>`</br>`<SubjectCode>JNF001000</SubjectCode>`</br>`</Subject>`</br>`<Subject>`</br>`<SubjectSchemeIdentifier>10</SubjectSchemeIdentifier>`</br>`<SubjectCode>JNF028020</SubjectCode>`</br>`</Subject>`</br> 
**Short Tag**      |N/A                             |BISAC</br>`<b064>JNF001100</b064>`</br>`<subject>`</br>`<b067>10</b067>`</br>`<b069>JNF028000</b069>`</br>`<subject>`</br>BIC</br>`<b065>YNU</b065>`</br>                            |`<subject>`</br>`<x425/>`</br>`<b067>10</b067>`</br>`<b069>JNF001000</b069>`</br>`</subject>`</br>`<subject>`</br>`<b067>10</b067>`</br>`<b069>JNF028020</b069>`</br>
<sub>Scroll right to see entire table ->></sub>
</br> 

### Notes</br>
Best practices recommend that books include up to 3 subject category codes to maximize customer reach.
We do not currently accept Thema codes. </br>
Kobo only supports BISAC, BIC and CLIL categories codes. (Please note that the
CLIL codes are accepted but mapped to BISAC via our system).</br>

2017 BISAC subjects codes are supported by Rakuten Kobo.</br>

<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>

## Sales Rights	
### Definition</br>
Your eBook's sales rights.
 
### Best Practice	</br>
> To indicate sales rights use two-letter territory codes to specify where your ebook can be sold according to the rights your company holds. `<SalesRightsType>` is important in indicating specific type of rights held (exclusive, non-exclusive, not for sale, etc). Please see correct usage for how to declare sales rights in ONIX.</br>
>
> ONIX 2.1: Please use upper-case characters and separate each territory with a space in `<RightsCountry>US CA</RightsCountry>`. World Rights should be indicated as `<RightsTerritory>WORLD</RightsTerritory>`</br>
> ONIX 3.0: Similarly, in `<CountriesIncluded>` please use upper-case characters and separate each territory with a space. World rights should be indicated as `<RegionsIncluded>WORLD</RegionsIncluded>`</br>
>
> Excel: Leave this field blank if you want your by default contract sales right info to be applied. If your eBook can only be sold in a specific list of countries, you must indicate their two-letter country codes in this field with each country code separated by a comma.

### Correct Usage (example)	</br>
Info| Excel                       | ONIX 2.1                   | ONIX 3.0
-------------- | --------------------------- | ---------------------------|---------------------------
**Reference Name** |US,CA,BR|`<SalesRights>`</br>`<SalesRightType>01</SalesRightsType>`</br>`<RightsCountry>US CA BR</RightsCountry>`</br>`</SalesRights>`</br>|`<SalesRights>`</br>`<SalesRightsType>01</SalesRightsType>`</br>`<Territory>`</br>`<CountriesIncluded>US CA BR</CountriesIncluded>`</br>`</Territory>`</br>`</SalesRights>`</br>`<ROWSalesRightsType>03</ROWSalesRightsType>`</br>
**Short Tag**      |N/A|`<salesrights>`</br>`<b089>01</b089>`</br>`<b090>US CA BR</b090>`</br>`</salesrights>`</br>                            |`<salesrights>`</br>`<b089>01</b089>`</br>`<territory>`</br>`<x449>US CA BR</x449>`</br>`</territory>`</br>`<salesrights>`</br>`<x456>03</x456>`</br>

### :warning: Common Errors (example)	</br>
Excel: Australia


<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>

## Price/Price Type Code (ONIX only)	
### Definition</br>
Your eBook's price.

The Price Type Code specifies the type of price submitted (e.g. reommended retail price, agency, fixed retail price).

### Best Practice	</br>
> **Price**</br>
> In **ONIX**, please follow the 2.1 or 3.0 specification.</br>
> In **Excel** price:</br>
  > * Must not contain commas. Use a period character as a decimal point.</br>
  > * Must be formatted as a number.</br>
  > * Must not contain currency symbols.</br>
  > * Currency must be in upper-case format.</br>
  
> **Price Type Code**
> Please submit prices that correspond with your territory and contract type. For prices that don't have tax included (applicable to CAD, USD, INR, JPY, MXN, PHP and BRL), our system will automatically add taxes upon customer checkout. Please see below for a list of important price type codes.</br>

> Prices without tax included (CAD, USD, INR, JPY, MXN, PHP and BRL)</br>
> 01 – Recommended retail prices in CAD, USD and BRL, without tax included</br>
> 41 – Agency prices in CAD, USD and BRL, without tax included</br>
> 03 – Fixed retail prices in CAD, USD and BRL, without tax included</br>
</br>

> Prices with tax included (EUR, GBP, AUD, NZD and ZAR)</br>
> 02 – Recommended retail prices in the EUR, GBP, AUD, NZD, ZAR, JPY and MXN, with tax included</br>
> 42 – Agency prices in the EUR, GBP, AUD, NZD, ZAR, JPY and MXN, with tax included</br>
> 04 – Fixed retail prices in the EUR, GBP, AUD, NZD, ZAR, JPY and MXN, with tax included" </br>

### Correct Usage (example)	</br>
 
Info               | Excel                       | ONIX 2.1                   | ONIX 3.0
-------------- | --------------------------- | ---------------------------|---------------------------
**Reference Name** |Price: 7.99</br>Currency: CAD|`<Price> `</br>`<PriceTypeCode>41</PriceTypeCode> `</br>`<PriceAmount>12.99</PriceAmount> `</br>`<CurrencyCode>CAD</CurrencyCode> `</br>`</Price> `</br>|`<Price> `</br>`<PriceType>02>/<PriceType> `</br>`<PriceAmount>13.99</PriceAmount> `</br>`<CurrencyCode>GBP</CurrencyCode> `</br>`</Price> `</br> 
**Short Tag**      |N/A|`<price>`</br> `<j148>41</j148> `</br>`<j151>12.99</j151> `</br>`<j152>CAD</j152> `</br>`</price>`</br> |`<price>`</br>`<x462>02</462> `</br>`<j151>13.99</j151> `</br>`<j152>GBP</j152> `</br>`</price>`</br> 

### :warning: Common Errors (example)	</br>
  * Incorrect price: $3.99</br>
  * Incorrect price: 1,299.99</br>
  * Incorrect currency in Excel: cad, CA</br>

### Notes</br>
**Excel and ONIX**: JPY prices must be listed as a whole number with zero decimal values. Hiding decimal places with values other than zero will cause your entry to **fail**. 

MXN prices must also be listed as whole numbers with zero decimal values. For MXN pricing, if decimals are provided, the prices will be rounded up or down (e.g. 249.25 MXN will be rounded to 249 MXN, while 249.75 MXN will be rounded to 250 MXN). 

In both Excel and ONIX free titles must be listed with a 0 or 0.00 value.

<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>

## Price Effective Date & Price Date Role (ONIX only)	
### Definition</br>
Price Effective Date (ONIX 2.1) and Price Date Role (ONIX 3.0) composites allow you to schedule promotional prices with your ONIX feed.

### Best Practice	</br>
Rakuten Kobo supports the three price method only: 
  > * Ensure your starting regular price has an end date. Otherwise, our system won’t know to look for a new price.</br>
  > * Ensure the promo price has both a start and end date. </br>
  > * Ensure your regular price is reinstated by including a new start date. All dates are inclusive: they start at 0:00 and end at 23:59 EST of the specified start and end dates. 

### Correct Usage (example)	</br>
Example of a sample scheduled price reduction, with embedded comments for clarification:

ONIX 2.1 example (with embedded notes for clarification):</br>
`<price>`</br>
`<j148>41</j148>`</br>
`<j151>7.99</j151>`</br>
`<j152>USD</j152>`</br>
`<j162>20151222</j162>`</br>
`</price>`</br>
**--- the above price will end at 23:59 EST on Dec 22**</br>
`<price>`</br>
`<j148>41</j148>`</br>
`<j151>3.99</j151>`</br>
`<j152>USD</j152>`</br>
`<j161>20151223</j161>`</br>
`<j162>20151230</j162>`</br>
`</price>`</br>
**--- the promo price starts at 0:00 EST Dec 23 and ends 23:59 EST Dec 30**</br>
`<price>`</br>
`<j148>41</j148>`</br>
`<j151>7.99</j151>`</br>
`<j152>USD</j152>`</br>
`<j161>20151231</j161>`</br>
`</price>`</br>
**--- the regular price is reinstated at 0:00 EST Dec 31</br>
Onix 3.0 uses the PriceDateRole tags where PriceDateRole 14 = From Date and PriceDateRole 15 = Until Date**</br>
`<Price>`</br>
`<PriceType>01</PriceType>`</br>
`<PriceAmount>10.00</PriceAmount>`</br>
`<CurrencyCode>USD</CurrencyCode>`</br>
`<PriceDate>`</br>
`<PriceDateRole>15</PriceDateRole>`</br>
`<Date>20151221</Date>`</br>
`</PriceDate>`</br>
`</Price>`</br>
**--- the above price will end at 23:59 EST on Dec 21**</br>
`<Price>`</br>
`<PriceType>01</PriceType>`</br>
`<PriceAmount>8.00</PriceAmount>`</br>
`<CurrencyCode>USD</CurrencyCode>`</br>
`<PriceDate>`</br>
`<PriceDateRole>14</PriceDateRole>`</br>
`<Date>20151222</Date>`</br>
`</PriceDate>`</br>
`<PriceDate>`</br>
`<PriceDateRole>15</PriceDateRole>`</br>
`<Date>20151230</Date>`</br>
`</PriceDate>`</br>
`</Price>`</br>
**--- the promo price starts at 0:00 EST on Dec 22 and ends 23:59 EST Dec 30**</br>
`<Price>`</br>
`<PriceType>01</PriceType>`</br>
`<PriceAmount>10.00</PriceAmount>`</br>
`<CurrencyCode>USD</CurrencyCode>`</br>
`<PriceDate>`</br>
`<PriceDateRole>14</PriceDateRole>`</br>
`<Date>20151231</Date>`</br>
`</PriceDate>`</br>
`</Price>`</br>
**--- the regular price is reinstated at 0:00 EST on Dec 31**</br>


<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>

## Publishing Status	
### Definition</br>
Your eBook's publishing status.

### Best Practice	</br>
> To place your title for sale or preorder, indicate active. To remove your title from sale, indicate deactivated.

### Correct Usage (example)	</br>
Info               | Excel                       | ONIX 2.1 and 3.0
-------------- | --------------------------- | --------------------------- 
**Reference Name** |Publishing Status: active OR deactivated| `<PublishingStatus>02</PublishingStatus>`</br>
**Short Tag**      |N/A                             |`<b394>02</b394>`</br>
### :warning: Common Errors (example)	</br>
Excel: "inactive" instead of "deactivated"

### Notes</br>
ONIX: We are only reading the `<PublishingStatus>` or `<b394>` composite for activations and deactivations. A value of 04 will activate a book. A value of 02 will indicate that the book should be put on preorder (note that Rakuten Kobo also supports Public Announcement Date: <PublishingDateRole> code 09). Any other value will quarantine the book. Any titles listed as Forthcoming (02) or Active (04) will be activated. All others will be deactivated, so we encourage you to review and update all of your titles. Please pay special attention to any titles with value 00 (Unspecified).  


<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>


## Publication Date	
### Definition</br>
Your eBook's initial availability date, as it should appear on the product page on the Kobo store.
It is a display value only. 

### Best Practice	</br>
> Excel: Please use the format: YYYY-MM-DD.
> If no publication date is included, the default date is set as December 2009.

### Correct Usage (example)	</br>
Info               | Excel                       | ONIX 2.1                   | ONIX 3.0
-------------- | --------------------------- | ---------------------------|---------------------------
**Reference Name** |<sub>Publication Date: 2010-01-16</sub>| `<PublicationDate>20130315</PublicationDate>`</br>|`<PublishingDate>`</br>`<PublishingDateRole>01</PublishingDateRole>`</br>`<Date>20150219</Date>`</br>`</PublishingDate>`</br> 
**Short Tag**|N/A|`<b003>20130315</b003>`</br>|`<publishingdate>`</br>`<x448>01</x448>`</br>`<b306>20150219</b306>`</br>`</publishingdate>`</br> 
### :warning: Common Errors (example)	</br>
* Excel: 21/11/2013</br>
* Excel: 2013</br>
* Excel: 2013/11/21</br>


<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>


## On Sale Date (ONIX 2.1) / Embargo Date (ONIX 3.0)	
### Definition</br>
The On Sale Date/Embargo Date is when your title is made active on site. If your book is available for preorder, it is the date it goes from preorder to regular sale. This is also the date the epub will be available for download to customer libraries.

### Best Practice	</br>
> If no On Sale/Embargo date is provided, the default date is the date metadata is ingested.</br>
> Excel: The required date format is YYYY-MM-DD. 


### Correct Usage (example)	</br> 
Info               | Excel                       | ONIX 2.1                   | ONIX 3.0
-------------- | --------------------------- | ---------------------------|---------------------------
**Reference Name**|  <sub>OnSale Date: 2010-01-16</sub>   | **On Sale Date**</br>`<OnSaleDate>20150219</OnSaleDate>`</br>|**Embargo Date**</br>`<PublishingDate>`</br>`<PublishingDateRole>02</PublishingDateRole>`</br>`<Date>20150219</Date>`</br>`</PublishingDate> `</br>
**Short Tag**|N/A|`<j143>20150219</j143>`</br>|`<publishingdate> `</br>`<x448>02</x448> `</br>`<b306>20150219</b306>`</br>`</publishingdate>`</br> 
### :warning: Common Errors (example)	</br>
* Excel: 21/11/2013</br>
* Excel: 2013</br>

### Notes</br>
This is the date on which products are available for purchase by customers. With ONIX, if you want to prevent early sales, EDItEUR insists that this date is provided along with Publication Date to distinguish between the date of publication and date of availability for sale. If the book is made available for preorder before the On Sale Date/Embargo Date, the On Sale Date/Embargo Date ensures the epub file is not delivered to customers until that date.


<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>

## Related Product
### Definition</br>
The ISBN of the print version of your book, that partners who sell print books can use to link print product page to ebook product page.  

### Best Practice	</br>
> In Excel, use column C "Related ISBN". </br>
> In ONIX, RelationCode 06 equals "alternative format", you can also use Relation code 13 for specific "Epublication based on (print product)"</br>
  > * ProductIDType 15=ISBN-13.</br>
  > * ProductForm BA=Book.</br>
  > * ProductForm AA=Audio.</br>

> Multiple RelatedProduct could be linked to 1 title, as soon as the corresponding ISBN are different in each RelatedProduct composites.

### Correct Usage (example)	</br>
Info               | Excel                       | ONIX 2.1 and 3.0
-------------- | --------------------------- | --------------------------- 
**Reference Name** |Related ISBN:9782246731412                             |`<RelatedProduct>`</br>`<RelationCode>06</RelationCode>`</br>`<ProductIdentifier>`</br>`<ProductIDType>15</ProductIDType>`</br>`<IDValue>9782246731412</IDValue>`</br>`</ProductIdentifier>`</br>`<ProductForm>BA</ProductForm>`</br>`</RelatedProduct>`</br> 
**Short Tag**      |N/A                              |`<relatedproduct>`</br>`<h208>13</h208>`</br>`<productidentifier>`</br>`<b221>15</b221>`</br>`<b244>9783540261698</b244>`</br>`</productidentifier>`</br>`<b012>BA</b012>`</br>`</relatedproduct>`</br>   

### Notes</br>
While Kobo Inc does not itself use the `<RelatedProduct>` composite, it is a useful and necessary tag for many of our partners who sell physical books.


<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>

## Series Name/Series Number	
### Definition</br>
Your eBook's series name as it should appear on the Kobo store and your eBook's number or sequence within a series as it should appear on the Kobo store.

### Best Practice	</br>
> **Series Name**</br>
> Please indicate this in the series fields of your metadata, not in the title of the your ebook. For the European book trade, if both Series and Publisher Collection (Collection éditoriale, code 11) are used in your metadata, please make sure to use the appropriate code (code 10 for Series, code 11 for Collection éditoriale)</br>

> **Series Number**</br>
  > * Please indicate this as a numerical value, not as text.</br>
  > * These should always be a numeric value, no text (e.g. 1).</br>
  > * Novellas, short stories that bridge two parts together: Series number can be set to a decimal, no text (e.g. 1.5, 2.3).</br>
  > * Collections/Omnibus Editions: Ranges acceptable (e.g. 1-3, 3-6, etc.).Please don't use the words "omnibus" or "collection" in Part metadata information.</br>

### Correct Usage (example)	</br>

Info               | Excel                       | ONIX 2.1                   | ONIX 3.0
-------------- | --------------------------- | ---------------------------|---------------------------
**Reference Name** |Series: Lord of the Rings</br></br># in series: 5                               |`<Series>`</br>`<TitleOfSeries>Lord of the Rings</TitleOfSeries>`</br>`<NumberWithinSeries>Volume 5</NumberWithinSeries>`</br>`</Series>`</br>                            |`<Collection>`</br>`<CollectionType>10</CollectionType>`</br>`<TitleDetail>`</br>`<TitleType>01</TitleType>`</br>`<TitleElement>`</br>`<TitleElementLevel>02</TitleElementLevel>`</br>`<TitleText>Lord of the Rings</TitleText>`</br>`</TitleElement>`</br>`<TitleElement>`</br>`<TitleElementLevel>01</TitleElementLevel>`</br>`<PartNumber>5</PartNumber>`</br>`</TitleElement>`</br>`</TitleDetail>`</br>`</Collection>`</br>  
**Short Tag**      |N/A                             |`<series>`</br>`<b018>Lord of the Rings</b018>`</br>`<b019>5</b019>`</br>`</series>`</br>                            |`<collection>`</br>`<x329>10</x329>`</br>`<titledetail>`</br>`<b202>01</b202>`</br>`<titleelement>`</br>`</x409>02</x409>`</br>`<b203>Lord of the Rings</b203>`</br>`</titleelement>`</br>`<titleelement>`</br>`</x409>01</x409>`</br>`<x410>5</x410>`</br>`</titleelement>`</br>`</titledetail>`</br>`</collection>`</br>
**Character Limits**	|250                   |250                         |250

### Notes</br>
* ONIX 3.0. Kobo system stores, but not make use of `<CollectionType>11</CollectionType>`= Collection Editoriale, for now.  
However, in order to make sure the series information is correctly displayed on the Kobo Store, please use the appopriate `<CollectionType>10</CollectionType>`.
* Kobo supports only 1 series information.



<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>


## Audience Age Range - From/Audience Age Range - To	
### Definition</br>
Especially for children's, teenages and school books. 
The "From" age value for your eBook's audience age range. The "To" age value for your eBook's audience age range.

### Best Practice	</br>
> If your title has a specific age range,  in this field you can specify the "from" or "to" values for the beginning age or age limit. 

> The "from" field can be left blank if you prefer to simply specify an age limit in the Audience Age Range - To field. Similarly, the "to" field can be left blank if your title has no age limit.

> Please use a numerical value, not text.

### Correct Usage (example)	</br>
Info               | Excel                       | ONIX 2.1 and 3.0
-------------- | --------------------------- | --------------------------- 
**Reference Name** |Audience Age Range - From: 8 </br>Audience Age Range - To: 12|Please note that although both "to" and "from" ranges are provided in the examples below, you have the option to use either of these values on its own. </br> </br>This example, tell us this title is for Interest Ages 6+</br></br>`<AudienceRange> `</br>`<AudienceRangeQualifier>17</AudienceRangeQualifier> `</br>`<AudienceRangePrecision>03</AudienceRangePrecision> `</br>`<AudienceRangeValue>6</AudienceRangeValue> `</br>`</AudienceRange>`</br> 
**Short Tag**      |N/A                             | The following composite tells us that this title is for Interest Ages 8-12.</br></br>`<audiencerange> `</br>`<b074>17</b074> `</br>`<b075>03</b075> `</br>`<b076>8</b076> `</br>`<b075>04</b075> `</br>`<b076>12</b076> `</br>`</audiencerange>`</br></br>If you’re sending us Interest Age, Years or Audience Range Qualifier 17, then you can actually use just the “From” and “To” audience range precision tags. Here’s an example:</br>`<audiencerange> `</br>`<b074>17</b074> `</br>`<b075>03</b075> `</br>`<b076>8</b076> `</br>`<b075>04</b075> `</br>`<b076>12</b076> `</br>`</audiencerange>`</br> The above translates to ages 8 years old to 12 years old."    

### :warning: Common Errors (example)	</br>
Incorrect: eight

### Notes</br>
Rakuten Kobo system ingests and stores the Age Range information, but it's not used on our store currently. 



<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>

## Product Availability	
### Definition</br>
Indicates if a product is available. `<ProductAvailability>` should carry a datestamp attribute to indicate how current the data is.

### Best Practice	</br>
> This field is mandatory when the `<SupplyDetail>` composite is used.

### Correct Usage (example)	</br>
ONIX 3.0 only.
`<ProductAvailability datestamp="20110517">10</ProductAvailability>`</br>

### Notes</br>
Kobo reads ProductAvailability in Onix 3. </br>Mandatory in the `<SupplyDetail>` composite: 
</br>Code List: https://ns.editeur.org/onix/en/65 </br>
ONIX 3: SupplyDate with SupplyDateRole = '08' required when ProductAvailability = '10' (List 65).


<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>

## Master Brand	
### Definition</br>
Your eBook or its series' master brand. Used only for branded media properties carrying, for example, a children’s character brand.


### Best Practice	</br>
> Please list this as it should be displayed, without commas.

### Correct Usage (example)	</br>
Info               | Excel                       | ONIX 2.1                   | ONIX 3.0
-------------- | --------------------------- | ---------------------------|---------------------------
**Reference Name** | Main Character (brand): Sesame Street|`<OtherText>`</br>`<TextTypeCode>98</TextTypeCode>`</br>`<Text>Sesame Street</Text>`</br>`</OtherText> `</br>|`<TitleDetail>`</br>`<TitleType>01<\TitleType>`</br>`<TitleElement> `</br>`<TitleElementLevel>05</TitleElementLevel>`</br>`<TitleText>Sesame Street</TitleText> `</br>`</TitleElement> `</br>`</TitleDetail>`</br> 
**Short Tag**      |N/A                             |`<othertext>`</br>`<b102>98</b102>`</br>`<d104>Sesame Street</d104>`</br>`</othertext>`</br>|`<TitleDetail> `</br>`<b202>01</b202>`</br>`<TitleElement>`</br>`<x409>05</x409>`</br>`<b203>Sesame Street</b203>`</br>`</TitleElement>`</br>`</TitleDetail>`</br> 
**Character Limits**	|250                   |250                         |250



<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>

## Subtitle	
### Definition</br>
Your eBook's subtitle as it should appear on the product page.

### Best Practice	</br>
> Please refrain from appending "A" or "The" to the end of the title as it might interfere with search functions. Also, please refrain from adding the subtitle in the title field and use the appropriate Excel field or ONIX tag.
> For correct usage of Subtitle within the title composite please see the entry for Title.

### Correct Usage (example)	</br>
Info               | Excel                       | ONIX 2.1 and 3.0
-------------- | --------------------------- | --------------------------- 
**Reference Name** |Subtitle: Left Shark's Park Lark                             |`<Subtitle>Left Shark's Park Lark</Subtitle>`</br> 
**Short Tag**      | N/A                            |`<b029>Left Shark's Park Lark</b029>`</br>   
**Character Limits**	|250|250

### Notes</br>
Book titles, subtitles, series titles or author fields that include extraneous words that are not actually part of the official title, subtitle, series title or author name are not acceptable and lead to confusion and the corruption of metadata standards. We respectfully request that you ensure your catalog of titles does not include such details so that the overall Kobo catalog can offer the purest experience for our customers around the world.

Please consult [BIC Statement on Best Practice for Subtitle Field in Metadata Feeds](http://www.bic.org.uk/files/pdfs/BIC%20Statement%20on%20Best%20Practice%20for%20Sub-title%20field%20FINAL%209th%20March%202018.pdf).

<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>

## Imprint	
### Definition</br>
Your imprint, or the marketing brand you want to apply to your book, as you want it to appear on the product page on the Rakuten Kobo Store.  
Strongly recommanded, especially if different from Publisher's name. 

### Best Practice	</br>
> 

### Correct Usage (example)	</br>
Info               | Excel                       | ONIX 2.1 and 3.0
-------------- | --------------------------- | --------------------------- 
**Reference Name** |Imprint: Your Imprint| `<Imprint>`</br> `<ImprintName>Imprint Imprint</ImprintName>`</br> `</Imprint>`</br> 
**Short Tag**      |  N/A                           | `<imprint>`</br> `<b079>Imprint Imprint</b079>`</br> `</imprint>`</br> 
  
**Character Limits**	|250|250


<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>

# Audiobooks Specific Metadata
For Audiobooks, specific metadata have to be added to your metadata feed. 

## Product Form	
*Required Field* - Based on [Code List 150](https://ns.editeur.org/onix/en/150) (ONIX 3.0 - Code list 7 in ONIX 2.1) - If `<ProductForm>` begins with 'A', metadata.format will be automatically recognised as AUDIO. </br>
  
Should be informed within the `<DescriptiveDetail>` composite. 


### Correct Usage (example)	</br>
Info               | Excel                       | ONIX 2.1 and 3.0
-------------- | --------------------------- | --------------------------- 
**Reference Name** |Detected by use of the Audiobooks template| `<ProductForm>AA</ProductForm>`</br> 
**Short Tag**      |  N/A                           | `<b012>AA</b012>`</br> 
  

<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>


## AudioBook Edition	
*Required Field* - The Edition of your audiobook (Abridged or unabridged version). For unabridged, indicate UBR, for abridged, indicate ABR.</br>
  
Should be informed within the `<DescriptiveDetail>` composite. 


Info               | Excel                       | ONIX 2.1                   | ONIX 3.0
-------------- | --------------------------- | ---------------------------|---------------------------
**Reference Name** | Audiobook Edition col. C of the Template |`<EditionTypeCode>UBR</EditionTypeCode> `</br> or `<EditionTypeCode>ABR</EditionTypeCode> `</br>|`<EditionType>UBR</EditionType>`</br> or `<EditionType>ABR</EditionType>`</br> 
**Short Tag**      |N/A                             |`<b056>UBR</b056>`</br> or`<b056>ABR</b056>`</br>|`<x419>UBR</x419>`</br> or `<x419>ABR</x419>`</br> 
  

<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>


## Contributor Type	
Add explicit support for: 
</br>
  * E03 Narrator
  * E07 Reader
  * E08 Performed by
  * E09 Speaker Of a speech
  
Base on EDItEUR [Code list 17](https://ns.editeur.org/onix/en/17)


### Correct Usage (example)	</br>
Info               | Excel                       | ONIX 2.1 and 3.0
-------------- | --------------------------- | --------------------------- 
**Reference Name** |Contributor Type col. T of the template</br> 3 contributors max.| `<ContributorRole>E03</ContributorRole>`</br> 
**Short Tag**      |  N/A                           | `<b035>E03</b035>`</br> 
  

<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>

## Duration
Parse the duration extent for time-duration information. Store both the ONIX values and the value normalized to seconds.
  
Base on EDItEUR </br>
[Code list 23](https://ns.editeur.org/onix/en/23) - `<ExtendType>` code  09 = Duration.</br>
[Code list 24](https://ns.editeur.org/onix/en/24) - `<ExtendUnit>` minutes; hours ; seconds etc… Only codes 04, 05, 06, 14, 15 and 16 are supported by Kobo as ExtentUnit values for duration extent. Other values will be ignored: 

Value               | is supported by Kobo                       | Description
-------------- | --------------------------- | ---------------------------
02| No| Words (will Fail ingestion) 
03| No| Pages (will Fail ingestion)
04| Yes| Hours (integer and decimals) 
05| Yes| Minutes (integer and decimals)
06| Yes| Seconds (integer only)
11| No| Words (will be ignored)
14| Yes| Hours HHH
15| Yes| Hours and minutes HHHMM
16| Yes| Hours minutes seconds HHHMMSS
17| Yes| Bytes
18| Yes| Kbytes
19| Yes| Mbytes


### Correct Usage (example)	</br>
Info               | Excel                       | ONIX 2.1 and 3.0
-------------- | --------------------------- | --------------------------- 
**Reference Name** |N/A | `<Extent>`</br> `<ExtentType>09</ExtentType>`</br> `<ExtentValue>457</ExtentValue>`</br> `<ExtentUnit>05</ExtentUnit>`</br> `</Extent>`</br> 
**Short Tag**      |  N/A                           | `<extend>`</br>`<b218>09</218>`</br>`<b219>457</b219>`</br>`<b220>16</b220>`</br>`</extend>`</br> 
  

<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>

## Filesize
Parse the size extent for file-size information. Store both the ONIX values and the value normalized to bytes

Information is stored in Rakuten Kobo system, but is not used. 

Based on EDItEUR</br>
[Code list 23](https://ns.editeur.org/onix/en/23) - `<ExtendType>` code  22 = FileSize.</br>


### Correct Usage (example)	</br>
Info               | Excel                       | ONIX 2.1 and 3.0
-------------- | --------------------------- | --------------------------- 
**Reference Name** |N/A | `<Extent>`</br>`<ExtentType>22</ExtentType>`</br>`<ExtentValue>19</ExtentValue>`</br>`<ExtentUnit>500</ExtentUnit>`</br>`</Extent>`</br> 
**Short Tag**      |  N/A                           | `<extend>`</br>`<b218>22</218>`</br>`<b219>19</b219>`</br>`<b220>500</b220>`</br>`</extend>`</br> 
  

<sub>:back:[Table of Contents](#table-of-contents)</sub>
</br>
</br>
