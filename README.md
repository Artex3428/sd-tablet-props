<div align="center">

# sd-tablet-props

**Streamed in-hand tablet props for [sd-tablet](https://github.com/Samuels-Development/sd-tablet), one model per frame colour.**

### This branch is for GTA V LEGACY

[![Enhanced build](https://img.shields.io/badge/On%20GTA%20V%20Enhanced%3F-get%20the%20enhanced%20branch-9EEADD?style=for-the-badge)](https://github.com/Samuels-Development/sd-tablet-props/tree/enhanced)

[**sd-tablet**](https://github.com/Samuels-Development/sd-tablet) · [**Documentation**](https://docs.samueldev.shop/resources/tablet/) · [**Discord**](https://discord.gg/FzPehMQaBQ)

</div>

---

Streams the `sd_tablet_<colour>` drawables (black, blue, green, orange, pink, purple, red, yellow) that sd-tablet attaches to the player's hand while the tablet is out. The prop colour matches the tablet item the player used.

## Preview
<img width="1500" height="1500" alt="image" src="https://github.com/user-attachments/assets/b1f9f9ec-db57-4690-b4a9-c01cf6854b66" />

<img width="1500" height="1500" alt="v10_pinwheel" src="https://github.com/user-attachments/assets/18c7d631-62c7-4a31-b5aa-15d4a054bf5a" />

## Which branch do I want

| Branch | Game build |
|---|---|
| `main` (you are here) | GTA V **Legacy** |
| [`enhanced`](https://github.com/Samuels-Development/sd-tablet-props/tree/enhanced) | GTA V **Enhanced** |

The two carry the same models. Only the asset format differs: the drawables and the `.ytyp` on the `enhanced` branch have been run through CFX's Alchemist, which rewrites them into the format the Enhanced build loads. Everything else, the resource name, the manifest, the model names and the dimensions below, is identical, so sd-tablet needs no change either way.

Loading the wrong branch for your build is the usual cause of an invisible or malformed prop.

## Installation

```cfg
ensure sd-tablet-props
ensure sd-tablet
```

No configuration. sd-tablet resolves the prop names automatically; without this resource the tablet still works, players just hold nothing visible.

## Models

`sd_tablet_black` `sd_tablet_blue` `sd_tablet_green` `sd_tablet_orange`
`sd_tablet_pink` `sd_tablet_purple` `sd_tablet_red` `sd_tablet_yellow`

Textures are embedded in each `.ydr`, so there are no `.ytd` files to manage. Each drawable is 8,070 triangles at real-world scale (177.7 x 249.9 x 8.9 mm), with a `METAL_SOLID_SMALL` box bound embedded in the drawable and an emissive screen. Archetypes are declared in `stream/sd_tablet.ytyp` at `lodDist` 100.

## Drop-in for `prop_cs_tablet`

These are built to the same convention as the base-game tablet: origin at the geometry centre, local X across the screen, Y through it, Z up it.

```
prop_cs_tablet    min(-0.0899, -0.0055, -0.1201)  max(0.0899, 0.0055, 0.1201)
sd_tablet_<col>   min(-0.0888, -0.0044, -0.1249)  max(0.0888, 0.0044, 0.1249)
```

So they weld where `prop_cs_tablet` welds. Any clip authored for the vanilla tablet fits these at a zero offset and rotation, with no per-script transform to work out:

```lua
AttachEntityToEntity(obj, ped, GetPedBoneIndex(ped, 60309),
    0.0, 0.0, 0.0, 0.0, 0.0, 0.0, true, true, false, true, 1, true)
```

## Credits

Tablet models by **Samuels Development**.
