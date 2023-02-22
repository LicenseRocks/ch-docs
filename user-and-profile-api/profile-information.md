---
label: Profile information
tags: [profile, information, profile-information]
order: 5
authors:
  - name: Igor Klepacki
    email: igor@licenserocks.de
    link: https://twitter.com/igorklepacki
    avatar:
---

# Profile information API

On this page you'll find detailed information how to manipulate and retrieve info about certain user's profile using our public API.

!!!warning Authentication
All requests sent to our User and Profile API (including the one you're viewing documentation of at this moment) must pass the authentication. [Learn more](/authorization)
!!!

### Technical details:

- `{INSTANCE_URL}` is URL of current instance without slash at the end and protocol. e.g. _creators-hub-instance.com_
- `{USER_ID}` is ID of an user you want to fetch/modify avatar from/for. e.g. _6_

## Get user's current profile information

```
GET https://{INSTANCE_URL}/api/public/user/{USER_ID}/info
```

```json Response
{
  "profile": {
    "id": 2,
    "avatarKey": "1677061054831/userAvatars/6/avatar.jpg",
    "coverKey": null,
    "description": null,
    "location": null,
    "twitterUrl": "https://twitter.com/igorklepacki",
    "facebookUrl": null,
    "instagramUrl": null,
    "websiteUrl": null,
    "ethPublicAddr": null,
    "bankAccount": null,
    "createdAt": "2022-10-27T12:38:14.699Z",
    "updatedAt": "2023-02-22T14:08:43.355Z",
    "userId": 6,
    "seenNotifications": null,
    "country": {
      "label": "Albania",
      "value": "AL"
    },
    "isCreator": null,
    "creatorsData": null,
    "creatorsPosition": null,
    "user": {
      "name": "Igor Klepacki",
      "email": "igor@licenserocks.de",
      "role": {
        "id": 2,
        "name": "Admin",
        "privileges": {
          "feesSet": true,
          "nftMedia": true,
          "settings": true,
          "userRole": true,
          "nftCreate": true,
          "dropManage": true,
          "nftDetails": true,
          "nftPublish": true,
          "userManage": true,
          "nftBuyResell": true,
          "projectCreate": true,
          "collectionCreate": true
        },
        "createdAt": "2022-07-27T09:07:50.096Z",
        "updatedAt": "2022-07-27T09:07:50.097Z"
      },
      "username": "neg4n"
    }
  }
}
```

## Update user's profile

```
PUT https://{INSTANCE_URL}/api/public/user/{USER_ID}/info
```

```json Payload (application/json)
{
  "twitterUrl": "https://twitter.com/igorklepacki",
  "description": "My profile description",
  "facebookUrl": "https://facebook.com/",
  "instagramUrl": "https://instagram.com/",
  "websiteUrl": "https://docs.license.rocks/",
  "country": {
    "label": "Poland",
    "value": "PL"
  }
}
```

```json Response
{
  "updatedProfile": {
    "id": 2,
    "avatarKey": "1677074922600/userAvatars/6/avatar.jpg",
    "coverKey": null,
    "description": "My profile description",
    "location": null,
    "twitterUrl": "https://twitter.com/igorklepacki",
    "facebookUrl": "https://facebook.com/",
    "instagramUrl": "https://instagram.com/",
    "websiteUrl": "https://docs.license.rocks/",
    "ethPublicAddr": null,
    "bankAccount": null,
    "createdAt": "2022-10-27T12:38:14.699Z",
    "updatedAt": "2023-02-22T14:28:18.942Z",
    "userId": 6,
    "seenNotifications": null,
    "country": {
      "label": "Poland",
      "value": "PL"
    },
    "isCreator": null,
    "creatorsData": null,
    "creatorsPosition": null,
    "user": {
      "name": "Igor Klepacki",
      "email": "igor@licenserocks.de",
      "role": {
        "id": 2,
        "name": "Admin",
        "privileges": {
          "feesSet": true,
          "nftMedia": true,
          "settings": true,
          "userRole": true,
          "nftCreate": true,
          "dropManage": true,
          "nftDetails": true,
          "nftPublish": true,
          "userManage": true,
          "nftBuyResell": true,
          "projectCreate": true,
          "collectionCreate": true
        },
        "createdAt": "2022-07-27T09:07:50.096Z",
        "updatedAt": "2022-07-27T09:07:50.097Z"
      },
      "username": "neg4n"
    }
  }
}
```
