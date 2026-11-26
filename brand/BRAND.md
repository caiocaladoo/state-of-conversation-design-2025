# State of Conversation Design: brand guide for charts

Use this to make charts and pages that look like the official report (https://stateofconversationdesign.com/2025/). The images in this folder and in `../images/` are real exports from the report.

## Logo

- Wordmark "SoCD" in **Dela Gothic One**, white on indigo `#4D49FC`, rounded box. The "o" is green `#24CB71`. See `logo-wordmark.png`.
- Square mark: `logo-mark.svg` (vector) and `logo-mark-512.png`.
- In HTML you can rebuild it as text: `<span style="background:#4D49FC;color:#fff;font-family:'Dela Gothic One';padding:6px 14px;border-radius:10px">S<span style="color:#24CB71">o</span>CD</span>`.
- Next to the logo, write the edition as text: "State of Conversation Design 2025/26".

## Fonts (Google Fonts)

- Titles: **Dela Gothic One**
- Text: **IBM Plex Sans** (400, 600)
- Numbers, ids, labels in capitals (such as "QUESTION", "n = 286"): **IBM Plex Mono**

## Colors

| Use | Color |
|---|---|
| Indigo (brand, main bars, left panel) | `#4D49FC` |
| Text | `#0E0D2E` |
| Secondary text | `#3A3965`, `#5A5984` |
| Page background / chart panel | `#F5F5FD` / `#FFFFFF` |
| Lines | `#DAD9F0` |
| Highlight inside text (key words and numbers) | Yellow `#FFC700` on indigo |
| Extra series, in order | `#0391D6`, `#D92A2A`, `#B93FC4`, `#B88600`, `#0F9C55` |
| Other / small groups | Grey `#8A8AA8` |
| Decorative shapes (covers only) | Pink `#F697F9`, yellow `#FFC700`, orange `#FF7237`, blue `#00B6FF`, lime `#D5EB97` |

Never use color alone to tell things apart: label bars directly, and use patterns, outlines or markers when there is more than one series (see the striped and outlined bars in `../images/report-chart-7-45.png`).

## Chart layout (as in the report exports)

See `../images/report-chart-1-03.png`, `report-chart-7-45.png` and `report-chart-9-15.png`.

1. **Header:** logo and "State of Conversation Design 2025/26" on the left; a pill with the chapter ("CHAPTER 07 · FUTURE") on the right.
2. **Left panel, indigo with white text:**
   - chart number and question id in mono ("7.45 · Q45");
   - title in Dela Gothic One;
   - "QUESTION ·" and the question as asked;
   - the takeaway in one or two sentences, with the key words or numbers in yellow;
   - optionally a box "IF YOU DESIGN" with one practical tip.
3. **Right panel, light:** the chart. Values written on the bars, n on every group, small groups (under 10) hidden or marked "small".
4. **Footer:** "n = 286 · scope · Edition 2025/26" on the left; "OPEN THIS CHART" and the report link on the right.

Social cards (`example-finding-card.png`, `example-cover-card.png`) use a dark background `#0E0D2E`, a big number in yellow, and the decorative shapes in the corner.
