---
title: McAPI

language_tabs: # must be one of https://git.io/vQNgJ
  - curl

toc_footers:
  - Jan Krüger, all rights reserved. 2015 - 2018
  - This website is not affiliated with Mojang.
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:

search: true
---

# Introduction

McAPI is in development for almost 4 years by now. It features the latest technology
and a ton of experience which is making it the best Web Minecraft API out there.

## Components

McAPI is one of the most feature rich APIs for Minecraft. - McAPI provides APIs
  for server details (Server API), user details & reputation (User API), Minecraft
  itself and its services (Game API), voting services (Votifier & NuVotifer),
  an image processing service (Image API), donation services (Buycraft API) and
  our own interface called Pipeline API.

## Community

McAPI is for the community. Minecraft is and has always been a community game.
   This project is contributing to this community to become the best it can possibly
   be. It is also community-driven: you can suggest new featueres and engage on
   our GitHub page to improve this project with your own ideas.

## High-Volume API

McAPI is serving millions of requests each day to developers and projects around
   the world. We can do this, because we have experienced what it takes to manage
   this project and what it requires to run smoothly.

## High Availability


McAPI is based and running on the latest hardware. We are using high-availability
cache systems to provide a responsive and trustworthy system. All data is
stored on SSDs or in-memory.

## Made with Love

McAPI is a hobby project driven by its community and made with love (and some tea and pizza).

# Authentication

You are not required to authenticate your application in any way when interacting
with the API. We hope that this trust will not be abused and that we can continue
to offer this API free for all.

<aside class="success">
Remember — fair-use!
</aside>

# Server

## Ping

```curl
curl -XGET -H "Content-type: application/json" 'https://mcapi.de/api/server/ping/play.hivemc.eu'
```

> The above command returns JSON structured like this:

```json
{
  "meta": {
    "status": 200,
    "message": "Ok"
  },
  "data": {
    "online": true,
    "host": "51.255.94.106",
    "port": 25565,
    "software": "BeeCord 1.7.x ➜ 1.12.x",
    "motd": "",
    "players": {
      "online": 2747,
      "max": 20000,
      "list": []
    },
    "favicon": "data:image/png;base64,iVBORw0KGgoAAAAN[...]"
  },
  "cache": {
    "stored": true,
    "updated": {
      "date": "2018-03-07 20:47:36.130514",
      "timezone_type": 3,
      "timezone": "UTC"
    },
    "expires": {
      "date": "2018-03-07 20:57:36.131377",
      "timezone_type": 3,
      "timezone": "UTC"
    }
  }
}
```

### HTTP Request

`GET https://mcapi.de/api/server/ping/{host}[/{port}]`

### Query Parameters

Parameter | Default | Required | Description |
--------- | ------- | -------- | ----------- |
host      | -       | Yes      | The host or IPv4/IPv6 address of the server. |
port      | 25565   | No       | The port of the server. |


## Ping Pocket Edition

```curl
curl -XGET -H "Content-type: application/json" 'https://mcapi.de/api/server/pe/ping/grandtheft.mcpe.me'
```

> The above command returns JSON structured like this:

```json
{
  "meta": {
    "status": 200,
    "message": "Ok"
  },
  "data": {
    "online": true,
    "host": "193.111.199.205",
    "port": 19132,
    "software": "PocketMine-MP 201",
    "gametype": "3589352543432295325",
    "motd": "§f§ograndtheft§r§4§lMCPE§r",
    "version": "1.2.10",
    "players": {
      "online": 41,
      "max": 300,
      "list": []
    }
  },
  "cache": {
    "stored": true,
    "updated": {
      "date": "2018-03-07 20:55:50.643385",
      "timezone_type": 3,
      "timezone": "UTC"
    },
    "expires": {
      "date": "2018-03-07 21:05:50.643884",
      "timezone_type": 3,
      "timezone": "UTC"
    }
  }
}
```

### HTTP Request

`GET https://mcapi.de/api/server/pe/ping/{host}`

### Query Parameters

Parameter | Default | Required | Description |
--------- | ------- | -------- | ----------- |
host      | -       | Yes      | The host or IPv4/IPv6 address of the server. |


## Query

```curl
curl -XGET -H "Content-type: application/json" 'https://mcapi.de/api/server/query/192.168.2.70'
```

> The above command returns JSON structured like this:

