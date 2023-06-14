---
label: Adding Addresses
tags: [manage, nft]
order: 4
authors:
- name: Kacper Hernacki
  email: kacper@licenserocks.de
  avatar: ../static/kacper.jpeg
  link: https://twitter.com/KacperHernacki
---
# Adding addresses

When it comes to creating orders, you need to provide billing and shipping addresses. In this section you will learn how to add them to your platform.

## Billing address

Use below endpoint in order to create new billing address for a user.

```
POST https://{INSTANCE_URL}/api/public/billingAddress
```
## Delivery address

Use below endpoint in order to create new delivery address for a user.

```
POST https://{INSTANCE_URL}/api/public/deliveryAddress
```
## Body of the request

```json Payload (application/json)
{
  "street": "street 123",
  "postal": "12345",
  "city": "Berlin",
  "country": "Germany",
  "companyName": "Licenserocks",
  "taxId": "1234567890",
  "userId": 12
}
```

## Response

```json Response (application/json)
{
  "billingAddress": {
    "id": 13,
    "street": "street 123",
    "postal": "12345",
    "city": "Berlin",
    "country": "Germany",
    "companyName": "Licenserocks",
    "taxId": "1234567890",
    "userId": 12,
    "isDefault": false
  }
}
```