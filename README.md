<div align="center">

# sd-tablet-props

**Streamed in-hand tablet props for [sd-tablet](https://github.com/Samuels-Development/sd-tablet), one model per frame colour.**

[**sd-tablet**](https://github.com/Samuels-Development/sd-tablet) · [**Documentation**](https://docs.samueldev.shop/resources/tablet/) · [**Discord**](https://discord.gg/FzPehMQaBQ)

</div>

---

Streams the `sd_tablet_<colour>` drawables (black, blue, green, orange, pink, purple, red, yellow) that sd-tablet attaches to the player's hand while the tablet is out. The prop colour matches the tablet item the player used.

## Installation

```cfg
ensure sd-tablet-props
ensure sd-tablet
```

No configuration. sd-tablet resolves the prop names automatically; without this resource the tablet still works, players just hold nothing visible.

## Models

`sd_tablet_black` `sd_tablet_blue` `sd_tablet_green` `sd_tablet_orange`
`sd_tablet_pink` `sd_tablet_purple` `sd_tablet_red` `sd_tablet_yellow`

Textures are embedded in each `.ydr`, so there are no `.ytd` files to manage. Each drawable is 8,070 triangles at real-world scale (177.7 x 249.9 x 8.9 mm) with the origin at the geometry centre, a `METAL_SOLID_SMALL` box bound embedded in the drawable, and an emissive screen. Archetypes are declared in `stream/sd_tablet.ytyp` at `lodDist` 100.

## Credits

Tablet models by **Samuels Development**.
