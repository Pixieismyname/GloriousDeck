# Glorious Deeds — Card Editor

Browser-based card editor for **Trench Crusade** Glorious Deeds cards. Open `card_editor.html` directly in any modern browser — no server or install required.

Feel free to buy me a coffee if you like it.
https://buymeacoffee.com/pixieal
It is published free and under CC BY-NC-SA

---

## Files

| File | Purpose |
|------|---------|
| `card_editor.html` | The editor — open this |
| `glorious_deeds.csv` | Source data: all deeds with descriptions, bible verses, AI art prompts |
| `image/bg3.jpg` | Card back background texture |
| `image/extracted_image_1.png` | Trench Crusade banner (top of card back) |
| `image/extracted_image_2–7.jpeg` | Objective medallion coins (card back) |
| `fonts/` | Local font files (see Fonts section) |

---

## Using the Editor

### Card Content

- **Deed Title** — card title with +/− font size control (Medusa Gothic)
- **Description** — deed condition text with +/− font size control (MetalGothic)
- **Value** — circled number badge 1–9, top-right (OldNewspaper Types)

### Reward Pips

Toggle reward tags in the bottom bar:

| Pip | Meaning |
|-----|---------|
| 1 VP | Victory Point |
| 1 XP (Elite) | Experience for elite models |
| +1 Glory | Glory reward |
| +1D6 Promo | Promo roll |
| Campaign Only | No VP awarded |
| +2 Glory | Double glory reward |

### Art Image

- Click **"Click to select image"** to upload from disk
- Or paste an image URL
- Art area: **273 × 130 px** on screen
- For print quality (300 DPI): **852 × 406 px** source image

### Actions

- **Print / Save as PDF** — browser print dialog; page auto-sized to 153×104mm, enable background graphics
- **Save as Image (JPG)** — exports at 300 DPI with physical dimensions embedded in JFIF header

---

## Card Layout

```text
┌──────────────────────────────────────────────────┐  ← print sheet (578×393px / 153×104mm)
│░░░░░░░░░░░░░░░░│░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░│  ← diagonal grey bleed (lamination guide)
│░┌────────────┐░│░┌──────────────────────────────┐░│
│░│   FRONT    │░│░│           BACK               │░│
│░│ [title]    │░│░│  [Trench Crusade banner]      │░│
│░│ [art area] │░│░│  [bg texture 40% opacity]    │░│
│░│ [body]     │░│░│  [6 objective coins]         │░│
│░│ [pips]     │░│░│  CC BY-NC-SA                 │░│
│░└────────────┘░│░│  © Trench Crusade...         │░│
│░░░░░░░░░░░░░░░░│░└──────────────────────────────┘░│
└──────────────────────────────────────────────────┘
                 ↑ fold line (black, centred in 16px gap)
```

Each card face: **273 × 377 px** (≈72 × 100mm). 
Cut utside the striped area.
Fold along the black line, glue and press. 
Once glued, cut away the striped area and laminate. Leave a 2mm border of lamination and cut to size

---

## Source Data (CSV)

`glorious_deeds.csv` columns:

| Column | Content |
|--------|---------|
| Scenario | Mission/scenario name |
| Deed Name | Card title |
| Description | Deed condition (body text) |
| Bible Verse | Flavour quote |
| Reference | Scripture reference |
| AI Art Prompt | Ready-to-use prompt for image gen (portrait 2:3, 852×406px) |

---

## Fonts

All fonts loaded via `@font-face` from the `fonts/` folder.

| Font | File | Used for |
|------|------|---------|
| Medusa Gothic | `MedusaGothic-D.otf` | Card title |
| MetalGothic | `MetalGothic-Regular.ttf` | Body text (demo version) |
| OldNewspaper Types | `OldNewspaperTypes.ttf` | Value badge number |


All editor UI uses **Arial**.

Font sources:

- Medusa Gothic: [dafont.com/medusa-gothic.font](https://www.dafont.com/medusa-gothic.font)
- MetalGothic: [dafont.com/metal-gothic.font](https://www.dafont.com/metal-gothic.font)
- OldNewspaper Types [dafont.com/oldnewspapertypes.font]

---

## Tweaking Appearance

### Background darkness (card back)

Find the bg image tag near the top of the SVG back section:

```text
opacity="0.55"   ← lower = more transparent
```

Darken RGB channels via filter:

```text
values="0.5 0 0 0 0  0 0.5 0 0 0  0 0 0.5 0 0  0 0 0 1 0"
         ^R                ^G                ^B
```

Lower R+G to reduce yellow tones.

### Bleed stripe colours

In CSS (two places — screen and print):

```css
background: repeating-linear-gradient(45deg, #b8b8b8, #b8b8b8 4px, #e0e0e0 4px, #e0e0e0 8px);
```

---

## License

**CC BY-NC-SA** — share and adapt for non-commercial use with attribution and same licence.
For personal use only. Print and play with your friends.

© Trench Crusade. All rights reserved by their respective rightsholders.
