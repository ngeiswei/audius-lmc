# Audius Libre Music Challenge

Resources on how to create and manage Libre Music Challenge with
Audius.

## REST API

The following is obtained from the [Audius API](https://docs.audius.org/api).

There is REQUEST box where one can enter parameters and get the
corresponding CURL command.

### Glossary

- *User ID*: Internal ID
- *User Handle*: User as it appears on the Audius URL.  For instance,
  the URL https://audius.co/A_Lin the handle of the corresponding user
  is A_Lin.

### Get Bulk Users

```bash
curl -L -X GET 'https://api.audius.co/v1/users?id=Lx88z' -H 'Accept: application/json' | jq
```

### Get list of users by ID

```bash
curl -L -X GET 'https://api.audius.co/v1/users?user_id=27731&id="Lx88z"' -H 'Accept: application/json | jq'
```

outputs

```json
{
  "code": 403,
  "error": "You are not authorized to make this request authedWallet= myId=27731"
}
```

### Get User IDs by addresses

```bash
curl -L -X GET 'https://api.audius.co/v1/users/address?address=0x04282c359df38d8a2df75f82be4b9b494b529547' -H 'Accept: application/json' | jq
```

outputs

```json
{
  "data": [
    {
      "user_id": "Lx88z",
      "address": "0x04282c359df38d8a2df75f82be4b9b494b529547"
    }
  ]
}
```

### Get User by Handle

```bash
curl -L -X GET 'https://api.audius.co/v1/users/handle/kennygotsoul' -H 'Accept: application/json' | jq
```

outputs

```
{
  "data": {
    "id": "Lx88z",
    "album_count": 0,
    "artist_pick_track_id": null,
    "bio": null,
    "cover_photo": {
      "640x": "https://cn4.mainnet.audiusindex.org/content/Qmen9kwHMVvNApy3UAXKMrjaUnDw6EgE5bAGNWhuiUg6rq/640x.jpg",
      "2000x": "https://cn4.mainnet.audiusindex.org/content/Qmen9kwHMVvNApy3UAXKMrjaUnDw6EgE5bAGNWhuiUg6rq/2000x.jpg",
      "mirrors": [
        "https://audius-content-3.figment.io",
        "https://audius-creator-2.theblueprint.xyz",
        "https://creatornode2.audius.co"
      ]
    },
    "followee_count": 3,
    "follower_count": 105,
    "handle": "kennygotsoul",
    "is_verified": true,
    "twitter_handle": "kennygotsoul",
    "instagram_handle": null,
    "tiktok_handle": null,
    "verified_with_twitter": true,
    "verified_with_instagram": false,
    "verified_with_tiktok": false,
    "website": null,
    "donation": null,
    "location": "Burbank, CA",
    "name": "R&B Kenny ",
    "playlist_count": 0,
    "profile_picture": {
      "150x150": "https://audius-creator-11.theblueprint.xyz/content/QmZQBcZSvByYsNkez7FaNbWXv6dog2BrCEXCEJj67kysW9/150x150.jpg",
      "480x480": "https://audius-creator-11.theblueprint.xyz/content/QmZQBcZSvByYsNkez7FaNbWXv6dog2BrCEXCEJj67kysW9/480x480.jpg",
      "1000x1000": "https://audius-creator-11.theblueprint.xyz/content/QmZQBcZSvByYsNkez7FaNbWXv6dog2BrCEXCEJj67kysW9/1000x1000.jpg",
      "mirrors": [
        "https://audius-discovery-7.cultur3stake.com",
        "https://audius-content-5.cultur3stake.com",
        "https://creatornode2.audius.co"
      ]
    },
    "repost_count": 0,
    "track_count": 2,
    "is_deactivated": false,
    "is_available": true,
    "erc_wallet": "0x04282c359df38d8a2df75f82be4b9b494b529547",
    "spl_wallet": "7DRwqjsJyUqsiKd1uLLu43uoRnnwngbtQcN9S9B2LhxB",
    "spl_usdc_wallet": null,
    "spl_usdc_payout_wallet": null,
    "supporter_count": 1,
    "supporting_count": 0,
    "total_audio_balance": 6,
    "wallet": "0x04282c359df38d8a2df75f82be4b9b494b529547"
  }
}
```

### Get User

```bash
curl -L -X GET 'https://api.audius.co/v1/users/Lx88z' -H 'Accept: application/json'
```

outputs

```
{
  "data": {
    "id": "Lx88z",
    "album_count": 0,
    "artist_pick_track_id": null,
    "bio": null,
    "cover_photo": {
      "640x": "https://audius-creator-2.theblueprint.xyz/content/Qmen9kwHMVvNApy3UAXKMrjaUnDw6EgE5bAGNWhuiUg6rq/640x.jpg",
      "2000x": "https://audius-creator-2.theblueprint.xyz/content/Qmen9kwHMVvNApy3UAXKMrjaUnDw6EgE5bAGNWhuiUg6rq/2000x.jpg",
      "mirrors": [
        "https://cn4.mainnet.audiusindex.org",
        "https://audius-content-3.figment.io",
        "https://creatornode2.audius.co"
      ]
    },
    "followee_count": 3,
    "follower_count": 105,
    "handle": "kennygotsoul",
    "is_verified": true,
    "twitter_handle": "kennygotsoul",
    "instagram_handle": null,
    "tiktok_handle": null,
    "verified_with_twitter": true,
    "verified_with_instagram": false,
    "verified_with_tiktok": false,
    "website": null,
    "donation": null,
    "location": "Burbank, CA",
    "name": "R&B Kenny ",
    "playlist_count": 0,
    "profile_picture": {
      "150x150": "https://audius-creator-11.theblueprint.xyz/content/QmZQBcZSvByYsNkez7FaNbWXv6dog2BrCEXCEJj67kysW9/150x150.jpg",
      "480x480": "https://audius-creator-11.theblueprint.xyz/content/QmZQBcZSvByYsNkez7FaNbWXv6dog2BrCEXCEJj67kysW9/480x480.jpg",
      "1000x1000": "https://audius-creator-11.theblueprint.xyz/content/QmZQBcZSvByYsNkez7FaNbWXv6dog2BrCEXCEJj67kysW9/1000x1000.jpg",
      "mirrors": [
        "https://audius-discovery-7.cultur3stake.com",
        "https://audius-content-5.cultur3stake.com",
        "https://creatornode2.audius.co"
      ]
    },
    "repost_count": 0,
    "track_count": 2,
    "is_deactivated": false,
    "is_available": true,
    "erc_wallet": "0x04282c359df38d8a2df75f82be4b9b494b529547",
    "spl_wallet": "7DRwqjsJyUqsiKd1uLLu43uoRnnwngbtQcN9S9B2LhxB",
    "spl_usdc_wallet": null,
    "spl_usdc_payout_wallet": null,
    "supporter_count": 1,
    "supporting_count": 0,
    "total_audio_balance": 6,
    "wallet": "0x04282c359df38d8a2df75f82be4b9b494b529547"
  }
}
```

### Get User Challenges

```bash
curl -L -X GET 'https://api.audius.co/v1/users/Lx88z/challenges' -H 'Accept: application/json' | jq
```

outputs something very long.

### Search Users

```bash
curl -L -X GET 'https://api.audius.co/v1/users/search?limit=1&query="b"' -H 'Accept: application/json' | jq
```

### Get Tracks by User

```bash
curl -L -X GET 'https://api.audius.co/v1/users/RYYlbpg/tracks?limit=100' -H 'Accept: application/json' | jq
```

outputs all last 100 tracks metadata of A_Lin.

### Get Track

```bash
curl -L -X GET 'https://api.audius.co/v1/tracks/1059143530' -H 'Accept: application/json' | jq
```

outputs metadata about *The Hologram* of A_Lin.

### Get Track Access Info

```bash
curl -L -X GET 'https://api.audius.co/v1/tracks/1059143530/access-info' -H 'Accept: application/json' | jq
```

outputs

```json
{
  "data": {
    "access": {
      "stream": true,
      "download": true
    },
    "user_id": "RYYlbpg",
    "blocknumber": 107004300,
    "is_stream_gated": false,
    "stream_conditions": null,
    "is_download_gated": false,
    "download_conditions": null
  }
}
```

### Download Track

```bash
curl -L -X GET 'https://api.audius.co/v1/tracks/1059143530/download' --output the_hologram.flac
```

download *The Hologram* and save it in file `the_hologram.flac`.

## How to create a challenge

1. Go to https://audius.co/libremusicchallenge
2. Click on Upload
3. 

## Resources

- https://stackoverflow.com/questions/39404922/tsc-command-not-found-in-compiling-typescript
- https://turborepo.com/docs/getting-started/installation
- https://docs.audius.org/
- https://audius.co/libremusicchallenge
