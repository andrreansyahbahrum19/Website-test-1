# REPUBBLICA FIGMA HANDOFF & SPECIFICATION GUIDE
**Brand**: Repubblica Architectural Surfaces & Tapware (Canberra, ACT)  
**Contest/Project**: 99designs Architectural eCommerce System  

---

## 1. File & Token Imports

1. **Tokens JSON**: Sudah tersedia file `/public/figma-tokens.json` di root proyek ini.
   - Kamu bisa mengimpor file tersebut langsung menggunakan plugin Figma seperti **Tokens Studio for Figma** atau plugin **Variables Import/Export**.
   - Semua warna (`Oxblood #5C0202`, `Plum-black #2B0E10`, `Paper #F4F2EF`, `Line #DCD6CE`), spasi 4px/8px, radius 2px, dan skala tipografi otomatis terkonversi menjadi Figma Variables & Typography Styles.

---

## 2. Global Frame & Artboard Setup

| Parameter | Value (Desktop) | Value (Mobile 375) |
| :--- | :--- | :--- |
| **Canvas Background** | `#F4F2EF` | `#F4F2EF` |
| **Frame Dimensions** | `1440px` (Width) × `Auto` | `390px` (Width) × `Auto` |
| **Grid Layout** | 12 Columns, Gutter: `24px`, Margin: `80px` (Max Content Width: `1280px`) | 4 Columns, Gutter: `16px`, Margin: `16px` |
| **Borders** | `1px solid #DCD6CE` (Divider Hairline) | `1px solid #DCD6CE` |

---

## 3. Master Component Specifications for Figma Auto-Layout

### Component 1: `btn/primary` (Oxblood Architectural Button)
- **Auto-Layout**: Horizontal, `Hug contents`
- **Padding**: Top/Bottom: `12px`, Left/Right: `24px` (2:1 exact proportion)
- **Corner Radius**: `2px`
- **Fill**: `#5C0202` (Brand Oxblood)
- **Text Layer**: `Suisse Grotesque` or `Plus Jakarta Sans`, SemiBold (600), `12px`, Tracking: `+0.08em`, Color: `#F4F2EF`, UPPERCASE
- **Hover State**: Fill `#7A1A10` (Brick)

### Component 2: `btn/secondary` (1px Outline Button)
- **Auto-Layout**: Horizontal, `Hug contents`
- **Padding**: Top/Bottom: `10px`, Left/Right: `20px`
- **Corner Radius**: `2px`
- **Stroke**: `1px solid #1C1B1B` (Inside)
- **Text Layer**: SemiBold (600), `12px`, Tracking: `+0.06em`, Color: `#1C1B1B`, UPPERCASE

### Component 3: `btn/sample-chip` (Card Quick-Add Sample Chip)
- **Auto-Layout**: Horizontal, Align Center, Gap `6px`
- **Padding**: Top/Bottom: `6px`, Left/Right: `10px`
- **Corner Radius**: `2px`
- **Fill**: `#FBFAF8`
- **Stroke**: `1px solid #DCD6CE`
- **Icon**: `Plus` or `Check` (12px, stroke 1.25)
- **Text**: `+ SAMPLE · $3` (10.5px, Medium, `#1C1B1B`)
- **Active State (In Tray)**: Fill `#5C0202`, Text `#F4F2EF`, Stroke `#5C0202`