```json
{
  "meta": {
    "status": 200,
    "message": "Ok"
  },
  "data": {
    "online": true,
    "host": "192.168.2.70",
    "port": 25565,
    "software": "Spukkit on Bukkit 1.6.4-R2.1-SNAPSHOT",
    "gametype": "SMP",
    "game_id": "MINECRAFT",
    "motd": "A Minecraft Server",
    "version": "1.7.2",
    "map": "world",
    "players": {
      "online": 0,
      "max": 20,
      "list": []
    },
    "plugins": [
      "Votifier 2.3.6-pre",
      "SuperbVote 0.3.4"
    ]
  },
  "cache": {
    "stored": true,
    "updated": {
      "date": "2018-03-08 09:35:12.000000",
      "timezone_type": 3,
      "timezone": "UTC"
    },
    "expires": {
      "date": "2018-03-08 09:45:12.000000",
      "timezone_type": 3,
      "timezone": "UTC"
    }
  }
}
```


### HTTP Request

`GET https://mcapi.de/api/server/query/{host}[/{port}]`

### Query Parameters

Parameter | Default | Required | Description |
--------- | ------- | -------- | ----------- |
host      | -       | Yes      | The host or IPv4/IPv6 address of the server. |
port      | 25565   | No       | The port of the server. |




# User

## Information

```curl
curl -XGET -H "Content-type: application/json" 'https://mcapi.de/api/user/profile/Yonas'
```

> The above command returns JSON structured like this:

```json
{
  "meta": {
    "status": 200,
    "message": "Ok"
  },
  "data": {
    "premium": true,
    "uuid": "c3ba4b04764c4c9985ac506220806e54",
    "username": "Yonas",
    "history": [
      {
        "name": "MineNotchCrafter"
      },
      {
        "name": "Yonas",
        "changedToAt": 1423071780000
      }
    ],
    "properties": {
      "decoded": [
        {
          "name": "textures",
          "value": {
            "timestamp": 1517258990662,
            "profileId": "c3ba4b04764c4c9985ac506220806e54",
            "profileName": "Yonas",
            "signatureRequired": true,
            "textures": {
              "SKIN": {
                "url": "http://textures.minecraft.net/texture/f1b58d6787ede3dadabbd7abeebf59ae917a8179c95e5b84be9ff96ebc1dcf56"
              }
            }
          }
        }
      ],
      "raw": [
        {
          "name": "textures",
          "value": "eyJ0aW1lc3RhbXAiOjE1MTcyNTg5OTA2NjIsInByb2ZpbGVJZCI6ImMzYmE0YjA0NzY0YzRjOTk4NWFjNTA2MjIwODA2ZTU0IiwicHJvZmlsZU5hbWUiOiJZb25hcyIsInNpZ25hdHVyZVJlcXVpcmVkIjp0cnVlLCJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvZjFiNThkNjc4N2VkZTNkYWRhYmJkN2FiZWViZjU5YWU5MTdhODE3OWM5NWU1Yjg0YmU5ZmY5NmViYzFkY2Y1NiJ9fX0=",
          "signature": "ZLyKRgkjykLYlIEoB8crh+mxRBWCKyKHxfBuxFQ748BeSdomIP/obmx5sIFUgwrpjL1mmUG0nrL4fh8ihoDjKKpP29Hx+oSXuNq4ea58RQfxZUEnkyRpK+n6GRrdYOzs6HxIWf+PkN/vPkmrD2imXMK+TU0xw5DhdvaxVn2dBuEyxTnwYSrCXqWvEdNdCkdh8CuA481VyXqx1d/wQh2wqXE/aaRaogvnrQmTaBmHAnJhjnBGnAm1yFO13DW7v4Mi2TBRKRbz7ToihiLT4+eZAmnPlFnVMiJ6eleHBdsJM9gClmUSC6rxvJEVuv8GkKvFuRoeV6tRNoQEvkUnU//1DQZsnuWhhsn+yf7Vrz8OozVS5u/ldwnjPS8vZYhiwE75gyBVSmXtxuN0TG1CaMMFJmvTfR972J/FCBx+AeVRQVr2eTMMCagBlcy/0mgS1pfCdhk36SgUozl8LEs0i6z+d9DOh1oRu0mEMq7Bsp2+F0xUpp2ZFuya8FFPj+obvGfTr7/Imp9ltRVBSTSGIbEx+dcwgk1WMIXoYqEDwIhSiwSpuKdhEAWQpAz+Ky/MQ82uFa/G3tl5CMX2ZenCelJFsK+E+5M2bV2IKnyZRrdiAE2cjEUN3yU0zzKRWCUi9z4Pc1sxJUOLjQq3uzQcmpVyvhmQ4Ayv5d1dvJD6PMqxy08="
        }
      ]
    }
  },
  "cache": {
    "stored": true,
    "updated": {
      "date": "2018-03-08 09:17:41.000000",
      "timezone_type": 3,
      "timezone": "UTC"
    },
    "expires": {
      "date": "2018-03-08 09:47:41.000000",
      "timezone_type": 3,
      "timezone": "UTC"
    }
  }
}
```


