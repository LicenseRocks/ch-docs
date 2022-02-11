---
label: Ownership Validation
tags: [manage, nft]
order: 6
authors:
  - name: Kacper Hernacki
    email: kacper@licenserocks.de
    avatar: ../static/kacper.jpeg
    link: https://twitter.com/KacperHernacki
---

# Ownership Validation

In this section you will learn how to use our endpoints for validating ownership of a concrete nft in different networks.

## How to validate an ownership?

Use below endpoint in order to check if a given public address owns concrete NFT in defined network.

```
GET https://{INSTANCE_URL}/api/public/ownership
```

!!!warning
You have to pass data which examples are listed below
!!!

```json Payload (application/json)
[
  {
    "nftId": 123,
    "publicAddr": "0xcc0D1aC7Ec5E09ef11373EF76590EA9942392794",
    "network": "mumbaiTestnet",
    "contractAddress": "0x608a1CDBf0207fBC9c3e5C33bb6Ba1d9cb003613"
  }
]
```

```json Response
{
  "isOwned": true
}
```
