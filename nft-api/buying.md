---
label: Buying
tags: [manage, nft]
order: 7
authors:
- name: Kacper Hernacki
  email: kacper@licenserocks.de
  avatar: ../static/kacper.jpeg
  link: https://twitter.com/KacperHernacki
---
# Buying NFTs

In this section you will learn how to use our endpoints for buying tokens on your platform.

## Creating Order

Use below endpoint in order to create new order for an NFT.

```
POST https://{INSTANCE_URL}/api/public/order
```

!!!warning
this request must contain Authorization header with your token
!!!

```json Payload (application/json)
{
  "paymentMethod": "creditCard",
  "billingAddressId": 1,
  "items": [
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
      "Files": [
        {}
      ],
      "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0xca5ab7a0f61b1b14174cfb96b1d4178e7350ba80/nftFiles/1/cover/sample-image.jpg",
      "slug": "1-sample-nft"
    }
  ],
  "shippingAddressId":1,
  "listingId": 1
}
```
Response
```json Response
{
  "id": 139,
  "buyerId": 5,
  "billingAddressId": 20,
  "paymentMethod": 'creditCard',
  "provider": null,
  "providerId": null,
  "checkoutUrl": null,
  "secupayStxTransactionId": null,
  "secupayPciTransactionId": null,
  "secupayWebhookToken": '6441f72c-dc4f-4043-af27-5d1ca35fcda3',
  "totalPriceCents": 10000,
  "totalPriceCurrentotalPriceEth": '136.02333072168',
  "status": 'initialized',
  "failReason": null,
  "feesCollectedAt": null,
  "createdAt": 2023-06-13T17:11:06.183Z,
  "updatedAt": 2023-06-13T17:11:06.184Z,
  "ProductType": 'nft',
  "organizationId": null,
  "orderItems": [
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
      "Files": [
        {}
      ],
      "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0xca5ab7a0f61b1b14174cfb96b1d4178e7350ba80/nftFiles/1/cover/sample-image.jpg",
      "slug": "1-sample-nft"
    }
  ]
}
```

It is possible to use also paymentMethods, like "secupay" and "wert"

## Checkout Response

Checkout response can be made in different forms. For "secupay",
use below endpoint to restore a checkout url.

```
POST https://{INSTANCE_URL}/api/public/order/${orderId}/secupay
```
```json Payload (application/json)
{
  "cartItems": [
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
      "Files": [
        {}
      ],
      "coverSrc": "https://creatorshub.s3.eu-central-1.amazonaws.com/0xca5ab7a0f61b1b14174cfb96b1d4178e7350ba80/nftFiles/1/cover/sample-image.jpg",
      "slug": "1-sample-nft"
    }
  ],
  "paymentMethod": "secupay",
  "successUrl": "{YOUR_INSTANCE_URL}/myOrders",
  "cancelUrl": "{YOUR_INSTANCE_URL}/myOrders"
}
```

Response

```json Response
{
  "checkoutUrl": "secupay checkout url"
}
```

To get checkout URL for Stripe, use endpoint:
```
PUT https://{INSTANCE_URL}/api/externalOrders/updateCheckoutUrl?orderId=${orderId}
```
!!!warning
#### JSON payload and response are the same as for Secupay.
!!!
---

## Wert.io as a provider

Create analogically the order as above, but with ```"paymentMethod":"wert"```

Use below endpoint to get Wert data:
```
GET https://{INSTANCE_URL}/api/public/order/wertIo?orderId=${orderId}
```
!!!warning
Response data use in a Wert Modal
!!!

```React
import WertModule from "@wert-io/module-react-component";
.
.
<WertModule options={wertOptions} />
```