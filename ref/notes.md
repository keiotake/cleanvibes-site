# Reference: bikazaidan.or.jp (top page) — observed 2026-11-06

Values come from the DOM and computed styles at 1280px wide. Values marked "≈" were read from screenshots. The site runs on the WordPress theme TCD "nano" (nano_tcd065) with a slick slider.

## Section order (top → bottom, PC page height ≈7,900px)
1. **Header** (0–160px): a logo row plus a full-width grey menu bar.
2. **Hero slider** (160–860px): full-bleed photos at 1280×700 that rotate through 4 slides, each with a centered white caption and a "続きを見る" type button.
3. **Intro card** (760–1075px): a white box overlapping the bottom 100px of the hero. It holds the h2 "おーい！ みんなで海岸をキレイにしようよ！" with a 2-line centered paragraph.
4. **Three tiles** (1075–1718): Volunteer / Marine debris / Supporter. Each tile is an h3 (JP) + small English label over a portrait photo (≈391×533). The tiles sit edge to edge with 1px #DDD borders. A blue button "財団の案内" sits below them.
5. **News** "お知らせ / NEWS" (1818–2717): 4 tabs (active tab black bg + white text) above a list of 10 rows (date · pill category label · title). The rows have bg #F8F8F8 and a 1px #DDDDDD border, each 61px tall. A blue button "お知らせ list" follows.
6. **Supporter** "サポーター募集 / support" (2817–4450): a centered paragraph above a 3-column card grid (image ≈372×220, title, excerpt, black pill "ご寄付"). Each card's text block has a ≈4px blue left border. A blue button "サポーター募集" follows.
7. **Banner**: a GREEN×EXPO 2027 image (≈1024 wide).
8. **Member logos**: a blue bar heading "特別法人・団体会員" (white text) above a 6-column grid of logos (no borders).
9. **Link banners**: three photo banners (≈370×140) with white overlaid text, on a light grey band (≈#F3F3F3).
10. **Footer**: logo + tagline + SNS icons on one row, a row of small text links below it, then a blue copyright bar.

## Header
- Static (not sticky), 160px tall in total, white.
- Row 1 (100px): logo image 354×51 at the left (x=50), tagline "日本で唯一の海岸美化専門の団体です。" (16px) next to it, and a search icon at the far right.
- Row 2 (60px): nav bar with bg **#EEEEEE**, a 1180px inner area with 50px side margins, and 5 items spread over the full width with vertical divider lines. Text is 14px, black, centered, line-height 60px. Dropdowns are white text on blue.
- SP: logo + hamburger; the hero starts directly below.

## Hero
- PC 1280×700, SP ≈390×600, image cover. The text **overlaps the image**: centered white text (serif, ≈34px) with no dark box behind it. The first viewport shows header + hero only (see bika_pc_top.png).

## Typography
- Body: `Arial, "Hiragino Sans", "Yu Gothic Medium", Meiryo, sans-serif`, 16px, black #000. Paragraph line-height ≈2.1 (intro).
- Headings (h1–h3): `"Times New Roman", "Yu Mincho", 游明朝, "Hiragino Mincho Pro", serif`, weight 700. **Note:** the page loads no web font, and the screenshots render these as a gothic font in this environment.
- h2 section titles: 43–46px, centered, with a small 14–16px English subtitle below. Intro h2 is 35px. Tile h3 is 30px.
- News titles 14px. Footer links ≈12px.

## Colors
- Background: #FFFFFF. Grey surfaces: #EEEEEE (nav), #F8F8F8 (news rows), ≈#F3F3F3 (banner band).
- Text #000000. Borders #DDDDDD.
- Accent **#00A0E9** (buttons, copyright bar, member heading bar, card left borders).
- Black #000000 for the active tab, "ご寄付" pills and the page-top button.
- Category pills: outlined, 1px, with blue / red / green text depending on the category.

## Spacing
- Content width 1180px (50px side margins). Each section block has `margin-bottom: 100px`. The intro card has 92px top/bottom padding. Headings sit ≈50px above their content.

## Photos
- **No border radius anywhere and no shadows on images.** Tiles are portrait (≈3:4), cards ≈5:3, the hero is wide (≈16:9 / 1280×700), and images use object-fit: cover.
- The only shadow on the page is on the intro card: `0 -8px 10px rgba(0,0,0,.2)` (upward, over the hero).

## Buttons
- Main: flat rectangle 240×60, bg #00A0E9, white bold 14px, radius 0, centered under each section.
- Secondary: black pill (≈100×30, fully rounded), white 12px text.

## Footer
- White, 753px tall in total. One row with the logo (left), tagline and SNS icons (right). Below a thin divider, a centered row of 8 text links (≈12px). At the bottom, a copyright bar (60px tall) in **#00A0E9** with white 12px text.

## Capture notes
- The origin server often returned **HTTP 502**, sometimes for the HTML itself and often for individual images and jquery-migrate.js. I retook the shots until the page, CSS and JS loaded. Some images are still missing in the final shots, shown as empty frames: several supporter card images, some member logos, and the FooGallery grid (grey placeholders on PC).
- SP page width is 394px (a 4px horizontal overflow on the site itself).
