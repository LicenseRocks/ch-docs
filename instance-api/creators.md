---
label: Fetching creators
tags: [manage, creators]
order: 6
authors:
- name: Kacper Hernacki
  email: kacper@licenserocks.de
  avatar: ../static/kacper.jpeg
  link: https://twitter.com/KacperHernacki
---
# Fetching creators

When it comes to displaying creators on the frontend, you can use the following endpoint to fetch all creators.
```
GET https://{INSTANCE_URL}/api/public/creators
```

```
curl --location --request GET '{INSTANCE_URL}/api/public/creators' 
```

Response

```json Response (application/json)
{
  "creators": [
    {
      "creator": {
        "userId": 5,
        "payload": {
          "name": "John Test",
          "files": [
            {
              "path": "6FC85761-ED3A-47B2-8139-E408AAAF76EC.jpeg",
              "altName": null,
              "preview": "blob:http://localhost:3002/c6641f0f-35eb-414e-ab4f-3a1b7c87c72a"
            }
          ],
          "hello": "Test",
          "skills": [
            {
              "skill": {
                "id": 18,
                "label": "Digital Painting",
                "value": "digitalPaiting"
              }
            }
          ],
          "country": {
            "label": "Poland",
            "value": "PL"
          },
          "showNfts": true,
          "showFiles": true,
          "discordUrl": "testy",
          "showSkills": true,
          "singleNfts": [
            {
              "id": 50004,
              "title": "Meme",
              "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3/nftFiles/50004/cover/A7A753CB61854A94B14BF0686D603243_1_201_a.jpeg"
            },
            {
              "id": 50003,
              "title": "Ledger",
              "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3/nftFiles/50003/cover/1D3106E283944252AB676D56B96ADF5D_1_201_a.jpeg"
            },
            {
              "id": 50002,
              "title": "monkeys",
              "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3/nftFiles/50002/cover/1C64DC3BA370453F955BFCBBF6808EB0_1_201_a.jpeg"
            }
          ],
          "twitterUrl": "kacpi",
          "websiteUrl": "https://www.random.com",
          "companyName": "Testover",
          "facebookUrl": "kacpi",
          "instagramUrl": "kacpi",
          "descriptionDE": "<p>type a description to your profilekacpi</p>",
          "showCollections": true,
          "openForCocreation": true,
          "singleCollections": [
            {
              "id": 1,
              "title": "test",
              "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0xc100124c1C8b863841250F77DA02b32bE799bb3F/nftFiles/50000/cover/8AD2F397176A4CFFBEC39D5F4C3A39C6.jpeg"
            }
          ],
          "showCocreateWithMe": true,
          "cocreationAvailablility": {
            "id": 0,
            "label": "always open for co-creations",
            "value": "always"
          }
        },
        "discordUrl": "John Test",
        "twitterUrl": "John Test",
        "websiteUrl": "https://www.random.com",
        "facebookUrl": "John Test",
        "instagramUrl": "John Test",
        "name": "John Test",
        "position": null
      },
      "avatarUrl": "https://creatorshub.s3.eu-central-1.amazonaws.com/images/user-placeholder.png"
    }
  ]
}
```

## Get creator by Id

```
GET https://{INSTANCE_URL}/api/public/creators/${creatorId}
```


Use below endpoint in order to fetch collection by Id.


Response

