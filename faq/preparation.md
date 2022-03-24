---
label: NFT preparation
tags: [faq]
authors:
  - name: Artur Chmaro
    email: artur@licenserocks.de
    avatar: ../static/artur.jpeg
    link: https://twitter.com/ArtiChmaro
---

# NFT preparation

## How to prepare metadata before mint?

Providing metadata allows marketplaces to pull that data and display your NFT properly.
Currently the most popular marketplace is OpenSea. Please check their
[official docs](https://docs.opensea.io/docs/metadata-standards) to follow their standards.

Our minting flow automatically supports basic metadata:

```json
{
  "description": "Specify it in the minting flow",
  "external_url": "YourMarketplaceUrl.com",
  "image": "https://link to centralized storage",
  "name": "Specify it in the minting flow",
}
```

However besides that, OpenSea allows to setup more parameters (traits):

![docs.opensea.io](/static/metadata-opensea.png)

We are supporting traits, but before minting please contact our team, so we can enable them for you.

## How to customize collection at the OpenSea?

Please provide your public address to our team after mint, so we can enable editing mode for you.
Following things can be edited via OpenSea UI:
* logo image (350 x 350 px)
* featured image (600 x 400 px)
* banner image (1400 x 400 px)
* collection name
* URL
* description of the collection
* category (collectibiles, music, photography, sports, trading cards, utility)
* twitter account
* creator earnings
* website, discord, instagram, medium, telegram URLs

