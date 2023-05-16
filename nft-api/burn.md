---
label: Burn
tags: [manage, nft]
order: 1
authors:
  - name: Artur Chmaro
    email: artur@licenserocks.de
    avatar: ../static/artur.jpeg
    link: https://twitter.com/ArtiChmaro
---

# Burning NFTs

In this section you will learn how to use our endpoints for burning given NFT. Purpuse of burning is to make NFT not usable anymore. You may want to do it in case owner redeems NFT for some good/service.

## How to burn NFT?

Use below endpoint in order to burn NFT. Caller must own given NFT. 

```
GET https://{INSTANCE_URL}/api/nft/:nftId/burn
```

!!!warning
This endpoint will burn all of the NFTs that you currently own!
!!!

```json Payload (application/json)
[
  {
    "reason": "Claiming certificate #123", // that's optional
  }
]
```
