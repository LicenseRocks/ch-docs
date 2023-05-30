---
label: Fetch data
tags: [manage, nft]
order: 3
authors:
  - name: Artur Chmaro
    email: artur@licenserocks.de
    avatar: ../static/artur.jpeg
    link: https://twitter.com/ArtiChmaro
  - name: Igor Klepacki
    email: igor@licenserocks.de
    link: https://twitter.com/igorklepacki
    avatar:
---

# Fetch information about NFts

In this section you will learn how to use our endpoints for getting certain information about tokens listed at your marketplace.

## List of recent NFTs

Use below endpoint in order to get list of most recent NFTs.

```
GET https://{INSTANCE_URL}/api/public/nfts
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
      "discounts": [],
      "Files": [],
      "coverSrc": null,
      "slug": "1-crypto-punk"
    }
  ]
}
```

## Get all NFTs

Get list of all NFTs

```
GET https://{INSTANCE_URL}/api/nfts
```

```json Response
{
  "data": [
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
      "Files": [],
      "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0xca5ab7a0f61b1b14174cfb96b1d4178e7350ba80/nftFiles/1/cover/sample-image.jpg",
      "slug": "1-sample-nft"
    }
  ],
  "meta": {
    "currentPage": 1,
    "offset": 10,
    "pageCount": 5,
    "totalCount": 54
  },
  "error": null
}
```

## PDF proof of NFT

Returns the PDF (file) proof of NFT. Proof contains smart contract address, transaction hash and other information about given token.

```
GET https://{INSTANCE_URL}/api/public/nft/{nftId}/pdf
```

## Copyrights shares of NFT

Use below endpoint in order to get copyrights and royalty fee collectors.

```
GET https://{INSTANCE_URL}/api/public/nft/{nftId}/copyrights
```

## Owners of a specific NFT

Use below endpoint in order to get the owners of a specific NFT.

```
GET https://{INSTANCE_URL}/api/public/nft/{nftId}/owners
```

```json Response
{
  "owners": []
}
```

## Trading history of a specific NFT

Returns the trading history of a specific NFT

```
GET https://{INSTANCE_URL}/api/public/nft/{nftId}/trading_history
```

```json Response
{
  "tradingHistory": []
}
```

## Burn transactions

Use below endpoint in order to fetch burn transactions.

```
GET https://{INSTANCE_URL}/api/public/nft/{nftId}/transactions?type=burn
```

```json Response
{
  "burnTransactions": [
    {
      "id": 3,
      "nftId": 2,
      "name": "burn",
      "contractAddr": "0x7F22bF652e54Db9E79DF9f9d7cBeea2BddBf3d1a",
      "contractNetwork": "maticTestnet",
      "txHash": "0x3401741ca6d4454ff571fc8b95d68d148295b2fb3739edb1b0c87e3526058773",
      "fromAddr": "0x62291b903424a1b86ECff899eF116c0B2C4f099c",
      "toAddr": "0x0000000000000000000000000000000000000001",
      "amount": 1,
      "totalAmount": 1,
      "status": null,
      "txStatus": "initialized",
      "confirmations": 0,
      "txFee": null,
      "priceCents": null,
      "priceCurrency": null,
      "priceEths": null,
      "buyerId": null,
      "sellerId": 1,
      "createdAt": "2021-09-06T08:23:27.974Z",
      "hiddenAt": null,
      "updatedAt": "2021-09-06T08:23:27.975Z"
    }
  ]
}
```
