---
label: Fetching collections
tags: [manage, collections, nft]
order: 5
authors:
- name: Kacper Hernacki
  email: kacper@licenserocks.de
  avatar: ../static/kacper.jpeg
  link: https://twitter.com/KacperHernacki
---
# Fetching collections

When it comes to displaying collections on the frontend, you can use the following endpoint to fetch all collections.
Use below endpoint in order to fetch all collections.

```
GET https://{INSTANCE_URL}/api/public/collections
```
Response

```json Response (application/json)
{
  "collections": [
    {
      "id": 1,
      "isPublic": true,
      "name": "Test",
      "footer": "mb",
      "createdAt": "2023-05-11T10:35:47.569Z",
      "updatedAt": "2023-05-11T10:35:47.587Z",
      "userId": 5,
      "user": {
        "avatar": "https://preview-creatorshub.com/images/user-placeholder.png",
        "cover": "",
        "country": "",
        "description": "",
        "companyUser": false,
        "email": "test@example.com",
        "newsletterAgreement": false,
        "locale": "",
        "ethereumPublicAddr": "0xc100124c1C8b863841250F77DA02b32bE799bb3F",
        "id": 5,
        "location": "",
        "facebookUrl": "kacpi",
        "instagramUrl": "kacpi",
        "twitterUrl": "kacpi",
        "websiteUrl": "https://www.random.com",
        "name": "Kacper",
        "seenNotifications": null,
        "username": "John Test",
        "verified": false,
        "isCreator": false,
        "creatorsData": null
      },
      "slug": "1-kacper-meta",
      "projects": [],
      "likes": [],
      "nfts": [
        {
          "amount": 1,
          "availableAmount": 0,
          "Files": [
            {
              "key": "0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3/nftFiles/50003/cover/1D3106E283944252AB676D56B96ADF5D_1_201_a.jpeg",
              "public": true,
              "storageType": "s3",
              "type": "cover"
            }
          ],
          "id": 50003,
          "price": 10000,
          "title": "Ledger",
          "redeemable": false,
          "NftRedeemItem": [],
          "payload": {
            "audio": [
              {
                "path": "Summer Strut.mp3",
                "altName": null,
                "preview": ""
              }
            ],
            "cover": [
              {
                "altName": null,
                "preview": "blob:http://localhost:3000/cd43b1b0-0d93-4732-ad03-48c74667ad45"
              }
            ],
            "owner": "true",
            "price": "100",
            "terms": "true",
            "title": "Ledger",
            "status": "released",
            "contract": "true",
            "currency": "eur",
            "arweaveTx": "MgFUCVmPfD1vhZSB-8NMAmynj2S78abZAdjqiOgE3dQ",
            "useCaseId": 6,
            "amountType": "unique",
            "description": "",
            "licenseType": "private",
            "downloadable": false,
            "nftToUpgrade": null,
            "secretPhrase": "",
            "storageOption": "s3"
          },
          "status": "released",
          "priceCurrency": "EUR",
          "priceType": "FIXED",
          "creatorId": 6,
          "creator": {
            "avatar": "http://localhost:3000/images/user-placeholder.png",
            "cover": "",
            "country": "",
            "description": "",
            "companyUser": false,
            "email": "meta@maeta.com",
            "newsletterAgreement": false,
            "locale": "en",
            "ethereumPublicAddr": "0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3",
            "id": 6,
            "location": "",
            "facebookUrl": "",
            "instagramUrl": "",
            "twitterUrl": "",
            "websiteUrl": "",
            "name": "KacperMeta",
            "seenNotifications": null,
            "username": "KacpiMeta",
            "verified": false,
            "isCreator": false,
            "creatorsData": null
          },
          "NftListing": [],
          "position": 0,
          "label": "Ledger",
          "releaseAt": null,
          "createdAt": null,
          "deletedAt": null,
          "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3/nftFiles/50003/cover/1D3106E283944252AB676D56B96ADF5D_1_201_a.jpeg",
          "slug": "50003-ledger",
          "eventResults": [],
          "updatedAt": null,
          "createdWith": "creatorshub"
        },
        {
          "amount": 1,
          "availableAmount": 0,
          "Files": [
            {
              "key": "0xc100124c1C8b863841250F77DA02b32bE799bb3F/nftFiles/50000/cover/8AD2F397176A4CFFBEC39D5F4C3A39C6.jpeg",
              "public": true,
              "storageType": "s3",
              "type": "cover"
            }
          ],
          "id": 50000,
          "price": 10000,
          "title": "Hacker 001",
          "redeemable": false,
          "NftRedeemItem": [],
          "payload": {
            "cover": [
              {
                "id": 9,
                "key": "0xc100124c1C8b863841250F77DA02b32bE799bb3F/nftFiles/50000/cover/8AD2F397176A4CFFBEC39D5F4C3A39C6.jpeg",
                "type": "cover",
                "nftId": 50000,
                "public": true,
                "altName": null,
                "preview": "https://creatorshub.s3.eu-central-1.amazonaws.com/0xc100124c1C8b863841250F77DA02b32bE799bb3F/nftFiles/50000/cover/8AD2F397176A4CFFBEC39D5F4C3A39C6.jpeg",
                "checksum": null,
                "fileName": "8AD2F397176A4CFFBEC39D5F4C3A39C6.jpeg",
                "fileType": "image/png",
                "metaData": null,
                "createdAt": "2023-03-17T08:38:14.356Z",
                "creatorId": 5,
                "publicUrl": "https://creatorshub.s3.eu-central-1.amazonaws.com/0xc100124c1C8b863841250F77DA02b32bE799bb3F/nftFiles/50000/cover/8AD2F397176A4CFFBEC39D5F4C3A39C6.jpeg",
                "updatedAt": "2023-03-17T08:38:14.355Z",
                "rootFileId": null,
                "storageType": "s3",
                "downloadable": false
              }
            ],
            "owner": "true",
            "price": "100",
            "terms": "true",
            "title": "Hacker 001",
            "status": "released",
            "currency": "eur",
            "useCaseId": 2,
            "amountType": "unique",
            "description": "",
            "licenseType": "private",
            "nftToUpgrade": null,
            "secretPhrase": "",
            "storageOption": "s3",
            "assetSameAsCover": true
          },
          "status": "released",
          "priceCurrency": "EUR",
          "priceType": "FIXED",
          "creatorId": 5,
          "creator": {
            "avatar": "https://preview-creatorshub.com/images/user-placeholder.png",
            "cover": "",
            "country": "",
            "description": "",
            "companyUser": false,
            "email": "test@gmail.com",
            "newsletterAgreement": false,
            "locale": "en",
            "ethereumPublicAddr": "0xc100124c1C8b863841250F77DA02b32bE799bb3F",
            "id": 5,
            "location": "",
            "facebookUrl": "",
            "instagramUrl": "",
            "twitterUrl": "",
            "websiteUrl": "",
            "name": "Kacper",
            "seenNotifications": null,
            "username": "Kacper Hernacki",
            "verified": false,
            "isCreator": false,
            "creatorsData": null
          },
          "NftListing": [
            {
              "id": 7,
              "active": false,
              "activeTill": null,
              "type": "regular",
              "priceCents": 14000,
              "priceCurrency": "EUR",
              "amount": 1
            },
            {
              "id": 8,
              "active": false,
              "activeTill": null,
              "type": "regular",
              "priceCents": 14000,
              "priceCurrency": "EUR",
              "amount": 1
            },
            {
              "id": 9,
              "active": false,
              "activeTill": null,
              "type": "regular",
              "priceCents": 14000,
              "priceCurrency": "EUR",
              "amount": 1
            }
          ],
          "position": 1,
          "label": "Hacker 001",
          "releaseAt": null,
          "createdAt": null,
          "deletedAt": null,
          "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0xc100124c1C8b863841250F77DA02b32bE799bb3F/nftFiles/50000/cover/8AD2F397176A4CFFBEC39D5F4C3A39C6.jpeg",
          "slug": "50000-hacker-001",
          "eventResults": [],
          "updatedAt": null,
          "createdWith": "creatorshub"
        }
      ],
      "quantity": 2
    }
  ]
}
```
## Get collection by Id

