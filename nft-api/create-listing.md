---
label: Creating Listing
tags: [manage, nft]
order: 6
authors:
- name: Kacper Hernacki
  email: kacper@licenserocks.de
  avatar: ../static/kacper.jpeg
  link: https://twitter.com/KacperHernacki
---

# Creating Listing

In this section you will learn how to use our endpoints for creating a new listing for chosen NFT.

### Technical details:

- `{INSTANCE_URL}` is URL of current instance without slash at the end and protocol. e.g. _creators-hub-instance.com_
- `{NFT_ID}` is ID of an NFT, for which listing will be created.
- `{BIDDING_ENABLED}` is describing if an order is listed as bidding.
- `{PRICE}` if no bidding enabled, is describing the constant price of the listing.
- `{STARTING_PRICE}` is describing the starting price for bidding in cents.
- `{CURRENCY}` is describing the currency of a listing. Choices: `"eur"` - EURO, `"usd"` - DOLLAR .
- `{AMOUNT}` is describing how many of this NFT will be listed


## How to create listing?

Use below endpoint in order to create new listing for an NFT.

```
POST https://{INSTANCE_URL}/api/public/nft/{NFT_ID}/listing
```

!!!warning
You have to pass data which examples are listed below
!!!

for bidding:

```json Payload (application/json)
[
  {
    "nftId": 123,
    "biddingEnabled": true,
    "startingPrice": 300,
    "currency": "eur",
    "amount": 5,
    "price": 0
  }
]
```
without bidding:

```json Payload (application/json)
[
  {
    "nftId": 123,
    "biddingEnabled": false,
    "currency": "eur",
    "amount": 5,
    "price": 200
  }
]
```