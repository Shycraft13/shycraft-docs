# `economy/tags/gui/main.yml`

Location: `plugins/EconomyCore/economy/tags/gui/main.yml`

```yaml

gui:
  title: "&8ᴛᴀɢѕ"

  rows: 5

  items-per-page: 36

prev-page:
  SLOT: 36
  MATERIAL: ARROW
  TITLE: "&#FC0000&lPREVIOUS PAGE"
  LORE:
    - "&7Navigation"
    - ""
    - "&#FC0000Information"
    - "&fGo back one page."
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Go Back"

close:
  MATERIAL: RED_STAINED_GLASS_PANE
  TITLE: "&#FC0000&lCLOSE"
  LORE:
    - "&7Navigation"
    - ""
    - "&#FC0000Information"
    - "&fClose this menu."
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Close"

sort:
  SLOT: 39
  MATERIAL: HOPPER
  TITLE: "&#FCE300&lSORTING"
  LORE-HEADER:
    - "&7Tag Order"
    - ""
    - "&7Current Selection"
  ACTIVE-PREFIX: "&#FCE300▶ &f"
  INACTIVE-PREFIX: "&7▶ &f"
  LORE-FOOTER:
    - ""
    - "&#FCE300▶ &#FCE300&l&nCLICK&r &#FCE300to Change"

  MODES:
    OWNED: "Owned First"
    A_Z:   "A-Z"
    Z_A:   "Z-A"

clear:
  SLOT: 40
  MATERIAL: CHEST_MINECART
  TITLE: "&#FC0000&lCLEAR TAG"
  NONE: "&7None"
  LORE:
    - "&7Action"
    - ""
    - "&#FC0000Information"
    - "&fEquipped: %tag%"
    - "&fRemove the tag behind"
    - "&fyour name."
    - ""
    - "&#FC0000▶ &#FC0000&l&nCLICK&r &#FC0000to Clear"

search:
  SLOT: 41
  MATERIAL: OAK_SIGN
  TITLE: "&#00A4FC&lSEARCH"
  LORE:
    - "&7Tag Search"
    - ""
    - "&#00A4FCInformation"
    - "&fSearch for a tag"
    - "&fby name."
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Search"

search-active:
  MATERIAL: OAK_SIGN
  TITLE: "&#00FC99&lSEARCH"
  LORE:
    - "&7Tag Search"
    - ""
    - "&#00FC99Information"
    - "&fFiltering: &#00FC99%query%&f."
    - "&fType empty to clear."
    - ""
    - "&#00FC99▶ &#00FC99&l&nCLICK&r &#00FC99to Search Again"

next-page:
  SLOT: 44
  MATERIAL: ARROW
  TITLE: "&#00FC00&lNEXT PAGE"
  LORE:
    - "&7Navigation"
    - ""
    - "&#00FC00Information"
    - "&fGo forward one page."
    - ""
    - "&#00FC00▶ &#00FC00&l&nCLICK&r &#00FC00to Go Forward"

entry:
  TITLE: "%tag%"
  LORE-EQUIPPED:
    - "&7Tag"
    - ""
    - "&#00FC00Information"
    - "&fThis tag is equipped."
    - ""
    - "&#00FC00▶ &#00FC00&l&nEQUIPPED"
  LORE-OWNED:
    - "&7Tag"
    - ""
    - "&#00A4FCInformation"
    - "&fYou own this tag."
    - ""
    - "&#00A4FC▶ &#00A4FC&l&nCLICK&r &#00A4FCto Equip"
  LORE-LOCKED:
    - "&7Tag"
    - ""
    - "&#FC0000Information"
    - "&fYou do not own this tag."
    - "&fUnlock it on the store"
    - "&for with a rank."
    - ""
    - "&#FC0000▶ &#FC0000&l&nLOCKED"

FILLER:
  MATERIAL: AIR
  TITLE: " "
  LORE: []
```