### HTTP Request

`GET https://mcapi.de/api/user/profile/{identifier}`

### Query Parameters

Parameter | Default | Required | Description |
--------- | ------- | -------- | ----------- |
identifier| -       | Yes      | The username or the UUIDv4 with or without '-' of the account. |


## Reputation

```curl
curl -XGET -H "Content-type: application/json" 'https://mcapi.de/api/user/reputation/Notch'
```

> The above command returns JSON structured like this:

```json
{
  "meta": {
    "status": 200,
    "message": "Ok"
  },
  "data": {
    "services": {
      "glizer": {
        "servers": []
      },
      "mcbouncer": {
        "servers": [
          {
            "name": "play.pixelhype.net",
            "reason": "Why would you even come on this server?"
          },
          [...]
        ]
      }
    }
  },
  "cache": {
    "stored": true,
    "updated": {
      "date": "2018-03-08 09:53:47.412585",
      "timezone_type": 3,
      "timezone": "UTC"
    },
    "expires": {
      "date": "2018-03-09 09:53:47.413221",
      "timezone_type": 3,
      "timezone": "UTC"
    }
  }
}
```


### HTTP Request

`GET https://mcapi.de/api/user/reputation/{identifier}`

### Query Parameters

Parameter | Default | Required | Description |
--------- | ------- | -------- | ----------- |
identifier| -       | Yes      | The username or the UUIDv4 with or without '-' of the account. |





# Game

## Versions

```curl
curl -XGET -H "Content-type: application/json" 'https://mcapi.de/api/game/versions'
```

> The above command returns JSON structured like this:

```json
{
  "meta": {
    "status": 200,
    "message": "Ok"
  },
  "data": {
    "latest": {
      "snapshot": "18w10a",
      "release": "1.12.2"
    },
    "versions": [
      {
        "id": "18w10a",
        "type": "snapshot",
        "time": "2018-03-06T16:10:50+00:00",
        "releaseTime": "2018-03-06T15:54:24+00:00",
        "url": "https://launchermeta.mojang.com/mc/game/d380f1622067fa0d15a4ae2cce913901196bdda9/18w10a.json"
      },
      [...]
      {
        "id": "rd-132211",
        "type": "old_alpha",
        "time": "2016-02-02T15:37:47+00:00",
        "releaseTime": "2009-05-13T20:11:00+00:00",
        "url": "https://launchermeta.mojang.com/mc/game/959b97fce81f043fe846fb134770a727fbeb9245/rd-132211.json"
      }
    ]
  },
  "cache": {
    "stored": true,
    "updated": {
      "date": "2018-03-07 10:06:10.587723",
      "timezone_type": 3,
      "timezone": "UTC"
    },
    "expires": {
      "date": "2018-03-08 10:06:10.588603",
      "timezone_type": 3,
      "timezone": "UTC"
    }
  }
}
```


### HTTP Request

`GET https://mcapi.de/api/game/versions`

### Query Parameters

Parameter | Default | Required | Description |
--------- | ------- | -------- | ----------- |


## Version Run

```curl
curl -XGET -H "Content-type: application/json" 'https://mcapi.de/api/game/versions/run/1.12.2'
```

> The above command returns JSON structured like this:

```json
{
  "meta": {
    "status": 200,
    "message": "Ok"
  },
  "data": {
    "assetIndex": {
      "id": "1.12",
      "sha1": "98c430c16a705f18a58a281b27caabf3ef09d40d",
      "size": 169253,
      "url": "https://launchermeta.mojang.com/mc/assets/1.12/98c430c16a705f18a58a281b27caabf3ef09d40d/1.12.json",
      "totalSize": 127453671
    },
    "assets": "1.12",
    "downloads": {
      [..]
    },
    "id": "1.12.2",
    "libraries": [
        [...]
    ],
    "logging": {
      [...]
    },
    "mainClass": "net.minecraft.client.main.Main",
    "minecraftArguments": "--username ${auth_player_name} --version ${version_name} --gameDir ${game_directory} --assetsDir ${assets_root} --assetIndex ${assets_index_name} --uuid ${auth_uuid} --accessToken ${auth_access_token} --userType ${user_type} --versionType ${version_type}",
    "minimumLauncherVersion": 18,
    "releaseTime": "2017-09-18T08:39:46+00:00",
    "time": "2018-02-15T16:26:45+00:00",
    "type": "release"
  },
  "cache": {
    "stored": true,
    "updated": {
      "date": "2018-03-08 10:04:00.075337",
      "timezone_type": 3,
      "timezone": "UTC"
    },
    "expires": {
      "date": "2018-03-09 10:04:00.075722",
      "timezone_type": 3,
      "timezone": "UTC"
    }
  }
}
```


