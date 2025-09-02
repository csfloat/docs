---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - http

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Introduction

Welcome to the CSFloat API! You can use our API to access CSFloat API endpoints such as market listings, inspect link retrieval, and more!

You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

CSFloat uses API keys to allow access to the API. You can register a new CSFloat API key on your [profile](https://csfloat.com/profile) under the "developer" tab.

CSFloat API expects for the API key to be included in most API requests. Endpoints that require an API Key will state so. The authorization header should look like the following:

`Authorization: <API-KEY>`

<aside class="notice">
You must replace <code>&lt;API-KEY&gt;</code> with your personal API key.
</aside>

# Listings

## Get All Listings

```shell
curl "https://csfloat.com/api/v1/listings"
```

> The above command returns JSON structured like this:

```json
[
    {
    "id": "324288155723370196",
    "created_at": "2021-06-13T20:45:21.311794Z",
    "type": "buy_now",
    "price": 260000,
    "state": "listed",
    "seller": {
        "avatar": "https://steamcdn-a.akamaihd.net/steamcommunity/public/images/avatars/97/974f0a94f47f50a1a6a769fc8ff093cb93a49066_full.jpg",
        "flags": 435,
        "online": true,
        "stall_public": true,
        "statistics": {
            "median_trade_time": 236,
            "total_failed_trades": 0,
            "total_trades": 24,
            "total_verified_trades": 24
        },
        "steam_id": "76561198084749846",
        "username": "Step7750"
    },
    "item": {
        "asset_id": "22547095285",
        "def_index": 16,
        "paint_index": 449,
        "paint_seed": 700,
        "float_value": 0.02796577662229538,
        "icon_url": "-9a81dlWLwJ2UUGcVs_nsVtzdOEdtWwKGZZLQHTxDZ7I56KU0Zwwo4NUX4oFJZEHLbXH5ApeO4YmlhxYQknCRvCo04DEVlxkKgpou-6kejhjxszYfi5H5di5mr-HnvD8J_WCkmkEvp0pi7zDodv3jAHj-UM5ZGr7INfHJAc9MlzV-FK_kO281pa_ot2XnrA-A3kA",
        "d_param": "17054198177995786400",
        "is_stattrak": false,
        "is_souvenir": false,
        "rarity": 5,
        "quality": 4,
        "market_hash_name": "M4A4 | Poseidon (Factory New)",
        "stickers": [
            {
                "stickerId": 1060,
                "slot": 3,
                "icon_url": "columbus2016/nv_holo.fbbf7dc3ef16ade69ac294589fbe97f0a3169003.png",
                "name": "Sticker | Team EnVyUs (Holo) | MLG Columbus 2016",
                "scm": {
                    "price": 736,
                    "volume": 1
                }
            }
        ],
        "tradable": 0,
        "inspect_link": "steam://rungame/730/76561202255233023/+csgo_econ_action_preview%20S76561198084749846A22547095285D17054198177995786400",
        "has_screenshot": true,
        "scm": {
            "price": 175076,
            "volume": 0
        },
        "item_name": "M4A4 | Poseidon",
        "wear_name": "Factory New",
        "description": "It has been custom painted with a depiction of a battle between Pisces and Poseidon.\\n\\n<i>Three can keep a secret if two of them are dead</i>",
        "collection": "The Gods and Monsters Collection",
        "badges": []
    },
    "is_seller": false,
    "min_offer_price": 221000,
    "max_offer_discount": 1500,
    "is_watchlisted": false,
    "watchers": 0
  }
  ...
]
```

This endpoint retrieves all active listings on CSFloat Market.

### HTTP Request

`GET https://csfloat.com/api/v1/listings`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
cursor | | Opaque cursor string from a previous fetch, used to fetch the next results
limit | 50 | How many listings to return. Max of 50.
sort_by | `best_deal` | How to order the listings. Can be one of: <ul><li>`lowest_price`</li><li>`highest_price`</li><li>`most_recent`</li><li>`expires_soon`</li><li>`lowest_float`</li><li>`highest_float`</li><li>`best_deal`</li><li>`highest_discount`</li><li>`float_rank`</li><li>`num_bids`</li></ul>
category | 0 | Can be one of: 0 = `any`, 1 = `normal`, 2 = `stattrak`, 3 = `souvenir`
def_index | | Only include listings that have a one of the given def index(es)
min_float | | Only include listings that have a float higher than this
max_float | | Only include listings that have a float lower than this
rarity | | Only include listings that have this rarity
paint_seed | | Only include listings that have this paint seed
paint_index | | Only include listings that have this paint index
user_id | | Only include listings from this SteamID64
collection | | Only include listings from this collection (ie. `set_bravo_ii`, derived from the schema)
min_price | | Only include listings have a price higher than this (in cents)
max_price | | Only include listings have a price lower than this (in cents)
market_hash_name | | Only include listings that have this market hash name
type | | Either `buy_now` or `auction`
stickers | | Must be in the form: <code>ID&#124;POSITION?[,ID&#124;POSITION?...]</code>. Position being the sticker slot on the weapon.

## Get a Specific Listing

```shell
curl "https://csfloat.com/api/v1/listings/324288155723370196"
```

> The above command returns JSON structured like this:

```json
{
    "id": "324288155723370196",
    "created_at": "2021-06-13T20:45:21.311794Z",
    "type": "buy_now",
    "price": 260000,
    "state": "listed",
    "seller": {
        "avatar": "https://steamcdn-a.akamaihd.net/steamcommunity/public/images/avatars/97/974f0a94f47f50a1a6a769fc8ff093cb93a49066_full.jpg",
        "flags": 435,
        "online": true,
        "stall_public": true,
        "statistics": {
            "median_trade_time": 236,
            "total_failed_trades": 0,
            "total_trades": 24,
            "total_verified_trades": 24
        },
        "steam_id": "76561198084749846",
        "username": "Step7750"
    },
    "item": {
        "asset_id": "22547095285",
        "def_index": 16,
        "paint_index": 449,
        "paint_seed": 700,
        "float_value": 0.02796577662229538,
        "icon_url": "-9a81dlWLwJ2UUGcVs_nsVtzdOEdtWwKGZZLQHTxDZ7I56KU0Zwwo4NUX4oFJZEHLbXH5ApeO4YmlhxYQknCRvCo04DEVlxkKgpou-6kejhjxszYfi5H5di5mr-HnvD8J_WCkmkEvp0pi7zDodv3jAHj-UM5ZGr7INfHJAc9MlzV-FK_kO281pa_ot2XnrA-A3kA",
        "d_param": "17054198177995786400",
        "is_stattrak": false,
        "is_souvenir": false,
        "rarity": 5,
        "quality": 4,
        "market_hash_name": "M4A4 | Poseidon (Factory New)",
        "stickers": [
            {
                "stickerId": 1060,
                "slot": 3,
                "icon_url": "columbus2016/nv_holo.fbbf7dc3ef16ade69ac294589fbe97f0a3169003.png",
                "name": "Sticker | Team EnVyUs (Holo) | MLG Columbus 2016",
                "scm": {
                    "price": 736,
                    "volume": 1
                }
            }
        ],
        "tradable": 0,
        "inspect_link": "steam://rungame/730/76561202255233023/+csgo_econ_action_preview%20S76561198084749846A22547095285D17054198177995786400",
        "has_screenshot": true,
        "scm": {
            "price": 175076,
            "volume": 0
        },
        "item_name": "M4A4 | Poseidon",
        "wear_name": "Factory New",
        "description": "It has been custom painted with a depiction of a battle between Pisces and Poseidon.\\n\\n<i>Three can keep a secret if two of them are dead</i>",
        "collection": "The Gods and Monsters Collection",
        "badges": []
    },
    "is_seller": false,
    "min_offer_price": 221000,
    "max_offer_discount": 1500,
    "is_watchlisted": false,
    "watchers": 0
}
```

This endpoint retrieves the details for a specific listing, regardless of whether it is "active" or "in-active" (ie. `state` != `listed`).

### HTTP Request

`GET https://csfloat.com/api/v1/listings/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the listing to retrieve

## List an item

```shell
curl -X POST "https://csfloat.com/api/v1/listings" \
-H "Authorization: <API-KEY>; Content-Type: application/json" \
-d '{"asset_id": 21078095468, "type": "buy_now", "price": 8900, "description": "Just for show", "private": false}'
```

> The above command returns JSON structured like this:

```json
{
    "id": "292312870132253796",
    "created_at": "2021-03-17T15:06:59.155367Z",
    "type": "buy_now",
    "price": 8900,
    "description": "Just for show",
    "state": "listed",
    "seller": {
        "flags": 48,
        "obfuscated_id": "9169061817522033479",
        "online": false,
        "stall_public": false,
        "statistics": {
            "median_trade_time": 305,
            "total_failed_trades": 0,
            "total_trades": 13,
            "total_verified_trades": 13
        }
    },
    "item": {
        "asset_id": "21078095468",
        "def_index": 60,
        "paint_index": 77,
        "paint_seed": 346,
        "float_value": 0.26253828406333923,
        "icon_url": "-9a81dlWLwJ2UUGcVs_nsVtzdOEdtWwKGZZLQHTxDZ7I56KU0Zwwo4NUX4oFJZEHLbXH5ApeO4YmlhxYQknCRvCo04DEVlxkKgpou-6kejhz2v_Nfz5H_uO-jb-NmOXxIK_ulGRD7cR9teTE8YXghRrhrRBrMWD7coCQegU6aQyE_gC6xOi6gJC5tJTMn3BqvyNztH_VnRS-n1gSOeVXeHpm",
        "d_param": "721253437254664138",
        "is_stattrak": false,
        "is_souvenir": false,
        "rarity": 2,
        "quality": 4,
        "market_hash_name": "M4A1-S | Boreal Forest (Field-Tested)",
        "stickers": [
            {
                "stickerId": 55,
                "slot": 0,
                "icon_url": "emskatowice2014/fnatic.7f37dae42f8afbd799b89f77334be023368ba27a.png",
                "name": "Sticker | Fnatic | Katowice 2014",
                "scm": {
                    "price": 41000,
                    "volume": 0
                }
            },
            {
                "stickerId": 55,
                "slot": 1,
                "wear": 0.09002881,
                "icon_url": "emskatowice2014/fnatic.7f37dae42f8afbd799b89f77334be023368ba27a.png",
                "name": "Sticker | Fnatic | Katowice 2014",
                "scm": {
                    "price": 41000,
                    "volume": 0
                }
            },
            {
                "stickerId": 73,
                "slot": 2,
                "wear": 0.21217501,
                "icon_url": "emskatowice2014/reason.d48f01f2758c2852ef32a68c49f7039ce211500a.png",
                "name": "Sticker | Reason Gaming | Katowice 2014",
                "scm": {
                    "price": 118625,
                    "volume": 0
                }
            },
            {
                "stickerId": 73,
                "slot": 3,
                "icon_url": "emskatowice2014/reason.d48f01f2758c2852ef32a68c49f7039ce211500a.png",
                "name": "Sticker | Reason Gaming | Katowice 2014",
                "scm": {
                    "price": 118625,
                    "volume": 0
                }
            }
        ],
        "tradable": 0,
        "has_screenshot": true,
        "scm": {
            "price": 11,
            "volume": 0
        },
        "item_name": "M4A1-S | Boreal Forest",
        "wear_name": "Field-Tested",
        "description": "It has been painted using a forest camouflage hydrographic.\\n\\n<i>The woods can be a dangerous place... never travel alone</i>",
        "collection": "The Italy Collection",
        "badges": []
    },
    "is_seller": false,
    "min_offer_price": 7565,
    "max_offer_discount": 1500,
    "is_watchlisted": false,
    "watchers": 0
}
```

This endpoint lists the item specified by `asset_id`. Requires an authorization header.

### HTTP Request

`POST https://csfloat.com/api/v1/listings`

### Body Parameters

Parameter | Default | Description | Optional
--------- | --------| ----------- | ----------
type | `buy_now` | Either `buy_now` or `auction` | YES
asset_id | | The ID of the item to list | NO
price | | Either the `buy_now` price or the current bid or reserve price on an `auction` | NO (if `buy_now`)
max_offer_discount | Set in user profile | `buy_now` max discount for an offer. This will override the default set in your profile. | YES
reserve_price  | | `auction` start price | NO (if `auction`)
duration_days | | `auction` duration in days. Can be: `1`, `3`, `5`, `7`, or `14` | NO (if `auction`)
description | | User defined description. Max characters of 180. | YES
private | false | If `true`, will hide listings from public searches | YES
