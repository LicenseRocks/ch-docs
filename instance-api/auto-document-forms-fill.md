---
label: Filling PDFs forms programmatically
tags: [pdf, document, legal, contract, forms]
order: 6
authors:
  - name: Igor Klepacki
    email: igor@licenserocks.de
    link: https://twitter.com/igorklepacki
    avatar:
---

# Introduction

Our Instance's API exposes special endpoint with purpose of automatically generating (in other words - filling the PDF form) PDF file with data such as **NFT name**, **NFT creator**, **Mint Date** and so on… for every NFT!

## Endpoint’s details

```
POST https://{INSTANCE_URL}/api/generateSalesContract
```

with JSON payload containing following properties

```json
{
  "pdfUrl": "https://example.com/my-sales-contract.pdf",
  "nftId": 200,
  "save": true
}
```

where:

  - `pdfUrl` is an URL pointing to the PDF file that would be filled with data from our side. NOTE: This property is **optional**, in other words, if no `pdfUrl` is provided, the template to fill is retrieved from instance settings.

  - `nftId` is simply an identifier of NFT basing on which data will be put into appropriate text fields in PDF form

  - `save` is also an **optional** parameter and it is responsible for saving generated contract on our side and attaching it to the existing NFT in the database instead of just returning binary data from the endpoint

## Creating PDF template for sales contracts

As mentioned, the PDF template must be either uploaded via **Settings > General Settings > Contracts** or the URL where PDF is hosted must be provided to the endpoint. But how to send/upload file that is valid and will be correctly filled?

### Creating form and allowed values

Here’s [brilliant article from Adobe introducing to the forms in PDF document](https://www.adobe.com/acrobat/resources/how-to-create-fillable-pdf.html). The forms are kinda industry standard in places where documents have to be filled programatically e.g. government sites. We use this technique as well.

After getting familiar with article linked above, the only remark is fact, that you have to name text fields in form exactly as one of available names in order to have corresponding values put into each gap. The values’ names are self-explanatory and the full list is here:

  - `nftname` - text field named exactly like this will be filled with name of the NFT
  
  - `creatorsname` - text field named exactly like this will be filled with name of the NFT owner

_feel free to contact us by mail (hello@license.rocks) if there is any NFT property that is not present on the list and you want to use it 🚀_

## Example user story

To sum everything up, let’s see what example user story would look like 👀

  1. The user creates PDF with some fancy shapes and illustrations, e.g. circle and triangle.
  2. The user wants to put specific NFT name into the triangle and NFT creators name into the circle
  3. User creates form in PDF editor of choice *(e.g. Adobe Acrobat)* and puts two text fields into the document, one in the triangle and the second in the circle
  4. User names first text field exactly `nftname` and the second one exactly `creatorsname`
  5. User saves the PDF and uploads the file via CreatorsHub instance settings (**Settings > General Settings > Contracts**)
  6. User sends POST HTTP request to
        ```
        https://{INSTANCE_URL}/api/generateSalesContract
        ```
        with payload

        ```json
        {
          "nftId": 200,
          "save": true
        }
        ```
    7. The document that was prepared by user is now filled with properties retrieved from NFT with identifier = 200 and is attached to the NFT itself in the database
