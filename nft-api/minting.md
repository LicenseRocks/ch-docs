---
label: Mint
tags: [minting, nft]
order: 5
authors:
  - name: Artur Chmaro
    email: artur@licenserocks.de
    avatar: ../static/artur.jpeg
    link: https://twitter.com/ArtiChmaro
  - name: Adam Leszczyński
    email: adam.leszczynsky@gmail.com
    link: https://alsd.app
    avatar: https://avatars.githubusercontent.com/u/20825919
---
# Mint new NFTs

In this section you will learn how to use our endpoints for minting new NFT tokens.
It is crucial to remain the order of the requests in the following documentation.
## 1. Batch mint

Use below endpoint in order to create multiple draft NFTs in your instance.
Send array with one element if you want to create just single draft NFT.

```
POST https://{INSTANCE_URL}/api/public/batchMint
```

!!!warning
This request must contain [Authorization](/authorization.md) header with your token.
!!!

```json Payload (application/json)
[
  {
    "title": "Crypto Punk",
    "amount": 1,
    "price": 9999.5,
    "currency": "EUR",
    "collectionTemplateId": 1,
    "biddingEnabled": false,
    "status": "draft"
  }
]
```

```json Response
{
  "nfts": [
    {
      "id": 919,
      "amount": 10,
      "availableAmount": 0,
      "approved": false,
      "arweaveTx": null,
      "chainTx": null,
      "creatorPublicAddr": "0xBF2B65DC13eCB2D52F1507350DeE347B12F18200",
      "contractAddr": "0x7F22bF652e54Db9E79DF9f9d7cBeea2BddBf3d1a",
      "contractName": "AUCTIONABLE_ERC1155",
      "contractNetwork": "maticTestnet",
      "coverKey": null,
      "category": null,
      "secretPhrase": null,
      "fee": null,
      "feeRecipient": null,
      "payload": {
        "price": 40,
        "title": "Test mint API by ADI 6",
        "amount": 10,
        "status": "draft",
        "currency": "EUR",
        "biddingEnabled": false,
        "collectionTemplateId": 26
      },
      "price": 4000,
      "priceEths": "NaN",
      "priceCurrency": "EUR",
      "priceType": "FIXED",
      "downloadable": false,
      "title": "Test mint API by ADI 6",
      "creatorId": 240,
      "useCaseId": 2,
      "collectionTemplateCategoryId": 10,
      "collectionTemplateId": 26,
      "upgradeable": false,
      "tokenId": null,
      "newTokenId": null,
      "oldTokenId": null,
      "status": "draft",
      "releaseAt": "2023-06-22T12:56:03.923Z",
      "biddingEnabled": false,
      "createdAt": "2023-06-22T12:56:03.923Z",
      "updatedAt": "2023-06-22T12:56:03.924Z",
      "deletedAt": null,
      "fractionalized": false,
      "redeemable": false,
      "qrcodePrintfileId": null,
      "salesContractUrl": null,
      "organizationId": 5,
      "collectionTemplate": {
        "id": 26,
        "name": "High Resolution Image",
        "subline": null,
        "iconName": "images",
        "iconPrefix": "far",
        "logoUrl": null,
        "imageUrl": null,
        "defaultValue": {},
        "schema": {
          "steps": {
            "...": "..."
          }
        },
        "contractName": "",
        "contractAddr": null,
        "network": "",
        "biconomyApiKey": null,
        "biconomyApiId": "",
        "abiCode": null,
        "createdAt": "2021-05-28T11:15:57.554Z",
        "updatedAt": "2022-05-10T20:50:57.829Z",
        "collectionTemplateCategoryId": 10,
        "organizationId": null,
        "type": "megaflow",
        "typeformId": null,
        "wertCompatible": false,
        "approved": true,
        "editType": "master",
        "kycProvider": "platform",
        "paymentProviders": [
          "secupay"
        ],
        "licenseMetricId": null
      }
    }
  ],
  "status": "ok"
}
```

!!!
Consider storing NFT ID on your end. It can be useful for future calls to our API.
!!!

---

## 2. Cover (create/update)

Every NFT should contain cover file. Below endpoint allows to set it.

