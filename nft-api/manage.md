---
label: Manage
tags: [manage, nft]
order: 4
authors:
  - name: Artur Chmaro
    email: artur@licenserocks.de
    link: https://twitter.com/ArtiChmaro
---
# Manage your NFTs

In this section you will learn how to use our endpoints for managing tokens on your platform.

## Transfer

Use below endpoint in order to transfer ownership to certain public address.
Public address does not have to be present in current user base.

```
POST https://{INSTANCE_URL}/api/public/nft/{nftId}/transfer
```

!!!warning
this request must contain Authorization header with your token
!!!

```json Payload (application/json)
{
  "destAddr": "0x9e684dae9beb65e828ef8c02d8335e7eea11584a",
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
  "discounts": [ ],
  "Files": [
  {}
  ],
  "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0xca5ab7a0f61b1b14174cfb96b1d4178e7350ba80/nftFiles/1/cover/sample-image.jpg",
  "slug": "1-sample-nft"
}
```

---

!!!
Other endpoints are currently in development...
!!!


