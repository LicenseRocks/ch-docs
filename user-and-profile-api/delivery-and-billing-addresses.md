---
label: Delivery and billing addresses
tags: [deliver-address, billing-address, addresses, billing, delivery]
order: 5
authors:
  - name: Igor Klepacki
    email: igor@licenserocks.de
    link: https://twitter.com/igorklepacki
    avatar:
---

# Profile information API

On this page you'll find detailed information how to create, update, delete and retrieve info about certain user's all delivery addresses and billing adresses with possibility to manipulate this data using our public API.

!!!warning Authentication
All requests sent to our User and Profile API (including the one you're viewing documentation of at this moment) must pass the authentication. [Learn more](/authorization)
!!!

#### Technical details:

- `{INSTANCE_URL}` is URL of current instance without slash at the end and protocol. e.g. _creators-hub-instance.com_
- `{USER_ID}` is ID of an user you want to fetch/modify avatar from/for. e.g. _6_
- `{DELIVERY_ADDRESS_ID}` is ID of delivery address entry in instance database
- `{BILLING_ADDRESS_ID}` is ID of billing address entry in instance database

## Delivery address

### Get user's all delivery addresses

To get other user's delivery addresses:

```
GET https://{INSTANCE_URL}/api/public/user/{USER_ID}/deliveryAddresses
```

To get your delivery addresses:

```
GET https://{INSTANCE_URL}/api/public/user/me/deliveryAddresses
```

---

```json Response
{
  "deliveryAddresses": [
    {
      "id": 2,
      "userId": 6,
      "name": null,
      "street": "Sezamkowa 14",
      "postal": null,
      "city": null,
      "country": null,
      "companyName": null,
      "taxId": null,
      "email": null,
      "mobilePhone": null,
      "default": false,
      "createdAt": "2023-02-21T13:42:18.056Z",
      "updatedAt": "2023-02-21T13:42:37.028Z",
      "deletedAt": null
    }
  ]
}
```

### Create delivery address

```
POST https://{INSTANCE_URL}/api/public/deliveryAddress?id={DELIVERY_ADDRESS_ID}
```

!!!info Attaching delivery address to user
Since user can have multiple delivery addresses, when creating a new one it **must be attached** to an existing user. This can be easily done by providing `userId` property in the data below.
!!!

```json Payload (application/json)
{
  "userId": 6,
  "name": "Buzz Lightyear",
  "street": "Cosmos",
  "postal": "00-001",
  "city": "Mars Central Station",
  "country": "Moon",
  "companyName": "License Rocks",
  "taxId": "0",
  "email": "buzzlightyear@space-mission.de",
  "mobilePhone": "+48 133 713 371"
}
```

```json Response
{
  "newDeliveryAddress": {
    "id": 4,
    "userId": 6,
    "name": "Buzz Lightyear",
    "street": "Cosmos",
    "postal": "00-001",
    "city": "Mars Central Station",
    "country": "Moon",
    "companyName": "License Rocks",
    "taxId": "0",
    "email": "buzzlightyear@space-mission.de",
    "mobilePhone": "+48 133 713 371",
    "default": false,
    "createdAt": "2023-02-22T14:58:58.082Z",
    "updatedAt": "2023-02-22T14:58:58.082Z",
    "deletedAt": null
  }
}
```

### Update particular delivery address

```
PUT https://{INSTANCE_URL}/api/public/deliveryAddress?id={DELIVERY_ADDRESS_ID}
```

```json Payload (application/json)
{
  "name": "Igor Klepacki",
  "street": "Sezamkowa",
  "postal": "99-999",
  "city": "Sezamki",
  "country": "Poland",
  "companyName": "License Rocks",
  "taxId": "1337",
  "email": "igor@licenserocks.de",
  "mobilePhone": "+48 133 713 371"
}
```

```json Response
{
  "updatedDeliveryAddress": {
    "id": 2,
    "userId": 6,
    "name": "Igor Klepacki",
    "street": "Sezamkowa",
    "postal": "99-999",
    "city": "Sezamki",
    "country": "Poland",
    "companyName": "License Rocks",
    "taxId": "1337",
    "email": "igor@licenserocks.de",
    "mobilePhone": "+48 133 713 371",
    "default": false,
    "createdAt": "2023-02-21T13:42:18.056Z",
    "updatedAt": "2023-02-22T14:47:53.846Z",
    "deletedAt": "2023-02-22T14:47:53.845Z"
  }
}
```

### Delete particular delivery address

```
DELETE https://{INSTANCE_URL}/api/public/deliveryAddress?id={DELIVERY_ADDRESS_ID}
```

```json Response
{
  "updatedDeliveryAddress": {
    "id": 3,
    "userId": 6,
    "name": "Igor Klepacki",
    "street": "Sezamkowa",
    "postal": "99-999",
    "city": "Sezamki",
    "country": "Poland",
    "companyName": "License Rocks",
    "taxId": "1337",
    "email": "igor@licenserocks.de",
    "mobilePhone": "+48 133 713 371",
    "default": false,
    "createdAt": "2023-02-22T08:59:34.633Z",
    "updatedAt": "2023-02-22T14:46:32.925Z",
    "deletedAt": "2023-02-22T14:46:32.924Z"
  }
}
```

!!!info Note about deleting addresses
After deleting delivery address it will **no longer appear in results of [GET delivery addresses](#delivery-address)** and **cannot be manipulated by [PUT update delivery address](#update-particular-delivery-address)** or **[DELETE delete delivery address](#delete-particular-delivery-address)**
!!!

## Billing address

### Get user's all billing addresses

To get other user's delivery addresses:

```
GET https://{INSTANCE_URL}/api/public/user/{USER_ID}/billingAddresses
```

To get your billing addresses

```
GET https://{INSTANCE_URL}/api/public/user/me/billingAddresses
```

---

```json Response
{
  "billingAddresses": [
    {
      "id": 3,
      "isDefault": false,
      "city": "Mars Central Station",
      "country": "Moon",
      "companyName": "License Rocks",
      "postal": "00-001",
      "street": "Cosmos",
      "taxId": "0",
      "userId": 6,
      "createdAt": "2023-02-22T20:43:18.902Z",
      "deletedAt": null,
      "updatedAt": "2023-02-22T20:43:18.903Z"
    }
  ]
}
```

### Create billing address

```
POST https://{INSTANCE_URL}/api/public/deliveryAddress?id={BILLING_ADDRESS_ID}
```

!!!warning Attaching billing address to user
Since user can have multiple delivery addresses, when creating a new one it **must be attached** to an existing user. This can be easily done by providing `userId` property in the data below.
!!!

```json Payload (application/json)
{
  "userId": 6,
  "street": "Cosmos",
  "postal": "00-001",
  "city": "Mars Central Station",
  "country": "Moon",
  "companyName": "License Rocks",
  "taxId": "0"
}
```

```json Response
{
  "newBillingAddress": {
    "id": 4,
    "isDefault": false,
    "city": "Mars Central Station",
    "country": "Moon",
    "companyName": "License Rocks",
    "postal": "00-001",
    "street": "Cosmos",
    "taxId": "0",
    "userId": 6,
    "createdAt": "2023-02-22T20:43:33.958Z",
    "deletedAt": null,
    "updatedAt": "2023-02-22T20:43:33.959Z"
  }
}
```

### Update particular billing address

```
PUT https://{INSTANCE_URL}/api/public/billingAddress?id={DELIVERY_ADDRESS_ID}
```

```json Payload (application/json)
{
  "street": "Cosmos",
  "postal": "00-001",
  "city": "Venus East Station",
  "country": "Moon",
  "companyName": "License Rocks",
  "taxId": "0"
}
```

```json Response
{
  "updatedBillingAddress": {
    "id": 3,
    "isDefault": false,
    "city": "Venus East Station",
    "country": "Moon",
    "companyName": "License Rocks",
    "postal": "00-001",
    "street": "Cosmos",
    "taxId": "0",
    "userId": 6,
    "createdAt": "2023-02-22T20:43:33.958Z",
    "deletedAt": null,
    "updatedAt": "2023-02-22T20:45:47.655Z"
  }
}
```

### Delete particular billing address

```
DELETE https://{INSTANCE_URL}/api/public/billingAddress?id={DELIVERY_ADDRESS_ID}
```

```json Response
{
  "updatedBillingAddress": {
    "id": 4,
    "isDefault": false,
    "city": "Venus East Station",
    "country": "Moon",
    "companyName": "License Rocks",
    "postal": "00-001",
    "street": "Cosmos",
    "taxId": "0",
    "userId": 6,
    "createdAt": "2023-02-22T20:43:33.958Z",
    "deletedAt": "2023-02-22T20:46:36.158Z",
    "updatedAt": "2023-02-22T20:46:36.159Z"
  }
}
```

!!!warning Note about deleting addresses
After deleting delivery address it will **no longer appear in results of [GET delivery addresses](#delivery-address)** and **cannot be manipulated by [PUT update delivery address](#update-particular-delivery-address)** or **[DELETE delete delivery address](#delete-particular-delivery-address)**
!!!