### Component 4: `card/product` (4-Column Dense Architectural Card)
- **Auto-Layout**: Vertical, `Fill container` (Width: ~`284px` on 1280 grid)
- **Fill**: `#FBFAF8`
- **Stroke**: `1px solid #DCD6CE`
- **Radius**: `0px` or `2px`
- **Children Structure**:
  1. `Frame / Image-Container`: Ratio `1:1` (Aspect Square), Fill `#EFECE6`, Clip Content `true`
     - Badge Top-Left: `[IN STOCK: SYD/CBR]` (Pill/Tag, Fill `#FBFAF8`, Text `#3F6B4A`, 9.5px)
     - Overlay Top-Right: Quick View Icon Button (`28x28px`)
     - Swatch Row Bottom: Gap `4px`, Swatch circles (`12x12px`)
  2. `Frame / Content-Body`: Padding `16px`, Gap `8px`
     - Subtitle: `ZELLIGE · MOROCCO` (10px, `#6B6259`, UPPERCASE)
     - Title: `MEDINA BLUSH PINK ZELLIGE` (14.5px, Bold, `#1C1B1B`)
     - Spec Line: `100x100mm · Hand-Chipped Clay` (11.5px, `#6B6259`)
     - Price Lockup: `$185` (18px, Bold, `#1C1B1B`) + `/m²` (11px, `#6B6259`) + ` ($138.75/box)` (11px, `#6B6259`)
  3. `Frame / Card-Footer`: Border-top `1px solid #DCD6CE`, Padding `12px 16px`, Auto-Layout Horizontal (Justify Between)
     - Action: `Order Sample — $3` + ArrowRight (13px, stroke 1.25)

### Component 5: `floating/sample-tray-pill` (Persistent Tray Widget)
- **Positioning**: Fixed (Bottom: `24px`, Right: `24px`)
- **Dimensions**: Hug contents / Min width `280px`, Height `54px`
- **Fill**: `#1C1B1B`
- **Stroke**: `1px solid #5C0202`
- **Corner Radius**: `4px`
- **Padding**: `8px 14px`
- **Children Structure**:
  - Box Icon (`16px`, `#DFB3A5`, stroke 1.25)
  - Stack Vertical:
    - Row: `SAMPLE TRAY · 3 of 5` (11px, Bold, `#F4F2EF`) + `FIVE FOR $15`
    - Progress Bar: Width `100%`, Height `3px`, Track `#6B6259`, Fill `#DFB3A5` (60% width)
    - Subtitle: `Express Post Included Australia-Wide` (9.5px, `#DFB3A5`)
  - Button Action: `VIEW BOX` (Fill `#5C0202`, Radius `2px`, Padding `6px 10px`, Text `#F4F2EF`)

---

## 4. Section Structure Checklist (15 Frames)

1. `Frame_01_Utility_Announcement_Bar` (H: 36px, Fill `#2B0E10`)
2. `Frame_02_Navbar_Sticky` (H: 72px, Fill `#F4F2EF`, Border-bottom `1px #DCD6CE`)
3. `Frame_03_Hero_Section` (2-Columns: Left Headline Lockup, Right Dense Material Swatch Tray)
4. `Frame_04_Trust_Bar_Oxblood` (Full-bleed `#5C0202`, 4 Columns)
5. `Frame_05_Shop_By_Room` (4 Columns: Bathroom, Kitchen, Laundry, Outdoor)
6. `Frame_06_Four_Way_Discovery` (Pill switcher + Filter Chips)
7. `Frame_07_Product_Catalog_Grid` (4-Columns × 2 Rows)
8. `Frame_08_Google_Reviews_Band` (3 Cards + Google Verified Star Rating)
9. `Frame_09_Sample_Offer_Hero_Band` (Full-bleed `#5C0202` 5 for $15 explanation)
10. `Frame_10_Shop_The_Look` (Photography canvas with interactive coordinate pins)
11. `Frame_11_Showroom_Consultation` (Split 2-Columns: Canberra Showroom vs Virtual Booking)
12. `Frame_12_Journal_Articles` (3 Editorial Cards: provenance & laying technique)
13. `Frame_13_Newsletter_Despatch` (Fill `#2B0E10`, Voice Guide verbatim copy)
14. `Frame_14_Instagram_Grid` (6-tile square `@REPUBBLICA.AU`)
15. `Frame_15_Footer_Trade_Portal` (4 Columns + B2B Architectural Specifier Portal)

---

## 5. Typography Lockup Rule Formula
Setiap kali mendesain heading seksi:
- **Part A (85%)**: ALL CAPS, Grotesque Font (Suisse / Plus Jakarta Sans), Weight: Medium (500), Size: 26–34px.
- **Part B (15%)**: lowercase, Serif Italic Font (Playfair Display Italic), Weight: Regular (400), Size: 30–40px (+15% scale), Color: `#5C0202` (Oxblood) or `#DFB3A5` (on dark ground).
