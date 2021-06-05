---
title: My Canvas Format
date: 2021-02-07 12:00:00 -0500
categories: [Teaching, Resources]
tags: [canvas, code, resources]
---

## Daily Calendar Post Format

---

**Day # Objectives**

1. Item
  - Instruction
  - Instruction
    - Detail
    - Detail
  - Instruction
2. Item
  - Instruction
    - Detail
    - Detail
3. Don't Forget
  - Item DUE **TODAY**, time
  - Item DUE date, time
4. Weekly Accomplishments
  - Should be completed by Friday

---

## Code Snippets

**Horizontal Bar** (Divider)
```html
<div style="padding-top: 1em; padding-bottom: 1em; width=100%"> <!-- Divider -->
<div style="background-color: #017c8b; width: 100%; height: 6px;">&nbsp;</div>
</div>
```

**Title Bar** (Header)
```html
<table style="width: 100%; border-collapse: collapse; background-color: #017c8b;" border="1">
<tbody>
<tr>
<td style="width: 100%;">
<h2 style="text-align: center;"><span style="color: #ffffff; font-size: 24pt;"> Title </span></h2>
</td>
</tr>
</tbody>
</table>
```

---

## YouTube Linking

Start with this URL:
`https://www.youtube.com/embed/[Video ID]?version=3`

Then add tags (place at end of URL):

| &start=[seconds] | set start time |
| &end=[seconds] | set end time |
| &rel=0 | limit suggested videos to same channel |
| | |
| &autoplay=1 | automatically start video |
| &cc_load_policy=1 | automatically enable closed captions |
| &cc_lang_pref=en | set caption language to english |

Less useful tags:

| &loop=1 | loop video, must be followed by &playlist=[Video ID] (doesn't work with start or end) |
| &iv_load_policy=3 | disable video annotations (doesn't generally affect modern videos) |
| &modestbranding=1 | do not show YouTube logo (doesn't generally affect much) |
| &controls=0 | disable control visibility (good to avoid hovering controls, bad for media control or fullscreen) |
