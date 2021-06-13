---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/slatedocs/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Listings

## Get All Listings

```shell
curl "https://csgofloat.com/api/v1/listings"
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": "321906995529646373",
        "created_at": "2021-06-07T07:03:28.478474Z",
        "type": "buy_now",
        "price": 2061900,
        "state": "listed",
        "seller": {
            "avatar": "https://steamcdn-a.akamaihd.net/steamcommunity/public/images/avatars/e2/e235f369bdfb59b54b59bc3b258ea1f64758fac1_full.jpg",
            "flags": 48,
            "online": false,
            "stall_public": true,
            "statistics": {
                "median_trade_time": 1940,
                "total_failed_trades": 0,
                "total_trades": 38,
                "total_verified_trades": 38
            },
            "steam_id": "76561197975205218",
            "username": "magnemaus"
        },
        "item": {
            "asset_id": "21559522401",
            "def_index": 515,
            "paint_index": 619,
            "paint_seed": 543,
            "float_value": 0.03165145590901375,
            "icon_url": "-9a81dlWLwJ2UUGcVs_nsVtzdOEdtWwKGZZLQHTxDZ7I56KU0Zwwo4NUX4oFJZEHLbXH5ApeO4YmlhxYQknCRvCo04DEVlxkKgpovbSsLQJf0ebcZThQ6tCvq4GGqOT1I6vZn3lU18hwmOvN8IXvjVCLqSwwOj6rYJiRdg42NAuE-lW5kri5hpbuvM7AzHtmsnMh4imPzUa3gB4aaOw9hfCeVxzAUJ5TOTzr",
            "d_param": "4920288687732198929",
            "is_stattrak": false,
            "is_souvenir": false,
            "rarity": 6,
            "quality": 3,
            "market_hash_name": "★ Butterfly Knife | Doppler (Factory New)",
            "low_rank": 456,
            "high_rank": 270,
            "tradable": 0,
            "inspect_link": "steam://rungame/730/76561202255233023/+csgo_econ_action_preview%20S76561197975205218A21559522401D4920288687732198929",
            "has_screenshot": true,
            "scm": {
                "price": 3203808,
                "volume": 1
            },
            "item_name": "★ Butterfly Knife | Doppler",
            "wear_name": "Factory New",
            "phase": "Sapphire",
            "description": "It has been painted with black and silver metallic paints using a marbleizing medium, then candy coated.\\n\\n<i>Getting lost in its color can prove fatal</i>",
            "badges": []
        },
        "is_seller": false,
        "min_offer_price": 1958805,
        "max_offer_discount": 500,
        "is_watchlisted": false,
        "watchers": 0
    },
    {
        "id": "319448156230257615",
        "created_at": "2021-05-31T12:12:55.509603Z",
        "type": "buy_now",
        "price": 795000,
        "state": "listed",
        "seller": {
            "avatar": "https://steamcdn-a.akamaihd.net/steamcommunity/public/images/avatars/25/2568a702116748ccfd2c9aed9378f2a1bfd3bf2f_full.jpg",
            "flags": 48,
            "online": false,
            "stall_public": true,
            "statistics": {
                "median_trade_time": 697,
                "total_failed_trades": 0,
                "total_trades": 1,
                "total_verified_trades": 1
            },
            "steam_id": "76561198168522001",
            "username": "¡VSN B/S>Skins +Trading"
        },
        "item": {
            "asset_id": "21903991402",
            "def_index": 507,
            "paint_index": 415,
            "paint_seed": 642,
            "float_value": 0.034549176692962646,
            "icon_url": "-9a81dlWLwJ2UUGcVs_nsVtzdOEdtWwKGZZLQHTxDZ7I56KU0Zwwo4NUX4oFJZEHLbXH5ApeO4YmlhxYQknCRvCo04DEVlxkKgpovbSsLQJf2PLacDBA5ciJlY20heL2KoTcl3lT5MB4kOzFyoD8j1yg5UNkaz_xIdfEd1A5aQ3U-lPskunphJHptZvPwSM26CUht3_UmUe3gEpSLrs4ZlidBgY",
            "d_param": "14621055123599774367",
            "is_stattrak": false,
            "is_souvenir": false,
            "rarity": 6,
            "quality": 3,
            "market_hash_name": "★ Karambit | Doppler (Factory New)",
            "low_rank": 465,
            "high_rank": 151,
            "tradable": 0,
            "inspect_link": "steam://rungame/730/76561202255233023/+csgo_econ_action_preview%20S76561198168522001A21903991402D14621055123599774367",
            "has_screenshot": true,
            "scm": {
                "price": 1301546,
                "volume": 5
            },
            "item_name": "★ Karambit | Doppler",
            "wear_name": "Factory New",
            "phase": "Ruby",
            "description": "It has been painted with black and silver metallic paints using a marbleizing medium, then candy coated.\\n\\n<i>Getting lost in its color can prove fatal</i>",
            "badges": []
        },
        "is_seller": false,
        "min_offer_price": 675750,
        "max_offer_discount": 1500,
        "is_watchlisted": false,
        "watchers": 0
    }
]
```

This endpoint retrieves all listings.

### HTTP Request

`GET https://csgofloat.com/api/v1/listings`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 0 | Which page of listings to start from
limit | 100 | How many listings to return
order | `best_deal` | How to order the listings
category | 0 | Can be one of: <ul><li>0 = `any`</li><li>1 = `normal`</li><li>2 = `stattrak`</li><li>3 = `souvenir`</li></ul>
def_index | | Only include listings that have a one of the given def index(es)
min_float | | Only include listings that have a float higher then this
max_float | | Only include listings that have a float lower then this
rarity | | Only include listings that have this rarity
paint_seed | | Only include listings that have this paint seed
paint_index | | Only include listings that have this paint index
user_id | | Only include listings from this user
collection | | Only include listings from this collection
min_price | | Only include listings have a price higher then this
max_price | | Only include listings have a price lower then this
market_hash_name | | Only include listings that have this market hash name
type | | Can be one of: <ul><li>`buy_now`</li><li>`auction`</li></ul>
stickers | | Must be in the form: `<STICKER-ID>\|<POSITION>[,<STICKER-ID>\|<POSITION>...]`

## Get a Specific Listing

```shell
curl "http://csgofloat.com/api/v1/listings/<LISTING-ID>"
```

> The above command returns JSON structured like this:

```json
{
    "id": "292312870132253796",
    "created_at": "2021-03-17T15:06:59.155367Z",
    "type": "buy_now",
    "price": 8900,
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

This endpoint retrieves a specific listing.

### HTTP Request

`GET http://csgofloat.com/api/v1/listings/<LISTING-ID>`

### URL Parameters

Parameter | Description
--------- | -----------
listing_id | The ID of the listing to retrieve

