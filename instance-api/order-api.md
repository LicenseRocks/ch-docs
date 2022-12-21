---
label: Create Order and transfer NFT
tags: [order, nft, purchase, api, token]
order: 6
authors:
- name: Adam Leszczyński
  email: adam.leszczynsky@gmail.com
  link: https://alsd.app
  avatar: https://avatars.githubusercontent.com/u/20825919
---

# Order API

Created: December 21, 2022 12:22 PM
Last Edited Time: December 21, 2022 12:26 PM

Our Instance's API brings the secure, API Token protected endpoint that makes it easy to create Orders within it, setting its status to `paid`, which will trigger the transfer of the NFT to the buyer.

In order to obtain API key go to [Obtaining the API Token](/authorization/#obtaining-the-api-token)


## Examples

The endpoint accepts the `array of objects` as the body. 

Here is the example `cURL` request:

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

## Properties

Let's discuss properties in request's body:

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