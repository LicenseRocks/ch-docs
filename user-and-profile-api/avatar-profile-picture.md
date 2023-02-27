---
label: Avatars / Profile pictures
tags: [avatar, profile, profile-picture, jpeg]
order: 5
authors:
  - name: Igor Klepacki
    email: igor@licenserocks.de
    link: https://twitter.com/igorklepacki
    avatar:
---

# Avatar / profile picture API

On this page you'll find detailed information how to manipulate and retrieve avatar (a.k.a profile picture) using our public API.

!!!warning Authentication
All requests sent to our User and Profile API (including the one you're viewing documentation of at this moment) must pass the authentication. [Learn more](/authorization)
!!!

### Technical details:

- `{INSTANCE_URL}` is URL of current instance without slash at the end and protocol. e.g. _creators-hub-instance.com_
- `{USER_ID}` is ID of an user you want to fetch/modify avatar from/for. e.g. _6_

## Get user's current avatar URL

```
GET https://{INSTANCE_URL}/api/public/user/{USER_ID}/avatar
```

```json Response
{
  "avatarUrl": "https://creatorshub.s3.eu-central-1.amazonaws.com/1677061054831/userAvatars/6/avatar.jpg"
}
```

## Update user's current avatar with form data

To modify other user's avatar:

```
PUT https://{INSTANCE_URL}/api/public/user/{USER_ID}/updateAvatarFile
```

To modify your avatar:

```
PUT https://{INSTANCE_URL}/api/public/user/me/updateAvatarFile
```

!!!info Note bout the fields
Avatar field should be named `avatar`
!!!

---

```Payload (multipart/form-data)
--
Content-Disposition: form-data; name="avatar"; filename="andrew_ryan.webp"
Content-Type: image/webp
[DATA]
----
```

!!!success Providing avatar format and URL
Unlike for other endpoints, for this one the avatar file does not have to be `image/jpeg` type :rocket:
!!!

```json Response
{
  "avatarUrl": "https://creatorshub.s3.eu-central-1.amazonaws.com/1677074922600/userAvatars/6/avatar.jpg"
}
```

## Update user's current avatar with URL

To modify other user's avatar:

```
PUT https://{INSTANCE_URL}/api/public/user/{USER_ID}/avatar
```

To modify your avatar:

```
PUT https://{INSTANCE_URL}/api/public/user/me/avatar
```

---

```json Payload (application/json)
{
  "avatarUrl": "https://via.placeholder.com/150"
}
```

!!!info Providing avatar format and URL
Currently the best image format we support is `jpeg`. It is recommended for file to be easily convertible to following format since it is hard to detect true type of it programatically.
!!!

```json Response
{
  "avatarUrl": "https://creatorshub.s3.eu-central-1.amazonaws.com/1677074922600/userAvatars/6/avatar.jpg"
}
```

## Update user's current avatar with binary data

To modify other user's avatar:

```
PUT https://{INSTANCE_URL}/api/public/user/{USER_ID}/avatarBytes
```

To modify your avatar:

```
PUT https://{INSTANCE_URL}/api/public/user/me/avatarBytes
```

---

```Payload (image/jpeg)
<raw source of image>
```

!!!info Providing avatar format and URL
Currently the best image format we support is `jpeg`. It is recommended for file to be easily convertible to following format since it is hard to detect true type of it programatically.
!!!

```json Response
{
  "avatarUrl": "https://creatorshub.s3.eu-central-1.amazonaws.com/1677074922600/userAvatars/6/avatar.jpg"
}
```
