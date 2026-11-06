# Reference notes (captured 2026-11-06, Playwright/Chromium, 1280 wide + iPhone 13)

Files: `<key>_pc_top.png` (1280x800), `<key>_pc_full.png` (1280 wide, capped at 6000px), `<key>_sp_top.png` (iPhone 13, DPR 1).
Caveat: some assets on third-party CDNs were blocked by the sandbox network (see each site).

## greenbird (greenbird.jp) — energetic, hand-made
- Hero: full-width **hand-drawn illustration** (people picking litter in city/mountain/sea) on cream, not a photo; big handwritten JP tagline over a giant faint "About" script.
- Fonts: Noto Sans JP throughout (h1 40px / body 16px); headline is lettering art, not text.
- Colors: green #039359, cream #F5F1E6, text #333.
- Floating round badges ("ごみ拾いに参加する", "よくある質問") with wobbly blob shapes. Playful.
- Photos: rounded-corner cards, shown one at a time in a very tall (41,000px) scroll sequence — likely sticky/scroll-triggered.
- Motion: swiper, slick and AOS loaded; wavy SVG section edges.
- Menu: hamburger in a green circle (top-left), pill button "お問い合わせ" (radius 25px).

## spogomi (spogomi.or.jp) — most "sporty/energetic" JP ref
- Hero: huge "SPOGOMI" letters **cut out of a sky photo**, smiling woman+child picking trash in front; handwritten "ごみ拾いはスポーツだ!" over the left.
- Brush-stroke swooshes in yellow/green/blue across the hero bottom and section breaks — strong sense of motion.
- Fonts: Noto Sans JP; h2 35px weight 900 vs body 16px (good contrast).
- Colors: blue #1768C4, yellow #F5D400 accents, green #6DBE45, white.
- Sections: news list, "スポGOMIとは", big number cards (209,489人 / 2,080回 / 264,517kg) with icons, event search, FAQ. Clear rhythm, alternating white/light-blue bands.
- Header: sticky white bar, solid blue rounded button (radius 6px). 7 CSS-animated elements.
- Feels slightly corporate below the hero, but the hero + numbers are a strong model.

## uminohi (uminohi.jp) — bright but busy
- Hero: full-bleed photo of kids splashing into the sea, logo centered over the people; "Scroll" mouse cue; wavy bottom edge.
- Fonts: Lato + 游ゴシック; h2 52px vs body 14px.
- Colors: blue #3164BD, light aqua #EAF6FC, red accent from logo.
- Below hero: carousel of campaign banners (swiper), round icon "5 actions", many card grids → feels like a portal, dated/crowded.
- Fixed white header with a solid blue square hamburger; floating SNS icons on the right.

## oceancleanup (theoceancleanup.com) — bold but cool
- Cookie banner dismissed via "Accept all cookies".
- Hero: background **video was blocked**, so it shows a dark navy gradient; huge thin uppercase headline "JOIN THE LARGEST CLEANUP IN HISTORY" (Proxima Nova, 85px weight 300 vs body 18px).
- Colors: navy #003755, deep #002640, cyan #01CBE1.
- Stats strip (65M+ / 2–5% / 100+) with thin cyan rules; headings mix light + bold words ("WE **DEVELOP AND SCALE** SOLUTIONS").
- Long dark sections with lots of empty space (probably parallax video in the original).
- Header: white bar with a cyan logo block, navy "DONATE NOW" square button (radius 2px). Flickity slider.

## surfrider (surfrider.org) — campaign-poster punch
- Hero: full-bleed dramatic photo (oil fire at sea), left-aligned bold uppercase "DRILLING IS KILLING" (Roboto 56px vs 16px).
- Section labels in Bebas (condensed caps).
- Colors: coral-red #D15C5C (DONATE), black, light grey header #F5F6F7.
- Square buttons (radius 0). A CTA image failed to load (blocked asset).
- Rest of the page: standard card grids, relatively static (no motion libraries detected). Activist tone but not "youthful".

## 4ocean (4ocean.com) — e-commerce gloss
- Hero: full-bleed photo of a gloved hand picking a bottle on the beach, workers blurred behind; text bottom-left over darkened left side (not over faces).
- Montserrat throughout, uppercase bold headings (36px) vs 16px body; pill tag "50+ MILLION POUNDS REMOVED".
- Colors: royal blue #0057B8, white, black.
- Photos edge-to-edge in a tight grid with no gutters → magazine/shop feel; large split image/text blocks ("WHAT WE DO / WHAT YOU DO").
- Transparent header over the hero, blue announcement bar on top; square blue buttons. AOS scroll fades, 1 video.

## worldcleanup (worldcleanupday.org) — not usable
- Page loaded, but its Webflow CSS/image CDN (cdn.prod.website-files.com) and jQuery were **blocked by the sandbox network**, so screenshots show unstyled HTML (Times New Roman, blue links).
- Detected: slick + AOS, big count-up numbers (212 countries, 139M people). Design cannot be judged from these shots.

## fff (fridaysforfuture.jp) — youth movement, but plain
- Hero: boxed slider (swiper) of campaign posters ("ワタシのミライ") with arrows/dots, not full-bleed; lots of white space.
- Fonts: Poppins body, Assistant headings (29px), handwritten-style logo.
- Colors: green #007850, orange #E3912D, coral posters.
- Thin white header with green text links separated by dots; no strong CTA button.
- Lottie animations and 10 animated elements, but overall feels like a template; the posters carry all the energy.

## kab (kab.org) — dated
- Two-tier header (utility links + tall dark-green bar 231px total), menu wraps to 2 lines at 1280 — feels heavy.
- Hero: full-bleed photo (seagulls on a fence by the sea), large white text block over the photo; outline button with arrow.
- Open Sans; h2 35px weight 500 vs body 16px grey #666 — low contrast, little hierarchy.
- Colors: dark green #0B4D3F, orange #EBA04A (Donate), white.
- Swiper + GSAP loaded; Divi-style section stacking. Google Translate widget in the corner.

## Quick takeaways for Clean Vibes
- Most energetic: **spogomi** (cut-out giant word + brush swooshes + big numbers) and **greenbird** (hand-drawn, playful badges). **4ocean** for tight edge-to-edge photo grids; **oceancleanup** for oversized headline + stats strip.
- Avoid: kab's heavy header, uminohi's portal-like card clutter, fff's boxed slider hero.
