---
label: Fetch data
tags: [stats, marketplace, nft]
---
# Get data about your marketplace

In this section you will learn how to use our endpoints for fetching any information related to your marketplace.

## Basic stats (NFTs)

Get basic stats about amount of available NFTs.

```
GET https://{INSTANCE_URL}/api/public/stats
```

```json Response
{
  "stats": {
    "nfts": {
      "total": 12,
      "unique": 2,
      "rare": 9,
      "unlimited": 1
    }
  }
}
```

---

## Recent creators
Get list of most recent creators

```
GET https://{INSTANCE_URL}/api/public/creators
```

```json Response
{
  "stats": {
    "nfts": {
      "total": 12,
      "unique": 2,
      "rare": 9,
      "unlimited": 1
    }
  }
}
```