Use below endpoint in order to fetch collection by Id.


```
GET https://{INSTANCE_URL}/api/public/collections/${collectionId}
```
 Response

```json Response (application/json)
{
  "collections": [
    {
      "id": 1,
      "isPublic": true,
      "name": "Test",
      "footer": "mb",
      "createdAt": "2023-05-11T10:35:47.569Z",
      "updatedAt": "2023-05-11T10:35:47.587Z",
      "userId": 5,
      "user": {
        "avatar": "https://preview-creatorshub.com/images/user-placeholder.png",
        "cover": "",
        "country": "",
        "description": "",
        "companyUser": false,
        "email": "test@example.com",
        "newsletterAgreement": false,
        "locale": "",
        "ethereumPublicAddr": "0xc100124c1C8b863841250F77DA02b32bE799bb3F",
        "id": 5,
        "location": "",
        "facebookUrl": "kacpi",
        "instagramUrl": "kacpi",
        "twitterUrl": "kacpi",
        "websiteUrl": "https://www.random.com",
        "name": "Kacper",
        "seenNotifications": null,
        "username": "John Test",
        "verified": false,
        "isCreator": false,
        "creatorsData": null
      },
      "slug": "1-kacper-meta",
      "projects": [],
      "likes": [],
      "nfts": [
        {
          "amount": 1,
          "availableAmount": 0,
          "Files": [
            {
              "key": "0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3/nftFiles/50003/cover/1D3106E283944252AB676D56B96ADF5D_1_201_a.jpeg",
              "public": true,
              "storageType": "s3",
              "type": "cover"
            }
          ],
          "id": 50003,
          "price": 10000,
          "title": "Ledger",
          "redeemable": false,
          "NftRedeemItem": [],
          "payload": {
            "audio": [
              {
                "path": "Summer Strut.mp3",
                "altName": null,
                "preview": ""
              }
            ],
            "cover": [
              {
                "altName": null,
                "preview": "blob:http://localhost:3000/cd43b1b0-0d93-4732-ad03-48c74667ad45"
              }
            ],
            "owner": "true",
            "price": "100",
            "terms": "true",
            "title": "Ledger",
            "status": "released",
            "contract": "true",
            "currency": "eur",
            "arweaveTx": "MgFUCVmPfD1vhZSB-8NMAmynj2S78abZAdjqiOgE3dQ",
            "useCaseId": 6,
            "amountType": "unique",
            "description": "",
            "licenseType": "private",
            "downloadable": false,
            "nftToUpgrade": null,
            "secretPhrase": "",
            "storageOption": "s3"
          },
          "status": "released",
          "priceCurrency": "EUR",
          "priceType": "FIXED",
          "creatorId": 6,
          "creator": {
            "avatar": "http://localhost:3000/images/user-placeholder.png",
            "cover": "",
            "country": "",
            "description": "",
            "companyUser": false,
            "email": "meta@maeta.com",
            "newsletterAgreement": false,
            "locale": "en",
            "ethereumPublicAddr": "0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3",
            "id": 6,
            "location": "",
            "facebookUrl": "",
            "instagramUrl": "",
            "twitterUrl": "",
            "websiteUrl": "",
            "name": "KacperMeta",
            "seenNotifications": null,
            "username": "KacpiMeta",
            "verified": false,
            "isCreator": false,
            "creatorsData": null
          },
          "NftListing": [],
          "position": 0,
          "label": "Ledger",
          "releaseAt": null,
          "createdAt": null,
          "deletedAt": null,
          "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3/nftFiles/50003/cover/1D3106E283944252AB676D56B96ADF5D_1_201_a.jpeg",
          "slug": "50003-ledger",
          "eventResults": [],
          "updatedAt": null,
          "createdWith": "creatorshub"
        },
        {
          "amount": 1,
          "availableAmount": 0,
          "Files": [
            {
              "key": "0xc100124c1C8b863841250F77DA02b32bE799bb3F/nftFiles/50000/cover/8AD2F397176A4CFFBEC39D5F4C3A39C6.jpeg",
              "public": true,
              "storageType": "s3",
              "type": "cover"
            }
          ],
          "id": 50000,
          "price": 10000,
          "title": "Hacker 001",
          "redeemable": false,
          "NftRedeemItem": [],
          "payload": {
            "cover": [
              {
                "id": 9,
                "key": "0xc100124c1C8b863841250F77DA02b32bE799bb3F/nftFiles/50000/cover/8AD2F397176A4CFFBEC39D5F4C3A39C6.jpeg",
                "type": "cover",
                "nftId": 50000,
                "public": true,
                "altName": null,
                "preview": "https://creatorshub.s3.eu-central-1.amazonaws.com/0xc100124c1C8b863841250F77DA02b32bE799bb3F/nftFiles/50000/cover/8AD2F397176A4CFFBEC39D5F4C3A39C6.jpeg",
                "checksum": null,
                "fileName": "8AD2F397176A4CFFBEC39D5F4C3A39C6.jpeg",
                "fileType": "image/png",
                "metaData": null,
                "createdAt": "2023-03-17T08:38:14.356Z",
                "creatorId": 5,
                "publicUrl": "https://creatorshub.s3.eu-central-1.amazonaws.com/0xc100124c1C8b863841250F77DA02b32bE799bb3F/nftFiles/50000/cover/8AD2F397176A4CFFBEC39D5F4C3A39C6.jpeg",
                "updatedAt": "2023-03-17T08:38:14.355Z",
                "rootFileId": null,
                "storageType": "s3",
                "downloadable": false
              }
            ],
            "owner": "true",
            "price": "100",
            "terms": "true",
            "title": "Hacker 001",
            "status": "released",
            "currency": "eur",
            "useCaseId": 2,
            "amountType": "unique",
            "description": "",
            "licenseType": "private",
            "nftToUpgrade": null,
            "secretPhrase": "",
            "storageOption": "s3",
            "assetSameAsCover": true
          },
          "status": "released",
          "priceCurrency": "EUR",
          "priceType": "FIXED",
          "creatorId": 5,
          "creator": {
            "avatar": "https://preview-creatorshub.com/images/user-placeholder.png",
            "cover": "",
            "country": "",
            "description": "",
            "companyUser": false,
            "email": "test@gmail.com",
            "newsletterAgreement": false,
            "locale": "en",
            "ethereumPublicAddr": "0xc100124c1C8b863841250F77DA02b32bE799bb3F",
            "id": 5,
            "location": "",
            "facebookUrl": "",
            "instagramUrl": "",
            "twitterUrl": "",
            "websiteUrl": "",
            "name": "Kacper",
            "seenNotifications": null,
            "username": "Kacper Hernacki",
            "verified": false,
            "isCreator": false,
            "creatorsData": null
          },
          "NftListing": [
            {
              "id": 7,
              "active": false,
              "activeTill": null,
              "type": "regular",
              "priceCents": 14000,
              "priceCurrency": "EUR",
              "amount": 1
            },
            {
              "id": 8,
              "active": false,
              "activeTill": null,
              "type": "regular",
              "priceCents": 14000,
              "priceCurrency": "EUR",
              "amount": 1
            },
            {
              "id": 9,
              "active": false,
              "activeTill": null,
              "type": "regular",
              "priceCents": 14000,
              "priceCurrency": "EUR",
              "amount": 1
            }
          ],
          "position": 1,
          "label": "Hacker 001",
          "releaseAt": null,
          "createdAt": null,
          "deletedAt": null,
          "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0xc100124c1C8b863841250F77DA02b32bE799bb3F/nftFiles/50000/cover/8AD2F397176A4CFFBEC39D5F4C3A39C6.jpeg",
          "slug": "50000-hacker-001",
          "eventResults": [],
          "updatedAt": null,
          "createdWith": "creatorshub"
        }
      ],
      "quantity": 2
    }
  ]
}
```