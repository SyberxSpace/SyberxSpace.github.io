---
title: Making the Most of Windows
date: 2020-12-12 21:00:00 -0500
categories: [Tips & Tricks, Technology]
tags: [tips, tricks, unicode, characters, input, software, windows]
---

## Registry Edits

I immediately make these changes on my Windows machines to set up input methods as I like them. The first edit, `EnableHexNumpad`, allows me to use `ALT` + `+####` to input Unicode values instead of just the default alt codes. The second change, `DisableSearchBoxSuggestions` prevents the Windows search bar from web searching, ensuring it always opens programs when their names are typed.

```
Computer
└ HKEY_CURRENT_USER
  ├ Control Panel
  │ └ Input Method
  │   ► STRING • "EnableHexNumpad" • "1"
  └ SOFTWARE
    └ Policies
      └ Microsoft
        └ Windows
          └ Explorer
            ► DWORD • "DisableSearchBoxSuggestions" • "1"
```

**Note:** *Be careful if you decide to make these edits. Back up your registry or computer if you are not confident you know what you are doing.*

---

## Tools

These software packages add significant improvements to the Windows experience in my opinion. *I have no official relationship with any of these besides being a regular user of them.*

| [**AutoHotKey**](https://www.autohotkey.com) | Quick and easy macro creation and key reassignment |
| [**PowerToys**](https://github.com/microsoft/PowerToys) | Adds system features like a color picker, fancy zones, image resizing, and more |
| [**STL-Thumbnail**](https://github.com/cabbagecreek/STL-thumbnail) | Allows Windows to render thumbnails on 3D models |
| [**SuperF4**](https://stefansundin.github.io/superf4) | Allows the killing of programs instantly with Ctrl+Alt+F4 |

I also find installing Ubuntu using the Windows Subsystem for Linux (WSL) to be extremely handy as someone more familiar with the linux command line than the Windows command prompt.

---

## Useful Characters

I map these to keyboard combinations on my keyboard (it has hardware macro support), but they can be typed manually if needed.

| Symbol | Alt Code | Use |
| --: | :-- | :-- |
| • | `7` | Bullet Point |
| ► | `16` | Directional Arrow |
| ◄ | `17` | Directional Arrow |
| ▲ | `30` | Directional Arrow |
| ▼ | `31` | Directional Arrow |
| │ | `179` | Tree Structure |
| └ | `192` | Tree Structure |
| ├ | `195` | Tree Structure |
| ─ | `196` | Tree Structure |
| Ω | `234` | Resistance |
| ± | `241` | Delta from Value |
| ≥ | `242` | Inclusive Comparison |
| ≤ | `243` | Inclusive Comparison |
| ° | `0176` | Temperature and Angles |
| ² | `0178` | 2D Units |
| Ø | `0216` | Diameter |
| ‽ | `+203D` | Interrobang!? |
| ☐ | `+2610` | Checklists |
| ☑ | `+2611` | Checklists |
| ☒ | `+2612` | Checklists |
