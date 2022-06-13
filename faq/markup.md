---
label: Markup Language
tags: [faq]
authors:
  - name: Kacper Hernacki
    email: kacper@licenserocks.de
    avatar: ../static/kacper.jpeg
    link: https://twitter.com/KacperHernacki
---

# Markup Language

Our platform supports the markup language in few places, such as NFT description, author bio or while creating token process. This solution allows creating amazing, clean and smooth explanations and text areas through the entire platform.

### Markup options in a platform

As it was mentioned above, markup option can be found in places represented by screenshotsand with attached urls:

#### /profile/my-nfts/{nft-slug}

![](/static/markup-nft.png)

#### /profile/personal-information

![](/static/bio-markup.png)

### Editing Markup options in workflows

In Megaflow is implemented a markup for some inputs through workflow. For example in secret phrase, it is possible to type text, which is bold, italic and even linked. To achieve the wanted result, just follow rules described below:

- Italic - `*some italic text*` - italic text between \*
- Bold - `**some bold text**` - bold text between \*\*
- Links - `[linked text](https://www.licenserocks.de)` - link in format `[linked text](url)`
