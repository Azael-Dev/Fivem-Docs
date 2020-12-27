---
title: การตั้งค่าทรัพยากร
weight: 220
description: >
  คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีการตั้งค่า
---

## การตั้งค่าฝั่ง Server

สามารถตั้งค่าได้ที่ไฟล์ `config.server.lua`

### `script_token`

ตัวระบุ API เพื่อใช้ในการตรวจสอบสิทธิ์การใช้งานของทรัพยากร ดูได้ที่ [สินค้าที่ซื้อ](https://fivem.azael.dev/dashboard/digishop)

```lua
Config['script_token'] = 'Token Key'
```

### `esx_routers`

เส้นทางกิจกรรมของทรัพยากร ESX Framework หาก es_extended เซิร์ฟเวอร์ของคุณ มีการแก้ไขชื่อกิจกรรมของทรัพยากร เพื่อป้องกันโปรแกรมโกงต่างๆ

```lua
Config['esx_routers'] = {
	['server_shared_obj'] = 'esx:getSharedObject',
	['server_player_load'] = 'esx:playerLoaded'
}	
```

{{% alert theme="info" %}}
ห้ามแก้ไขการตั้งค่าในส่วนนี้โดยเด็ดขาด หากคุณไม่เข้าใจว่าสิ่งนี้คืออะไร เพราะอาจจะทำให้ทรัพยากรเกิดข้อผิดพลาดได้
{{% /alert %}}

### `event_name`

ชื่อเหตุการณ์ทริกเกอร์ (Trigger) เพื่อรับกิจกรรมต่างๆจากทรัพยากรภายนอก

```lua
Config['event_name'] = 'azael_discordlogs:sendToDiscord'
```

### `webhook_image`

รูปโปรไฟล์ของ Discord Webhook

```lua
Config['webhook_image'] = 'https://i.imgur.com/GxQpZzJ.png'
```

{{% alert theme="info" %}}
แนะนำเว็บไซต์ฝากรูป https://imgur.com
{{% /alert %}}

### `color`

แถบสีของกล่องข้อความที่เเสดงภายในกลุ่ม Discord

```lua
Config['color'] = {
	['^0'] = 16777215,										-- White #ffffff
	['^1'] = 16729156,										-- Light Red #ff4444
	['^2'] = 10079232,										-- Strong Green #99cc00
	['^3'] = 16759603,										-- Vivid Orange #ffbb33
	['^4'] = 39372,											-- Strong Blue #0099cc
	['^5'] = 3388901,										-- Bright Blue #33b5e5
	['^6'] = 11167436,										-- Moderate Violet #aa66cc
	['^7'] = 10070709,										-- Grayish Blue #99aab5
	['^8'] = 13369344,										-- Strong Red #cc0000
	['^9'] = 13369448										-- Strong Pink #cc0068
}
```

{{% alert theme="info" %}}
ดูรหัสสี Decimal ได้ที่ https://convertingcolors.com
{{% /alert %}}

### `webhook`

ชื่อของกิจกรรม (Event) และ ลิกค์ Webhook เพื่อใช้ในการส่งข้อความไปยังห้องภายในกลุ่ม Discord ที่กำหนด

```lua
Config['webhook'] = {
	['Login'] = 'Webhook URL - Login',						-- เชื่อมต่อกับเซิร์ฟเวอร์
	['Logout'] = 'Webhook URL - Logout',					-- ตัดการเชื่อมต่อเซิร์ฟเวอร์
	['Chat'] = 'Webhook URL - Chat',						-- ข้อความแชท
	['Dead'] = 'Webhook URL - Dead'							-- สาเหตุการเสียชีวิต
}
```

{{% alert theme="info" %}}
บรรทัดสุดท้ายจะต้องไม่มีเครื่องหมาย <kbd>,</kbd> เพราะอาจจะทำให้ทรัพยากรเกิดข้อผิดพลาดได้
{{% /alert %}}

## การตั้งค่าฝั่ง Client

สามารถตั้งค่าได้ที่ไฟล์ `config.client.lua`

### `esx_routers`

เส้นทางกิจกรรมของทรัพยากร ESX Framework หาก es_extended เซิร์ฟเวอร์ของคุณ มีการแก้ไขชื่อกิจกรรมของทรัพยากร เพื่อป้องกันโปรแกรมโกงต่างๆ

```lua
Config['esx_routers'] = {
	['client_shared_obj'] = 'esx:getSharedObject'
}
```

{{% alert theme="info" %}}
ห้ามแก้ไขการตั้งค่าในส่วนนี้โดยเด็ดขาด หากคุณไม่เข้าใจว่าสิ่งนี้คืออะไร เพราะอาจจะทำให้ทรัพยากรเกิดข้อผิดพลาดได้
{{% /alert %}}

### `event`

การกำหนดค่าต่างๆ สำหรับสาเหตุการเสียชีวิต

```lua
Config['event'] = {
    {
        ['type'] = 'Melee',                                 -- ระยะประชิด
        ['list'] = {
            {
                ['name'] = 'WEAPON_DAGGER',
                ['label'] = 'Antique Cavalry Dagger'
            },

            {
                ['name'] = 'WEAPON_BAT',
                ['label'] = 'Baseball Bat'
            },

            {
                ['name'] = 'WEAPON_BOTTLE',
                ['label'] = 'Broken Bottle'
            },

            {
                ['name'] = 'WEAPON_CROWBAR',
                ['label'] = 'Crowbar'
            },

            {
                ['name'] = 'WEAPON_UNARMED',
                ['label'] = 'Fist'
            },

            {
                ['name'] = 'WEAPON_FLASHLIGHT',
                ['label'] = 'Flashlight'
            },

            {
                ['name'] = 'WEAPON_GOLFCLUB',
                ['label'] = 'Golf Club'
            },

            {
                ['name'] = 'WEAPON_HAMMER',
                ['label'] = 'Hammer'
            },

            {
                ['name'] = 'WEAPON_HATCHET',
                ['label'] = 'Hatchet'
            },

            {
                ['name'] = 'WEAPON_KNUCKLE',
                ['label'] = 'Brass Knuckles'
            },

            {
                ['name'] = 'WEAPON_KNIFE',
                ['label'] = 'Knife'
            },

            {
                ['name'] = 'WEAPON_MACHETE',
                ['label'] = 'Machete'
            },

            {
                ['name'] = 'WEAPON_SWITCHBLADE',
                ['label'] = 'Switchblade'
            },

            {
                ['name'] = 'WEAPON_NIGHTSTICK',
                ['label'] = 'Nightstick'
            },

            {
                ['name'] = 'WEAPON_WRENCH',
                ['label'] = 'Pipe Wrench'
            },

            {
                ['name'] = 'WEAPON_BATTLEAXE',
                ['label'] = 'Battle Axe'
            },

            {
                ['name'] = 'WEAPON_POOLCUE',
                ['label'] = 'Pool Cue'
            },

            {
                ['name'] = 'WEAPON_STONE_HATCHET',
                ['label'] = 'Stone Hatchet'
            }
        }
    },

    {
        ['type'] = 'Bullet',                                 -- กระสุน
        ['list'] = {
            {
                ['name'] = 'WEAPON_PISTOL',
                ['label'] = 'Pistol'
            },

            {
                ['name'] = 'WEAPON_PISTOL_MK2',
                ['label'] = 'Pistol Mk II'
            },

            {
                ['name'] = 'WEAPON_COMBATPISTOL',
                ['label'] = 'Combat Pistol'
            },

            {
                ['name'] = 'WEAPON_APPISTOL',
                ['label'] = 'AP Pistol'
            },

            {
                ['name'] = 'WEAPON_STUNGUN',
                ['label'] = 'Stun Gun'
            },

            {
                ['name'] = 'WEAPON_PISTOL50',
                ['label'] = 'Pistol .50'
            },

            {
                ['name'] = 'WEAPON_SNSPISTOL',
                ['label'] = 'SNS Pistol'
            },

            {
                ['name'] = 'WEAPON_SNSPISTOL_MK2',
                ['label'] = 'SNS Pistol Mk II'
            },

            {
                ['name'] = 'WEAPON_HEAVYPISTOL',
                ['label'] = 'Heavy Pistol'
            },

            {
                ['name'] = 'WEAPON_VINTAGEPISTOL',
                ['label'] = 'Vintage Pistol'
            },

            {
                ['name'] = 'WEAPON_FLAREGUN',
                ['label'] = 'Flare Gun'
            },

            {
                ['name'] = 'WEAPON_MARKSMANPISTOL',
                ['label'] = 'Marksman Pistol'
            },

            {
                ['name'] = 'WEAPON_REVOLVER',
                ['label'] = 'Heavy Revolver'
            },

            {
                ['name'] = 'WEAPON_REVOLVER_MK2',
                ['label'] = 'Heavy Revolver Mk II'
            },

            {
                ['name'] = 'WEAPON_DOUBLEACTION',
                ['label'] = 'Double Action Revolver'
            },

            {
                ['name'] = 'WEAPON_RAYPISTOL',
                ['label'] = 'Up-n-Atomizer'
            },

            {
                ['name'] = 'WEAPON_CERAMICPISTOL',
                ['label'] = 'Ceramic Pistol'
            },

            {
                ['name'] = 'WEAPON_NAVYREVOLVER',
                ['label'] = 'Navy Revolver'
            },

            {
                ['name'] = 'WEAPON_MICROSMG',
                ['label'] = 'Micro SMG'
            },

            {
                ['name'] = 'WEAPON_SMG',
                ['label'] = 'SMG'
            },

            {
                ['name'] = 'WEAPON_SMG_MK2',
                ['label'] = 'SMG Mk II'
            },

            {
                ['name'] = 'WEAPON_ASSAULTSMG',
                ['label'] = 'Assault SMG'
            },

            {
                ['name'] = 'WEAPON_COMBATPDW',
                ['label'] = 'Combat PDW'
            },

            {
                ['name'] = 'WEAPON_MACHINEPISTOL',
                ['label'] = 'Machine Pistol'
            },

            {
                ['name'] = 'WEAPON_MINISMG',
                ['label'] = 'Mini SMG'
            },

            {
                ['name'] = 'WEAPON_RAYCARBINE',
                ['label'] = 'Unholy Hellbringer'
            },

            {
                ['name'] = 'WEAPON_PUMPSHOTGUN',
                ['label'] = 'Pump Shotgun'
            },

            {
                ['name'] = 'WEAPON_PUMPSHOTGUN_MK2',
                ['label'] = 'Pump Shotgun Mk II'
            },

            {
                ['name'] = 'WEAPON_SAWNOFFSHOTGUN',
                ['label'] = 'Sawed-Off Shotgun'
            },

            {
                ['name'] = 'WEAPON_ASSAULTSHOTGUN',
                ['label'] = 'Assault Shotgun'
            },

            {
                ['name'] = 'WEAPON_BULLPUPSHOTGUN',
                ['label'] = 'Bullpup Shotgun'
            },

            {
                ['name'] = 'WEAPON_MUSKET',
                ['label'] = 'Musket'
            },

            {
                ['name'] = 'WEAPON_HEAVYSHOTGUN',
                ['label'] = 'Heavy Shotgun'
            },

            {
                ['name'] = 'WEAPON_DBSHOTGUN',
                ['label'] = 'Double Barrel Shotgun'
            },

            {
                ['name'] = 'WEAPON_AUTOSHOTGUN',
                ['label'] = 'Sweeper Shotgun'
            },

            {
                ['name'] = 'WEAPON_ASSAULTRIFLE',
                ['label'] = 'Assault Rifle'
            },

            {
                ['name'] = 'WEAPON_ASSAULTRIFLE_MK2',
                ['label'] = 'Assault Rifle Mk II'
            },

            {
                ['name'] = 'WEAPON_CARBINERIFLE',
                ['label'] = 'Carbine Rifle'
            },

            {
                ['name'] = 'WEAPON_CARBINERIFLE_MK2',
                ['label'] = 'Carbine Rifle Mk II'
            },

            {
                ['name'] = 'WEAPON_ADVANCEDRIFLE',
                ['label'] = 'Advanced Rifle'
            },

            {
                ['name'] = 'WEAPON_SPECIALCARBINE',
                ['label'] = 'Special Carbine'
            },

            {
                ['name'] = 'WEAPON_SPECIALCARBINE_MK2',
                ['label'] = 'Special Carbine Mk II'
            },

            {
                ['name'] = 'weapon_bullpuprifle',
                ['label'] = 'Bullpup Rifle'
            },

            {
                ['name'] = 'WEAPON_BULLPUPRIFLE_MK2',
                ['label'] = 'Bullpup Rifle Mk II'
            },

            {
                ['name'] = 'WEAPON_COMPACTRIFLE',
                ['label'] = 'Compact Rifle'
            },

            {
                ['name'] = 'WEAPON_MG',
                ['label'] = 'MG'
            },

            {
                ['name'] = 'WEAPON_COMBATMG',
                ['label'] = 'Combat MG'
            },

            {
                ['name'] = 'WEAPON_COMBATMG_MK2',
                ['label'] = 'Combat MG Mk II'
            },

            {
                ['name'] = 'WEAPON_GUSENBERG',
                ['label'] = 'Gusenberg Sweeper'
            },

            {
                ['name'] = 'WEAPON_SNIPERRIFLE',
                ['label'] = 'Sniper Rifle'
            },

            {
                ['name'] = 'WEAPON_HEAVYSNIPER',
                ['label'] = 'Heavy Sniper'
            },

            {
                ['name'] = 'WEAPON_HEAVYSNIPER_MK2',
                ['label'] = 'Heavy Sniper Mk II'
            },

            {
                ['name'] = 'WEAPON_MARKSMANRIFLE',
                ['label'] = 'Marksman Rifle'
            },

            {
                ['name'] = 'WEAPON_MARKSMANRIFLE_MK2',
                ['label'] = 'Marksman Rifle Mk II'
            },

            {
                ['name'] = 'WEAPON_MINIGUN',
                ['label'] = 'Minigun'
            }
        }
    },

    {
        ['type'] = 'Explosion',                                 -- แรงระเบิด
        ['list'] = {
            {
                ['name'] = 'WEAPON_RPG',
                ['label'] = 'RPG'
            },

            {
                ['name'] = 'WEAPON_GRENADELAUNCHER',
                ['label'] = 'Grenade Launcher'
            },

            {
                ['name'] = 'WEAPON_GRENADELAUNCHER_SMOKE',
                ['label'] = 'Grenade Launcher Smoke'
            },

            {
                ['name'] = 'WEAPON_RAILGUN',
                ['label'] = 'Railgun'
            },

            {
                ['name'] = 'WEAPON_HOMINGLAUNCHER',
                ['label'] = 'Homing Launcher'
            },

            {
                ['name'] = 'WEAPON_COMPACTLAUNCHER',
                ['label'] = 'Compact Grenade'
            },

            {
                ['name'] = 'WEAPON_RAYMINIGUN',
                ['label'] = 'Widowmaker'
            },

            {
                ['name'] = 'WEAPON_PASSENGER_ROCKET',
                ['label'] = 'Passenger Rocket'
            },

            {
                ['name'] = 'WEAPON_AIRSTRIKE_ROCKET',
                ['label'] = 'Airstrike Rocket'
            },

            {
                ['name'] = 'WEAPON_STINGER',
                ['label'] = 'Stinger [Vehicle]'
            },

            {
                ['name'] = 'WEAPON_GRENADE',
                ['label'] = 'Grenade'
            },

            {
                ['name'] = 'WEAPON_STICKYBOMB',
                ['label'] = 'Sticky Bomb'
            },

            {
                ['name'] = 'WEAPON_SMOKEGRENADE',
                ['label'] = 'Tear Gas'
            },

            {
                ['name'] = 'WEAPON_EXPLOSION',
                ['label'] = 'Explosion'
            },

            {
                ['name'] = 'WEAPON_HELI_CRASH',
                ['label'] = 'Heli Crash'
            },

            {
                ['name'] = 'WEAPON_VEHICLE_ROCKET',
                ['label'] = 'Vehicle Rocket'
            },

            {
                ['name'] = 'WEAPON_PROXMINE',
                ['label'] = 'Proximity Mines'
            },

            {
                ['name'] = 'WEAPON_PIPEBOMB',
                ['label'] = 'Pipe Bombs'
            }
        }
    },

    {
        ['type'] = 'Gas',                                  -- แก๊สพิษ
        ['list'] = {
            {
                ['name'] = 'WEAPON_BZGAS',
                ['label'] = 'BZ Gas'
            }
        }
    },

    {
        ['type'] = 'Car',                                  -- ยานพาหนะ
        ['list'] = {
            {
                ['name'] = 'WEAPON_RAMMED_BY_CAR',
                ['label'] = 'ยานพาหนะ'
            },

            {
                ['name'] = 'WEAPON_RUN_OVER_BY_CAR',
                ['label'] = 'ยานพาหนะ'
            }
        }
    },

    {
        ['type'] = 'Animal',                                -- สัตว์
        ['list'] = {
            {
                ['name'] = 'WEAPON_ANIMAL',
                ['label'] = 'สัตว์ทำร้าย'
            },

            {
                ['name'] = 'WEAPON_COUGAR',
                ['label'] = 'เสือภูเขาทำร้าย'
            }
        }
    },

    {
        ['type'] = 'FallDamage',                             -- ตกจากที่สูง
        ['list'] = {
            {
                ['name'] = 'WEAPON_FALL',
                ['label'] = 'ตกจากที่สูง หรือ ขาดอาหาร'
            }
        }
    },

    {
        ['type'] = 'Burn',                                   -- เผา
        ['list'] = {
            {
                ['name'] = 'WEAPON_MOLOTOV',
                ['label'] = 'Molotov Cocktail'
            },

            {
                ['name'] = 'WEAPON_PETROLCAN',
                ['label'] = 'Jerry Can'
            },

            {
                ['name'] = 'WEAPON_FIREWORK',
                ['label'] = 'Firework Launcher'
            }
        }
    },

    {
        ['type'] = 'Drown',                                 -- จมน้ำ
        ['list'] = {
            {
                ['name'] = 'WEAPON_DROWNING',
                ['label'] = 'จมน้ำ'
            },

            {
                ['name'] = 'WEAPON_DROWNING_IN_VEHICLE',
                ['label'] = 'จมน้ำภายในยานพาหนะ'
            }
        }
    }
}
```