### HTTP Request

`GET https://mcapi.de/api/game/run/{version}`

### Query Parameters

Parameter | Default | Required | Description |
--------- | ------- | -------- | ----------- |
version   | -       | Yes      | The Minecraft version you wanna know more about. |


## Services

```curl
curl -XGET -H "Content-type: application/json" 'https://mcapi.de/api/user/status'
```

> The above command returns JSON structured like this:

```json
{
  "meta": {
    "status": 200,
    "message": "Ok"
  },
  "data": [
    {
      "service": "minecraft.net",
      "status": 200
    },
    {
      "service": "skins.minecraft.net",
      "status": 200
    },
    {
      "service": "textures.minecraft.net",
      "status": 200
    },
    {
      "service": "account.mojang.com",
      "status": 200
    },
    {
      "service": "auth.mojang.com",
      "status": 200
    },
    {
      "service": "authserver.mojang.com",
      "status": 200
    },
    {
      "service": "sessionserver.mojang.com",
      "status": 200
    },
    {
      "service": "api.mojang.com",
      "status": 200
    }
  ],
  "cache": {
    "stored": false,
    "updated": {
      "date": "2018-03-08 22:15:37.069056",
      "timezone_type": 3,
      "timezone": "UTC"
    },
    "expires": {
      "date": "2018-03-08 22:15:37.069056",
      "timezone_type": 3,
      "timezone": "UTC"
    }
  }
}
```


### HTTP Request

`GET https://mcapi.de/api/game/services/status`

### Query Parameters

Parameter | Default | Required | Description |
--------- | ------- | -------- | ----------- |


## Service Status

```curl
curl -XGET -H "Content-type: application/json" 'https://mcapi.de/api/services/status/minecraft.net'
```

> The above command returns JSON structured like this:

```json
{
  "meta": {
    "status": 200,
    "message": "Ok"
  },
  "data": {
    "service": "minecraft.net",
    "status": 200
  },
  "cache": {
    "stored": true,
    "updated": {
      "date": "2018-03-08 10:07:50.000000",
      "timezone_type": 3,
      "timezone": "UTC"
    },
    "expires": {
      "date": "2018-03-08 10:12:50.000000",
      "timezone_type": 3,
      "timezone": "UTC"
    }
  }
}
```


### HTTP Request

`GET https://mcapi.de/api/game/services/status/{service}`

### Query Parameters

Parameter | Default | Required | Description |
--------- | ------- | -------- | ----------- |
services  | -       | Yes      | The service you want to know the status of.

# Votifier

## NuVotifier

```curl
curl -XGET -H "Content-type: application/json" 'https://mcapi.de/api/voting/nu/192.168.2.70/8192/Yonas/f[...]u/M[...]B'
```

> The above command returns JSON structured like this:

```json
{
  "meta": {
    "status": 200,
    "message": "Ok"
  },
  "data": {
    "host": "192.168.2.70",
    "port": 8192,
    "response": "ok"
  },
  "cache": {
    "stored": false,
    "updated": {
      "date": "2018-03-09 09:16:07.001891",
      "timezone_type": 3,
      "timezone": "UTC"
    },
    "expires": {
      "date": "2018-03-09 09:16:07.001891",
      "timezone_type": 3,
      "timezone": "UTC"
    }
  }
}
```


### HTTP Request

`GET https://mcapi.de/api/voting/nu/{ip}/{port}/{identifier}/{token}/{publicKey}`

### Query Parameters

Parameter | Default | Required | Description |
--------- | ------- | -------- | ----------- |
host      | -       | Yes      | The host or IPv4/IPv6 address of the server. |
port      | 25565   | No       | The port of the server. |
identifier| -       | Yes      | The username of the voter. |
token     | -       | Yes      | The token that exists in the config.yml of the NuVotifier plugin. |
publicKey | -       | Yes      | Your public RSA key to encrypt the vote.   |


# Image

## Favicon

```curl
curl -XGET -H "Content-type: image/png" 'https://mcapi.de/api/image/favicon/play.hivemc.eu'
```

> <img src="images/favicon_example.png" alt="Favicon Example"/>



### HTTP Request

`GET https://mcapi.de/api/image/favicon/{host}[/{port}]`

### Query Parameters

Parameter | Default | Required | Description |
--------- | ------- | -------- | ----------- |
host      | -       | Yes      | The host or IPv4/IPv6 address of the server. |
port      | 25565   | No       | The port of the server. |