```
POST https://{INSTANCE_URL}/api/public/nft/{nftId}/coverFile
```

!!!warning
This request must contain [Authorization](/authorization.md) header with your token.
!!!

### Endpoint Details:

This endpoint utilizes multipart/form-data content type. Make sure to specify this in your Content-Type header as multipart/form-data; boundary=<your-boundary-value>.

This endpoint accepts form-data (`Content-Type: multipart/form-data; boundary=something`). One value is called `file` and it's binary file. The second value is `destination` of the storage you want to use to upload your Cover file. It is the string - either `s3` or `arweave`. Default value is `s3`, and if you don't want to change the storage to `arweave`, you can omit this value.

### Parameters:

There are two form-data parameters that this endpoint accepts:

1. file: This parameter represents the binary data of the file you want to upload. The file should be included in the form-data request body under this key.

2. destination: This parameter indicates the storage service you intend to use for uploading your cover file. It accepts a string value that is either s3 or arweave. By default, the destination is set to s3. If you wish to use s3 as your storage service, this parameter can be omitted from your request. However, if you prefer to use arweave as your storage service, make sure to include this parameter with the value arweave in your request.

```Payload (multipart/form-data)
{
  file: file <binary>,
  destination: String? ("s3" | "arweave")
}
```

```json Response
{
  "id": 1,
  "amount": 100,
  "arweaveTx": null,
  "chainTx": null,
  "biddingEnabled": true,
  "downloadable": true,
  "title": "Beach boys",
  "priceType": "CUSTOM",
  "creatorPublicAddr": "0x8a2e0A933C5D7e26C69ea5600c62BBd35a190655",
  "discounts": [ ],
  "Files": [],
  "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0xca5ab7a0f61b1b14174cfb96b1d4178e7350ba80/nftFiles/1/cover/sample-image.jpg",
  "slug": "1-sample-nft"
}
```

## 3. Release

Once you create draft NFT, assign cover and upload metadata you can finally mint the token on the blockchain:

```
POST https://{INSTANCE_URL}/api/public/nft/{nftId}/release
```

!!!warning
This request must contain [Authorization](/authorization.md) header with your token.
!!!

```json Response
{
  "id": 1,
  "amount": 100,
  "arweaveTx": null,
  "chainTx": null,
  "biddingEnabled": true,
  "downloadable": true,
  "title": "Hamburg's beach boys",
  "priceType": "CUSTOM",
  "creatorPublicAddr": "0x8a2e0A933C5D7e26C69ea5600c62BBd35a190655",
  "discounts": [],
  "payload": {
    "externalUrl": "https://mywebsite.com/123",
    "someAttribute": "unique"
  },
  "Files": [],
  "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0xca5ab7a0f61b1b14174cfb96b1d4178e7350ba80/nftFiles/1/cover/sample-image.jpg",
  "slug": "1-sample-nft",
  "status": "released"
}
```

## 4. Metadata
Each NFT ID to may represent different token type, which may have its own metadata, supply and other attributes.
Below endpoint allows to set them. You may treat metadata as JSON object.

```
POST https://{INSTANCE_URL}/api/public/metaFile
```

!!!warning
This request must contain [Authorization](/authorization.md) header with your token.
!!!

```json Payload (application/json)
{
  "externalUrl": "https://mywebsite.com/123",
  "someAttribute": "unique"
}
```

```json Response
{
  "id": 1,
  "amount": 100,
  "arweaveTx": null,
  "chainTx": null,
  "biddingEnabled": true,
  "downloadable": true,
  "title": "Hamburg's beach boys",
  "priceType": "CUSTOM",
  "creatorPublicAddr": "0x8a2e0A933C5D7e26C69ea5600c62BBd35a190655",
  "discounts": [],
  "payload": {
    "externalUrl": "https://mywebsite.com/123",
    "someAttribute": "unique"
  },
  "Files": [],
  "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0xca5ab7a0f61b1b14174cfb96b1d4178e7350ba80/nftFiles/1/cover/sample-image.jpg",
  "slug": "1-sample-nft"
}
```

---

That's it! Your NFT is minted, it has its own Cover image and Metadata file.