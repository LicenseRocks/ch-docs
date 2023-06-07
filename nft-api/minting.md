---
label: Mint
tags: [minting, nft]
order: 5
authors:
  - name: Artur Chmaro
    email: artur@licenserocks.de
    avatar: ../static/artur.jpeg
    link: https://twitter.com/ArtiChmaro
---
# Mint new NFTs

In this section you will learn how to use our endpoints for minting new NFT tokens.
Forget about deploying own smart contracts.

## Batch mint

Use below endpoint in order to create multiple tokens in your instance.
Send array with one element if you want to create just single token.

```
POST https://{INSTANCE_URL}/api/public/batchMint
```

!!!warning
this request must contain Authorization header with your token
!!!

```json Payload (application/json)
[
  {
  "title": "Crypto Punk",
  "amount": 1,
  "price": 9999.5,
  "currency": "EUR",
  "useCaseId": 1,
  "biddingEnabled": false,
  "status": "draft"
  }
]
```

```json Response
{
  "nfts": [
    {
      "id": 1,
      "amount": 1,
      "arweaveTx": null,
      "chainTx": null,
      "biddingEnabled": true,
      "downloadable": true,
      "title": "Crypto Punk",
      "priceType": "CUSTOM",
      "creatorPublicAddr": "0xca5ab7a0f61b1b14174cfb96b1d4178e7350ba80",
      "discounts": [ ],
      "Files": [],
      "coverSrc": null,
      "slug": "1-crypto-punk"
    }
  ]
}
```

!!!
Consider storing NFT id on your end. It can be useful for future calls to our API.
!!!

---

## Cover (create/update)

Every NFT should contain cover file. Below endpoint allows to set it. File might be uploaded to S3 or Arweave

```
POST https://{INSTANCE_URL}/api/public/nft/{nftId}/coverFile
```

!!!warning
this request must contain Authorization header with your token
!!!

```Payload (multipart/form-data)
{
  file: file <binary>
  destination: ("s3"|"arweave")
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

## Metadata
Each token ID to may represent different token type, which may have its own metadata, supply and other attributes.
Below endpoint allows to update them. You may treat metadata as JSON object.

```
POST https://{INSTANCE_URL}/api/public/nft/{nftId}/metaFile
```

!!!warning
this request must contain Authorization header with your token
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

## Release

Once you create draft NFT, assign cover and upload metadata you can release the token to the blockchain:

```
POST https://{INSTANCE_URL}/api/public/nft/{nftId}/release
```

!!!warning
this request must contain Authorization header with your token
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
  "status": "released",
}
```
