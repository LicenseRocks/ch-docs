---
label: Users orders
tags: [profile, information, profile-information]
order: 5
authors:
- name: Kacper Hernacki
  email: igor@licenserocks.de
  link: https://twitter.com/kacperhernacki
  avatar: ../static/kacper.jpeg
---

# Users orders

On this page you'll find detailed information how to manipulate and retrieve info about certain user's profile using our public API.

!!!warning Authentication
All requests sent to our User and Profile API (including the one you're viewing documentation of at this moment) must pass the authentication. [Learn more](/authorization)
!!!

### Technical details:

- `{INSTANCE_URL}` is URL of current instance without slash at the end and protocol. e.g. _creators-hub-instance.com_
- `{USER_ID}` is ID of an user you want to fetch/modify avatar from/for. e.g. _6_
- `{ORDER_TYPE}` is describing if order is purchased or sold. In case of displaying only bought tokens, use `purchased`. To display sold, use `sold` value.
- `{PAGE_NUMBER}` is a an actual page number, which will be passsed so that orders from next page will be returned.


## Get user's current profile information

To get all user's orders

```
GET https://{INSTANCE_URL}/api/public/user/{USER_ID}/orders/getAll
```
---

```json Response
{
  "orders": [
    {
      "id": 1394,
      "totalPriceCents": 10000,
      "totalPriceCurrency": "EUR",
      "totalPriceEth": "92.506938020351",
      "status": "paid",
      "createdAt": "2023-03-07T09:50:13.077Z",
      "billingAddress": {
        "companyName": "",
        "postal": "00-000",
        "street": "testers",
        "taxId": "",
        "city": "Test City",
        "country": null
      },
      "orderItems": [
        {
          "quantity": 1,
          "nft": {
            "Files": [
              {
                "fileName": "97323102877D4E97A9E50A6AD4D5D111_1_201_a.jpeg",
                "id": 1474,
                "key": "0xd061d288194a2107e6c44C34Fe85c67fC15BCeA7/nftFiles/725/cover/97323102877D4E97A9E50A6AD4D5D111_1_201_a.jpeg",
                "storageType": "s3"
              }
            ],
            "id": 725,
            "price": 10000,
            "title": "Test Token"
          },
          "slug": "Test Token",
          "cover": "https://creatorshub.s3.eu-central-1.amazonaws.com/0xd061d288194a2107e6c44C34Fe85c67fC15BCeA7/nftFiles/725/cover/97323102877D4E97A9E50A6AD4D5D111_1_201_a.jpeg"
        }
      ]
    }
  ],
  "meta": {
    "currentPage": 1,
    "offset": 10,
    "pageCount": 1
  }
}
```

To get all user's orders with pagination and types

```
GET https://{INSTANCE_URL}/api/public/user/{USER_ID}/orders/getAll?orderType={ORDER_TYPE}&pageNumber={PAGE_NUMBER}
```