```json Response (application/json)
{
  "creator": {
    "name": "John Test",
    "files": [],
    "hello": "John Test",
    "skills": [
      {
        "skill": {
          "id": 18,
          "label": "Digital Painting",
          "value": "digitalPaiting"
        }
      }
    ],
    "country": {
      "label": "Poland",
      "value": "PL"
    },
    "showNfts": true,
    "showFiles": true,
    "discordUrl": "John Test",
    "showSkills": true,
    "singleNfts": [
      {
        "id": 50004,
        "title": "Meme",
        "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3/nftFiles/50004/cover/A7A753CB61854A94B14BF0686D603243_1_201_a.jpeg"
      },
      {
        "id": 50003,
        "title": "Ledger",
        "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3/nftFiles/50003/cover/1D3106E283944252AB676D56B96ADF5D_1_201_a.jpeg"
      },
      {
        "id": 50002,
        "title": "monkeys",
        "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3/nftFiles/50002/cover/1C64DC3BA370453F955BFCBBF6808EB0_1_201_a.jpeg"
      }
    ],
    "twitterUrl": "kacpi",
    "websiteUrl": "https://www.random.com",
    "companyName": "John Test",
    "facebookUrl": "kacpi",
    "instagramUrl": "kacpi",
    "descriptionDE": "<p>type a description to your profilekacpi</p>",
    "showCollections": true,
    "openForCocreation": true,
    "singleCollections": [
      {
        "id": 1,
        "title": "John Test",
        "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0xc100124c1C8b863841250F77DA02b32bE799bb3F/nftFiles/50000/cover/8AD2F397176A4CFFBEC39D5F4C3A39C6.jpeg"
      }
    ],
    "showCocreateWithMe": true,
    "cocreationAvailablility": {
      "id": 0,
      "label": "always open for co-creations",
      "value": "always"
    },
    "walletAddr": "0xc100124c1C8b863841250F77DA02b32bE799bb3F",
    "userId": 5,
    "description": null,
    "likes": [],
    "isCreator": true,
    "allCreatorsIds": [
      5
    ],
    "avatar": "https://preview-creatorshub/images/user-placeholder.png"
  },
  "nfts": [
    {
      "amount": 1,
      "status": "released",
      "availableAmount": 0,
      "arweaveTx": "ugYz8liCU3c7TzKUxsC7-jfTV529EXKAxOFBZSOwAME",
      "biddingEnabled": false,
      "chainTx": null,
      "creator": {
        "companyUser": false,
        "email": "meta@maeta.com",
        "id": 6,
        "name": "TestMeta",
        "ethereumPublicAddr": "0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3",
        "profile": {
          "description": null,
          "isCreator": null
        },
        "SocialVerification": [],
        "username": "TestMeta"
      },
      "id": 50002,
      "price": 10000,
      "priceCurrency": "EUR",
      "title": "monkeys",
      "downloadable": false,
      "payload": {
        "cover": [
          {
            "altName": null,
            "preview": "https://preview-creatorshub/977031d7-152a-49ec-9091-f3d5dde77c80"
          }
        ],
        "owner": "true",
        "price": "100",
        "terms": "true",
        "title": "monkeys",
        "status": "released",
        "currency": "eur",
        "arweaveTx": "ugYz8liCU3c7TzKUxsC7-jfTV529EXKAxOFBZSOwAME",
        "useCaseId": 2,
        "amountType": "unique",
        "description": "",
        "licenseType": "private",
        "downloadable": false,
        "nftToUpgrade": null,
        "secretPhrase": "",
        "storageOption": "s3",
        "assetSameAsCover": true
      },
      "priceType": "FIXED",
      "Files": [
        {
          "key": "0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3/nftFiles/50002/cover/1C64DC3BA370453F955BFCBBF6808EB0_1_201_a.jpeg",
          "public": true,
          "storageType": "s3",
          "type": "cover"
        },
        {
          "public": true,
          "type": "salesContract",
          "fileName": "Sales contract",
          "url": "/api/contracts",
          "createdAt": null
        }
      ],
      "NftListing": [],
      "bids": [],
      "label": "monkeys",
      "releaseAt": null,
      "createdAt": null,
      "deletedAt": null,
      "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3/nftFiles/50002/cover/1C64DC3BA370453F955BFCBBF6808EB0_1_201_a.jpeg",
      "slug": "50002-monkeys",
      "eventResults": [],
      "files": [
        {
          "key": "0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3/nftFiles/50002/cover/1C64DC3BA370453F955BFCBBF6808EB0_1_201_a.jpeg",
          "public": true,
          "storageType": "s3",
          "type": "cover"
        },
        {
          "public": true,
          "type": "salesContract",
          "fileName": "Sales contract",
          "url": "/api/contracts",
          "createdAt": null
        }
      ],
      "NftRedeemItem": null,
      "updatedAt": null,
      "createdWith": "creatorshub",
      "NftOwner": [],
      "NftFraction": null,
      "isQuickBuyAvailable": false,
      "type": "unique"
    },
    {
      "amount": 1,
      "status": "released",
      "availableAmount": 0,
      "arweaveTx": "MgFUCVmPfD1vhZSB-8NMAmynj2S78abZAdjqiOgE3dQ",
      "biddingEnabled": false,
      "chainTx": null,
      "creator": {
        "companyUser": false,
        "email": "meta@maeta.com",
        "id": 6,
        "name": "Testy",
        "ethereumPublicAddr": "0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3",
        "profile": {
          "description": null,
          "isCreator": null
        },
        "SocialVerification": [],
        "username": "test"
      },
      "id": 50003,
      "price": 10000,
      "priceCurrency": "EUR",
      "title": "Ledger",
      "downloadable": false,
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
            "preview": "https://creatorshub.s3.eu-central-1.amazonaws.com/cd43b1b0-0d93-4732-ad03-48c74667ad45"
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
      "priceType": "FIXED",
      "Files": [
        {
          "key": "0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3/nftFiles/50003/cover/1D3106E283944252AB676D56B96ADF5D_1_201_a.jpeg",
          "public": true,
          "storageType": "s3",
          "type": "cover"
        },
        {
          "public": true,
          "type": "salesContract",
          "fileName": "Sales contract",
          "url": "/api/contracts",
          "createdAt": null
        }
      ],
      "NftListing": [],
      "bids": [],
      "label": "Ledger",
      "releaseAt": null,
      "createdAt": null,
      "deletedAt": null,
      "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3/nftFiles/50003/cover/1D3106E283944252AB676D56B96ADF5D_1_201_a.jpeg",
      "slug": "50003-ledger",
      "eventResults": [],
      "files": [
        {
          "key": "0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3/nftFiles/50003/cover/1D3106E283944252AB676D56B96ADF5D_1_201_a.jpeg",
          "public": true,
          "storageType": "s3",
          "type": "cover"
        },
        {
          "public": true,
          "type": "salesContract",
          "fileName": "Sales contract",
          "url": "/api/contracts",
          "createdAt": null
        }
      ],
      "NftRedeemItem": null,
      "updatedAt": null,
      "createdWith": "creatorshub",
      "NftOwner": [],
      "NftFraction": null,
      "isQuickBuyAvailable": false,
      "type": "unique"
    },
    {
      "amount": 1000,
      "status": "released",
      "availableAmount": 1000,
      "arweaveTx": "GLrShdQW6wYHB-EmO7lG-AR3mK3JzZp6viIz_6ekZ1k",
      "biddingEnabled": false,
      "chainTx": null,
      "creator": {
        "companyUser": false,
        "email": "meta@maeta.com",
        "id": 6,
        "name": "TestMeta",
        "ethereumPublicAddr": "0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3",
        "profile": {
          "description": null,
          "isCreator": null
        },
        "SocialVerification": [],
        "username": "TestMeta"
      },
      "id": 50004,
      "price": 10000,
      "priceCurrency": "EUR",
      "title": "Meme",
      "downloadable": false,
      "payload": {
        "cover": [
          {
            "altName": null,
            "preview": "https://creatorshub.s3.eu-central-1.amazonaws.com/9f0f66a1-167a-4a6d-bb31-0e7e1f9014d0"
          }
        ],
        "owner": "true",
        "price": "100",
        "terms": "true",
        "title": "Meme",
        "video": [
          {
            "path": "1 - intro.mp4",
            "altName": null,
            "preview": "https://creatorshub.s3.eu-central-1.amazonaws.com/a645a8de-bc4b-43be-a649-8dcf6051f08d"
          }
        ],
        "status": "released",
        "currency": "eur",
        "arweaveTx": "GLrShdQW6wYHB-EmO7lG-AR3mK3JzZp6viIz_6ekZ1k",
        "useCaseId": 7,
        "amountType": "unique",
        "description": "",
        "licenseType": "private",
        "downloadable": false,
        "nftToUpgrade": null,
        "secretPhrase": "",
        "storageOption": "s3"
      },
      "priceType": "FIXED",
      "Files": [
        {
          "key": "0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3/nftFiles/50004/cover/A7A753CB61854A94B14BF0686D603243_1_201_a.jpeg",
          "public": true,
          "storageType": "s3",
          "type": "cover"
        },
        {
          "public": true,
          "type": "salesContract",
          "fileName": "Sales contract",
          "url": "/api/contracts",
          "createdAt": null
        }
      ],
      "NftListing": [
        {
          "id": 5,
          "active": false,
          "activeTill": null,
          "type": "regular",
          "priceCents": 10000,
          "priceCurrency": "EUR",
          "amount": 1
        },
        {
          "id": 4,
          "active": false,
          "activeTill": null,
          "type": "regular",
          "priceCents": 10000,
          "priceCurrency": "EUR",
          "amount": 1
        },
        {
          "id": 10,
          "active": true,
          "activeTill": null,
          "type": "regular",
          "priceCents": 20000,
          "priceCurrency": "EUR",
          "amount": 200
        }
      ],
      "bids": [],
      "label": "Meme",
      "releaseAt": null,
      "createdAt": null,
      "deletedAt": null,
      "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3/nftFiles/50004/cover/A7A753CB61854A94B14BF0686D603243_1_201_a.jpeg",
      "slug": "50004-meme",
      "eventResults": [],
      "files": [
        {
          "key": "0x2008a908ac1fd8742ca179a06f2ef7cb59d0f4e3/nftFiles/50004/cover/A7A753CB61854A94B14BF0686D603243_1_201_a.jpeg",
          "public": true,
          "storageType": "s3",
          "type": "cover"
        },
        {
          "public": true,
          "type": "salesContract",
          "fileName": "Sales contract",
          "url": "/api/contracts",
          "createdAt": null
        }
      ],
      "NftRedeemItem": null,
      "updatedAt": null,
      "createdWith": "creatorshub",
      "NftOwner": [],
      "NftFraction": null,
      "isQuickBuyAvailable": true,
      "type": "edition"
    }
  ],
  "collections": [
    {
      "id": 1,
      "isPublic": true,
      "name": "Kacper Meta ",
      "footer": "mb",
      "createdAt": "2023-05-11T10:35:47.569Z",
      "updatedAt": "2023-05-11T10:35:47.587Z",
      "userId": 5,
      "user": {
        "avatar": "https://creatorshub.s3.eu-central-1.amazonaws.com/images/user-placeholder.png",
        "cover": "",
        "country": "",
        "description": "",
        "companyUser": false,
        "email": "hernackikacper@gmail.com",
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
        "username": "Kacper Hernacki",
        "verified": false,
        "isCreator": false,
        "creatorsData": null
      },
      "slug": "1-kacper-meta",
      "projects": [],
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
                "preview": "https://creatorshub.s3.eu-central-1.amazonaws.com/cd43b1b0-0d93-4732-ad03-48c74667ad45"
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
            "avatar": "https://creatorshub.s3.eu-central-1.amazonaws.com/images/user-placeholder.png",
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
            "avatar": "http://localhost:3000/images/user-placeholder.png",
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