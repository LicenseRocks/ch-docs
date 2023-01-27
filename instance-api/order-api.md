---
label: Orders
tags: [order, nft, purchase, read, api, token]
order: 6
authors:
- name: Adam Leszczyński
  email: adam.leszczynsky@gmail.com
  link: https://alsd.app
  avatar: https://avatars.githubusercontent.com/u/20825919
---

# Order API

Our Instance's API brings two secure, API Token protected endpoints which can:
- get the details about the Orders.
- create Orders within it, setting its status to `paid`, which will trigger the transfer of the NFT to the buyer.

In order to obtain API key go to [Obtaining the API Token](/authorization/#obtaining-the-api-token)

Both endpoints accept the `array of objects` as the body.

The endpoints' URL is: `https://{INSTANCE_URL}/api/externalOrders`

## GET method

Read the details of the specified Orders. Here is the example of `cURL` request:

```
curl --location --request GET '{INSTANCE_URL}/api/externalOrders/{IDs_seperated_by_commas}' \
--header 'authorization: {API_TOKEN}' \
--header 'Content-Type: application/json' \
--data-raw ''
```

Example of the proper URL construction:

`https://{INSTANCE_URL}/api/externalOrders/1,2,5`

Example of the proper response with `200 OK` status:

```json
{
    "orders": [
        {
            "id": 1,
            "buyerId": 24,
            "billingAddressId": 1,
            "paymentMethod": "externalPayment",
            "provider": "externalProvider",
            "providerId": null,
            "secupayStxTransactionId": null,
            "secupayPciTransactionId": null,
            "secupayWebhookToken": "a6a08c57-9fb3-4eb1-b569-c8450355cd3c",
            "totalPriceCents": 2000,
            "totalPriceCurrency": "EUR",
            "totalPriceEth": "13.422818791946",
            "status": null,
            "failReason": null,
            "feesCollectedAt": null,
            "createdAt": "2022-12-30T12:31:40.532Z",
            "updatedAt": "2022-12-30T12:31:40.562Z",
            "ProductType": "nft",
            "buyer": {
                "id": 24,
                "approved": false,
                "companyUser": false,
                "email": "adam@licenserocks.de",
                "ethereumPublicAddr": "0xBA53a45AaeaD689dD74eB7Cf338c5e9206A660f8",
                "name": null,
                "provider": "magiclink",
                "discordId": null,
                "roleId": null,
                "username": null,
                "viewMode": "buyer",
                "walletNonce": null,
                "stripeConnectId": null,
                "secupayExternalId": null,
                "simplexId": null,
                "newsletterAgreement": false,
                "locale": "en",
                "approvedAt": null,
                "createdAt": "2022-12-29T15:06:59.509Z",
                "lastAccessAt": null,
                "onboardedAt": null,
                "removedAt": null,
                "updatedAt": "2022-12-29T15:06:59.513Z",
                "ipAddress": "::ffff:127.0.0.1"
            },
            "orderItems": [
                {
                    "id": 1,
                    "orderId": 1,
                    "nftId": 1,
                    "listingId": 1,
                    "quantity": 1,
                    "priceCents": 2000,
                    "priceEths": "13.422818791946309",
                    "ethRecipient": null,
                    "priceCurrency": "EUR",
                    "txId": null,
                    "paymentProvider": null,
                    "status": null,
                    "createdAt": "2022-12-30T12:31:40.532Z",
                    "updatedAt": "2022-12-30T12:31:40.534Z",
                    "ProductType": "nft",
                    "nft": {
                        "id": 1,
                        "amount": 100,
                        "availableAmount": 100,
                        "approved": false,
                        "arweaveTx": "HaeA16eOIYAzXi2oJVK5MFfEubenIv_qnrkyK8aFiU0",
                        "chainTx": null,
                        "creatorPublicAddr": "0xfaE0be50ae6b4A2bdD5D4F8e0600fa1363722d33",
                        "contractAddr": "0x7F22bF652e54Db9E79DF9f9d7cBeea2BddBf3d1a",
                        "contractName": "AuctionableERC1155",
                        "contractNetwork": "maticTestnet",
                        "coverKey": null,
                        "category": null,
                        "secretPhrase": "Geheimbotschaft",
                        "fee": null,
                        "feeRecipient": null,
                        "payload": {
                            "audio": [
                                {
                                    "path": "file_example_MP3_700KB.mp3",
                                    "altName": null,
                                    "preview": ""
                                }
                            ],
                            "cover": [
                                {
                                    "path": "Group 1918.png",
                                    "altName": null,
                                    "preview": "blob:https://preview-creatorshub.license.rocks/d91f1138-14df-4f26-8b99-2a905e808a15"
                                }
                            ],
                            "owner": "true",
                            "terms": "true",
                            "title": "Titel NFT",
                            "amount": "100",
                            "currency": "eur",
                            "useCaseId": 15,
                            "amountType": "limited",
                            "description": "Beschreibung....",
                            "licenseType": "private",
                            "nftToUpgrade": null,
                            "secretPhrase": "Geheimbotschaft",
                            "startingPrice": "20",
                            "storageOption": "s3",
                            "biddingEnabled": true,
                            "initialSalesFees": [],
                            "bonusMediaEnabled": true,
                            "downloadableAsset": [
                                {
                                    "path": "Group 1900.png",
                                    "altName": "MP3 1.png",
                                    "preview": "blob:https://preview-creatorshub.license.rocks/d6146819-0aea-4e62-a362-5f860534454c"
                                },
                                {
                                    "path": "Group 1916.png",
                                    "altName": "Meet & Greet with dem Artist.png",
                                    "preview": "blob:https://preview-creatorshub.license.rocks/a629caef-7c31-4989-8941-d690044e80b1"
                                },
                                {
                                    "path": "Merch.png",
                                    "altName": null,
                                    "preview": "blob:https://preview-creatorshub.license.rocks/b02e87bd-83b6-4a3d-8ce1-7584b6fc797f"
                                },
                                {
                                    "path": "Group 1913.png",
                                    "altName": "Backstage Pass.png",
                                    "preview": "blob:https://preview-creatorshub.license.rocks/b4c77c20-585c-4966-8ddc-edfd64e446c6"
                                }
                            ],
                            "secondarySalesFees": [],
                            "salesContractEnabled": false
                        },
                        "price": 2000,
                        "priceEths": "13.513513513513",
                        "priceCurrency": "EUR",
                        "priceType": "FIXED",
                        "downloadable": true,
                        "title": "Titel NFT",
                        "creatorId": 1,
                        "useCaseId": 1,
                        "upgradeable": false,
                        "tokenId": null,
                        "newTokenId": null,
                        "oldTokenId": null,
                        "status": "released",
                        "releaseAt": "2022-12-28T13:24:39.865Z",
                        "biddingEnabled": true,
                        "createdAt": "2022-12-28T13:24:39.873Z",
                        "updatedAt": "2022-12-28T13:24:39.873Z",
                        "deletedAt": null,
                        "fractionalized": false,
                        "redeemable": false,
                        "qrcodePrintfileId": null,
                        "salesContractUrl": null
                    },
                    "listing": {
                        "id": 1,
                        "priceCents": 2000,
                        "amount": null,
                        "priceEths": "13.422818791946309",
                        "priceWei": "13422818791946309000",
                        "activeTill": "2023-01-04T13:24:39.865Z",
                        "active": true,
                        "type": "auction",
                        "txHash": "0xc7a061416e8a3b8b5a425a061b28062e3ea9a6b476d6359c256b4be31c3c9614",
                        "priceCurrency": "EUR",
                        "sellerId": 1,
                        "nftId": 1,
                        "captureCronId": null,
                        "createdAt": "2022-12-28T13:24:39.874Z",
                        "updatedAt": "2022-12-28T13:24:39.875Z"
                    }
                }
            ]
        },
        {
            "id": 2,
            "buyerId": 24,
            "billingAddressId": 1,
            "paymentMethod": "externalPayment",
            "provider": "externalProvider",
            "providerId": null,
            "secupayStxTransactionId": null,
            "secupayPciTransactionId": null,
            "secupayWebhookToken": "0bfbc1ba-07fd-463e-b9e9-63850b25447f",
            "totalPriceCents": 2000,
            "totalPriceCurrency": "EUR",
            "totalPriceEth": "13.422818791946",
            "status": null,
            "failReason": null,
            "feesCollectedAt": null,
            "createdAt": "2022-12-30T12:31:40.687Z",
            "updatedAt": "2022-12-30T12:31:40.703Z",
            "ProductType": "nft",
            "buyer": {
                "id": 24,
                "approved": false,
                "companyUser": false,
                "email": "adam@licenserocks.de",
                "ethereumPublicAddr": "0xBA53a45AaeaD689dD74eB7Cf338c5e9206A660f8",
                "name": null,
                "provider": "magiclink",
                "discordId": null,
                "roleId": null,
                "username": null,
                "viewMode": "buyer",
                "walletNonce": null,
                "stripeConnectId": null,
                "secupayExternalId": null,
                "simplexId": null,
                "newsletterAgreement": false,
                "locale": "en",
                "approvedAt": null,
                "createdAt": "2022-12-29T15:06:59.509Z",
                "lastAccessAt": null,
                "onboardedAt": null,
                "removedAt": null,
                "updatedAt": "2022-12-29T15:06:59.513Z",
                "ipAddress": "::ffff:127.0.0.1"
            },
            "orderItems": [
                {
                    "id": 2,
                    "orderId": 2,
                    "nftId": 1,
                    "listingId": 1,
                    "quantity": 1,
                    "priceCents": 2000,
                    "priceEths": "13.422818791946309",
                    "ethRecipient": null,
                    "priceCurrency": "EUR",
                    "txId": null,
                    "paymentProvider": null,
                    "status": null,
                    "createdAt": "2022-12-30T12:31:40.687Z",
                    "updatedAt": "2022-12-30T12:31:40.688Z",
                    "ProductType": "nft",
                    "nft": {
                        "id": 1,
                        "amount": 100,
                        "availableAmount": 100,
                        "approved": false,
                        "arweaveTx": "HaeA16eOIYAzXi2oJVK5MFfEubenIv_qnrkyK8aFiU0",
                        "chainTx": null,
                        "creatorPublicAddr": "0xfaE0be50ae6b4A2bdD5D4F8e0600fa1363722d33",
                        "contractAddr": "0x7F22bF652e54Db9E79DF9f9d7cBeea2BddBf3d1a",
                        "contractName": "AuctionableERC1155",
                        "contractNetwork": "maticTestnet",
                        "coverKey": null,
                        "category": null,
                        "secretPhrase": "Geheimbotschaft",
                        "fee": null,
                        "feeRecipient": null,
                        "payload": {
                            "audio": [
                                {
                                    "path": "file_example_MP3_700KB.mp3",
                                    "altName": null,
                                    "preview": ""
                                }
                            ],
                            "cover": [
                                {
                                    "path": "Group 1918.png",
                                    "altName": null,
                                    "preview": "blob:https://preview-creatorshub.license.rocks/d91f1138-14df-4f26-8b99-2a905e808a15"
                                }
                            ],
                            "owner": "true",
                            "terms": "true",
                            "title": "Titel NFT",
                            "amount": "100",
                            "currency": "eur",
                            "useCaseId": 15,
                            "amountType": "limited",
                            "description": "Beschreibung....",
                            "licenseType": "private",
                            "nftToUpgrade": null,
                            "secretPhrase": "Geheimbotschaft",
                            "startingPrice": "20",
                            "storageOption": "s3",
                            "biddingEnabled": true,
                            "initialSalesFees": [],
                            "bonusMediaEnabled": true,
                            "downloadableAsset": [
                                {
                                    "path": "Group 1900.png",
                                    "altName": "MP3 1.png",
                                    "preview": "blob:https://preview-creatorshub.license.rocks/d6146819-0aea-4e62-a362-5f860534454c"
                                },
                                {
                                    "path": "Group 1916.png",
                                    "altName": "Meet & Greet with dem Artist.png",
                                    "preview": "blob:https://preview-creatorshub.license.rocks/a629caef-7c31-4989-8941-d690044e80b1"
                                },
                                {
                                    "path": "Merch.png",
                                    "altName": null,
                                    "preview": "blob:https://preview-creatorshub.license.rocks/b02e87bd-83b6-4a3d-8ce1-7584b6fc797f"
                                },
                                {
                                    "path": "Group 1913.png",
                                    "altName": "Backstage Pass.png",
                                    "preview": "blob:https://preview-creatorshub.license.rocks/b4c77c20-585c-4966-8ddc-edfd64e446c6"
                                }
                            ],
                            "secondarySalesFees": [],
                            "salesContractEnabled": false
                        },
                        "price": 2000,
                        "priceEths": "13.513513513513",
                        "priceCurrency": "EUR",
                        "priceType": "FIXED",
                        "downloadable": true,
                        "title": "Titel NFT",
                        "creatorId": 1,
                        "useCaseId": 1,
                        "upgradeable": false,
                        "tokenId": null,
                        "newTokenId": null,
                        "oldTokenId": null,
                        "status": "released",
                        "releaseAt": "2022-12-28T13:24:39.865Z",
                        "biddingEnabled": true,
                        "createdAt": "2022-12-28T13:24:39.873Z",
                        "updatedAt": "2022-12-28T13:24:39.873Z",
                        "deletedAt": null,
                        "fractionalized": false,
                        "redeemable": false,
                        "qrcodePrintfileId": null,
                        "salesContractUrl": null
                    },
                    "listing": {
                        "id": 1,
                        "priceCents": 2000,
                        "amount": null,
                        "priceEths": "13.422818791946309",
                        "priceWei": "13422818791946309000",
                        "activeTill": "2023-01-04T13:24:39.865Z",
                        "active": true,
                        "type": "auction",
                        "txHash": "0xc7a061416e8a3b8b5a425a061b28062e3ea9a6b476d6359c256b4be31c3c9614",
                        "priceCurrency": "EUR",
                        "sellerId": 1,
                        "nftId": 1,
                        "captureCronId": null,
                        "createdAt": "2022-12-28T13:24:39.874Z",
                        "updatedAt": "2022-12-28T13:24:39.875Z"
                    }
                }
            ]
        }
    ],
    "error": null
}
```

## Properties in `GET` request
- `orderId` — Type `string`. IDs of the Orders in our Instance, **seperated by commas**. Each ID has to be a number. Working example: `1,2,5`. Bad example: `1,2,a` (because "a" is not a number).

You can also request only one order, like in this case:

`https://{INSTANCE_URL}/api/externalOrders/1`

If **any** of the provided IDs will *not* be a number, like here:

`https://{INSTANCE_URL}/api/externalOrders/a,2`

you will see `400 BAD REQUEST` response:

```json
{
    "orders": null,
    "error": "One or more IDs are not a number type. One of the example is 'a'. Check the URL."
}
```


If **any** of the provided IDs will be missing in our app, you will see `400 BAD REQUEST` response pointing to that ID, like this:

```json
{
    "orders": null,
    "error": "Order with ID {orderId} does not exist."
}
```

## POST method

Create Orders. Here is the example `cURL` request:

```
curl --location --request POST 'https://{INSTANCE_URL}/api/externalOrders' \
--header 'authorization: {API_TOKEN}' \
--header 'Content-Type: application/json' \
--data-raw '[
    {
        "nftId": 405,
        "listingId": 2,
        "quantity": 3,
        "buyerUserId": 50000,
        "buyerBillingData": {  
            "city": "Toruń",
            "country": "Poland",
            "postal": "87-100",
            "street": "Szeroka"
        }
    },
    {
        "nftId": 406,
        "listingId": 4,
        "quantity": 3,
        "buyerUserId": 5,
        "buyerBillingData": {  
            "city": "Toruń",
            "country": "Poland",
            "postal": "87-100",
            "street": "Szeroka"
        }
    }
]'
```

Example of the proper response with `200 OK` status:

```json
{
    "orders": [
        {
            "id": 42,
            "buyerId": 5,
            "billingAddressId": 51,
            "paymentMethod": "externalPayment",
            "provider": "externalProvider",
            "providerId": null,
            "secupayStxTransactionId": null,
            "secupayPciTransactionId": null,
            "secupayWebhookToken": "bba43d13-2d9c-408a-b610-407ecfba5864",
            "totalPriceCents": 100,
            "totalPriceCurrency": "EUR",
            "totalPriceEth": "1.1661372403595",
            "status": null,
            "failReason": null,
            "feesCollectedAt": null,
            "createdAt": "2022-12-21T12:07:45.557Z",
            "updatedAt": "2022-12-21T12:07:45.558Z",
            "ProductType": "nft",
            "orderItems": [
                {
                    "id": 42,
                    "orderId": 42,
                    "nftId": 405,
                    "listingId": 2,
                    "quantity": 1,
                    "priceCents": 100,
                    "priceEths": "1.1661372403595436",
                    "ethRecipient": null,
                    "priceCurrency": "EUR",
                    "txId": null,
                    "paymentProvider": null,
                    "status": null,
                    "createdAt": "2022-12-21T12:07:45.557Z",
                    "updatedAt": "2022-12-21T12:07:45.558Z",
                    "ProductType": "nft",
                    "nft": {
                        "id": 405,
                        "amount": 10000,
                        "availableAmount": 9989,
                        "approved": false,
                        "arweaveTx": "K9nLDK_2IluzmYphg_k1PZZI101vdQ_Q4lLjn03xVcM",
                        "chainTx": null,
                        "creatorPublicAddr": "0xb9449446c82b2f2a184d3bad2c0fafc5f21eeb73",
                        "contractAddr": "0xB362f5b77146c1E8C8c76C501ecA9EB4a7C7769D",
                        "contractName": "AUCTIONABLE_ERC1155",
                        "contractNetwork": "maticTestnet",
                        "coverKey": null,
                        "category": null,
                        "secretPhrase": null,
                        "fee": null,
                        "feeRecipient": null,
                        "payload": {
                            "cover": [
                                {
                                    "id": 9,
                                    "key": "0xb9449446c82b2f2a184d3bad2c0fafc5f21eeb73/nftFiles/405/cover/ancientaliensmeme.jpg",
                                    "type": "cover",
                                    "nftId": 405,
                                    "public": true,
                                    "altName": null,
                                    "preview": "https://creatorshub.s3.eu-central-1.amazonaws.com/0xb9449446c82b2f2a184d3bad2c0fafc5f21eeb73/nftFiles/405/cover/ancientaliensmeme.jpg",
                                    "checksum": null,
                                    "fileName": "ancientaliensmeme.jpg",
                                    "fileType": "image/png",
                                    "metaData": null,
                                    "createdAt": "2022-12-08T13:19:42.923Z",
                                    "creatorId": 4,
                                    "publicUrl": "https://creatorshub.s3.eu-central-1.amazonaws.com/0xb9449446c82b2f2a184d3bad2c0fafc5f21eeb73/nftFiles/405/cover/ancientaliensmeme.jpg",
                                    "updatedAt": "2022-12-08T13:19:42.922Z",
                                    "rootFileId": null,
                                    "storageType": "s3",
                                    "downloadable": false
                                }
                            ],
                            "owner": "true",
                            "price": "21",
                            "terms": "true",
                            "title": "Meme",
                            "amount": "10000",
                            "status": "released",
                            "currency": "eur",
                            "useCaseId": 2,
                            "amountType": "limited",
                            "description": "",
                            "licenseType": "private",
                            "nftToUpgrade": null,
                            "secretPhrase": "",
                            "storageOption": "s3",
                            "assetSameAsCover": true
                        },
                        "price": 2100,
                        "priceEths": "24.479033707629",
                        "priceCurrency": "EUR",
                        "priceType": "FIXED",
                        "downloadable": false,
                        "title": "Meme",
                        "creatorId": 4,
                        "useCaseId": 2,
                        "upgradeable": false,
                        "tokenId": null,
                        "newTokenId": null,
                        "oldTokenId": null,
                        "status": "released",
                        "releaseAt": "2022-12-08T13:19:41.332Z",
                        "biddingEnabled": false,
                        "createdAt": "2022-12-08T13:19:41.332Z",
                        "updatedAt": "2022-12-20T16:48:01.798Z",
                        "deletedAt": null,
                        "fractionalized": false,
                        "redeemable": false,
                        "qrcodePrintfileId": null,
                        "salesContractUrl": null
                    },
                    "listing": {
                        "id": 2,
                        "priceCents": 100,
                        "amount": 9989,
                        "priceEths": "1.1661372403595436",
                        "priceWei": "1166137240359543600",
                        "activeTill": null,
                        "active": true,
                        "type": "regular",
                        "txHash": "0xf2067078df17fbb6f948bf9c7dc06ce71eb67452cf2670bd068df4080d9d897c",
                        "priceCurrency": "EUR",
                        "sellerId": 4,
                        "nftId": 405,
                        "captureCronId": null,
                        "createdAt": "2022-12-08T13:33:08.541Z",
                        "updatedAt": "2022-12-20T16:48:01.771Z"
                    }
                }
            ]
        },
        {
            "id": 43,
            "buyerId": 5,
            "billingAddressId": 52,
            "paymentMethod": "externalPayment",
            "provider": "externalProvider",
            "providerId": null,
            "secupayStxTransactionId": null,
            "secupayPciTransactionId": null,
            "secupayWebhookToken": "93bb6da4-cb79-44f4-a9d2-391bc2c9fe21",
            "totalPriceCents": 1200,
            "totalPriceCurrency": "EUR",
            "totalPriceEth": "13.651116149384",
            "status": null,
            "failReason": null,
            "feesCollectedAt": null,
            "createdAt": "2022-12-21T12:07:45.584Z",
            "updatedAt": "2022-12-21T12:07:45.584Z",
            "ProductType": "nft",
            "orderItems": [
                {
                    "id": 43,
                    "orderId": 43,
                    "nftId": 406,
                    "listingId": 4,
                    "quantity": 1,
                    "priceCents": 1200,
                    "priceEths": "13.651116149384164",
                    "ethRecipient": null,
                    "priceCurrency": "EUR",
                    "txId": null,
                    "paymentProvider": null,
                    "status": null,
                    "createdAt": "2022-12-21T12:07:45.584Z",
                    "updatedAt": "2022-12-21T12:07:45.584Z",
                    "ProductType": "nft",
                    "nft": {
                        "id": 406,
                        "amount": 1,
                        "availableAmount": 1,
                        "approved": false,
                        "arweaveTx": "ZRnQwRRP3uvFLJ3DD6vlfv_RSAWszdh21M1BFoRRnzg",
                        "chainTx": null,
                        "creatorPublicAddr": "0x0173f9004cde92ca8f2a53c51072b74f42dd1958",
                        "contractAddr": "0xB362f5b77146c1E8C8c76C501ecA9EB4a7C7769D",
                        "contractName": "AUCTIONABLE_ERC1155",
                        "contractNetwork": "maticTestnet",
                        "coverKey": null,
                        "category": null,
                        "secretPhrase": null,
                        "fee": null,
                        "feeRecipient": null,
                        "payload": {
                            "cover": [
                                {
                                    "id": 11,
                                    "key": "0x0173f9004cde92ca8f2a53c51072b74f42dd1958/nftFiles/406/cover/901598356831371335.png",
                                    "type": "cover",
                                    "nftId": 406,
                                    "public": true,
                                    "altName": null,
                                    "preview": "https://creatorshub.s3.eu-central-1.amazonaws.com/0x0173f9004cde92ca8f2a53c51072b74f42dd1958/nftFiles/406/cover/901598356831371335.png",
                                    "checksum": null,
                                    "fileName": "901598356831371335.png",
                                    "fileType": "image/png",
                                    "metaData": null,
                                    "createdAt": "2022-12-09T11:22:18.997Z",
                                    "creatorId": 5,
                                    "publicUrl": "https://creatorshub.s3.eu-central-1.amazonaws.com/0x0173f9004cde92ca8f2a53c51072b74f42dd1958/nftFiles/406/cover/901598356831371335.png",
                                    "updatedAt": "2022-12-09T11:22:18.996Z",
                                    "rootFileId": null,
                                    "storageType": "s3",
                                    "downloadable": false
                                }
                            ],
                            "owner": "true",
                            "price": "12",
                            "terms": "true",
                            "title": "WOMM",
                            "status": "released",
                            "currency": "eur",
                            "useCaseId": 11,
                            "amountType": "unique",
                            "redeemType": "physical",
                            "description": "",
                            "licenseType": "private",
                            "nftToUpgrade": null,
                            "secretPhrase": "",
                            "storageOption": "s3",
                            "fractionsAmount": "100000",
                            "assetSameAsCover": true,
                            "redeemItemsAmount": 1,
                            "fractionableEnabled": true,
                            "redeemValidationDate": null
                        },
                        "price": 1200,
                        "priceEths": "13.701836617016",
                        "priceCurrency": "EUR",
                        "priceType": "FIXED",
                        "downloadable": false,
                        "title": "WOMM",
                        "creatorId": 5,
                        "useCaseId": 11,
                        "upgradeable": false,
                        "tokenId": null,
                        "newTokenId": null,
                        "oldTokenId": null,
                        "status": "released",
                        "releaseAt": "2022-12-09T11:22:17.543Z",
                        "biddingEnabled": false,
                        "createdAt": "2022-12-09T11:22:17.543Z",
                        "updatedAt": "2022-12-09T12:55:09.001Z",
                        "deletedAt": null,
                        "fractionalized": true,
                        "redeemable": false,
                        "qrcodePrintfileId": null,
                        "salesContractUrl": null
                    },
                    "listing": {
                        "id": 4,
                        "priceCents": 1200,
                        "amount": 1,
                        "priceEths": "13.651116149384164",
                        "priceWei": "13651116149384164000",
                        "activeTill": null,
                        "active": true,
                        "type": "regular",
                        "txHash": null,
                        "priceCurrency": "EUR",
                        "sellerId": 5,
                        "nftId": 406,
                        "captureCronId": null,
                        "createdAt": "2022-12-09T12:55:08.986Z",
                        "updatedAt": "2022-12-09T12:55:08.986Z"
                    }
                }
            ]
        }
    ],
    "error": null
}
```

## Properties in `POST` request

- `nftId` — Type `number`. ID of the NFT in our Instance. Lack of the property will throw `400 Bad Request`,
- `listingId` — Type `number`. ID of the NFT Listing (sale) in our Instance. Lack of the property will throw `400 Bad Request`,
- `buyerUserId` — Type `number`. ID of the User registered on our platform. Lack of the property or lack of the User with passed ID in our system will throw `400 Bad Request` with proper error message,
- `quantity` — Type `number`. Amount of the purchased product. Lack of the property will throw `400 Bad Request`,
- `buyerBillingData` — Type `object`. It contains 4 properties listed below. It's not required.
  - `city` — Type `string`. It's not required.
  - `country` — Type `string`. It's not required.
  - `postal` — Type `string`. It's not required.
  - `street` — Type `string`. It's not required.

## Billing Address behaviour

There are 2 options: 
- all `buyerBillingData` object properties are passed (`city, country, postal, street`) - we are using this data to create new Billing Address attached to the User with ID you passed in `buyerUserId`,
- 1 or more above-mentioned properties are missing - we are trying to get the first Billing Address for the user with the given `buyerUserId` and use that data instead of the properties you passed. If we don't fint matching Billing Address it will throw `400 Bad Request` error with proper message.