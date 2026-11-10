# titan-art.com UX notes (captured 2026-11-10)

**Capture caveat:** this sandbox's proxy blocks cdnjs/jsDelivr/unpkg, so the page's CDN libraries were served from identical npm versions through Playwright request interception. Without that, the page stays a blank white loader (the GSAP timeline never runs). Screenshots: `titan_t*` = opening at 0/1/2.5/5s, `titan_s01–s16` = 700px scroll steps (page is ~11,700px tall, so step 16 is the footer), `titan_sp_*` = iPhone 13, `titan_menu_*` = full-screen menu, `titan_hover_*` = hover states.

## Stack (WordPress theme "titanosaka", jQuery-based, no SPA)
jquery-3.7.1, jquery.easing 1.4.1, jquery.cookie, **lenis@1.0.19** (smooth scroll), smooth-scroll.min.js (anchor links), **jquery inview.min.js** (scroll reveal trigger), **swiper@8**, **gsap 3.11.5** (opening), **TweenMax 1.20.3** (cursor), **pixi.js 7.4.0** (opening particles), three.js r83 (loaded, not used visibly), lottie-player, prefixfree. Theme scripts: custom.js, customTop.js, mousestoker.js, customPopbn.js. The pjax.js page-transition script is commented out, so there are **no page transitions** (normal page loads).

## Opening animation (`titan_t0–t5`)
- `#loadingTop` is a fixed white full-screen overlay (z 10000) holding a PIXI canvas.
- The logo SVG is sampled pixel by pixel. Each pixel becomes a 1.5px black dot that starts at a random screen position and flies into place (`duration 3.5, ease "expo.inOut"`), so the logo assembles out of dust (t1).
- GSAP timeline: canvas fades in (0.5s) → canvas fades out after 4.5s, while the tagline 「クリエイティブの力で / 世界の課題を解決する」 (Shippori Mincho, 45px, letter-spacing 20px, centred, 2 lines) fades in (0.8s) → the overlay fades out (0.5s, delay 2s) and slides down (`y:"100%"`). Total ≈ 6s.
- Then the hero `#topMainSlide` (Swiper) reveals a layered image collage: `.img00…img05` each run `slide-active .3s` (opacity 1→0), staggered at 3s, 3.6s, 4.2s … 6s, so the stacked images peel away one by one.
- `sessionStorage.access` is set (intended to skip the loader on later visits).

## Scroll behaviour
- **Lenis inertia scroll** on the whole page: `new Lenis()` with defaults plus an rAF loop. Anchor links use jQuery `animate({scrollTop}, 500–800, "swing")`.
- **Reveal on scroll:** jQuery inview adds `.is-show` once. Fade-up of 5vw, 0.5s, with nth-of-type staggering of 0.1s:
```css
.fadeIn01{opacity:0;transition:.5s}
.fadeIn01.fadeup{transform:translateY(5vw)}
.fadeIn01.is-show{opacity:1}
.fadeIn01.fadeup.is-show{transform:translateY(0)}
.fadeIn01.is-show:nth-of-type(2){transition-delay:.1s} /* … up to 20 → 1.9s */
```
- **Split-text letters (OUR MISSION, `s09`):** `.triggers` text is split by JS into `<span class="row">` per line and `<span>` per character. On inview, each char gets `.animate` with a `ind*50ms` stagger. The `.triggers02` variant is a big heading with `background-clip:text` showing an animated GIF through the letters (faint grey text on black).
- **Word roulette (vision block):** `#rotate-text` cycles 企業→顧客→社員→採用→商品→未来→世界 by sliding out down and in from the top (`transform .5s ease-in-out`, 1s hold). It is started by an IntersectionObserver and stops on the last word.
- **Section background colour switch:** `.bgScrlArea{transition:all .7s ease}`. Passing each `.block-bg` (offset −500px) sets bg `#E6E6E6 → #000000 → #FFFFFF` and text black/white/black. This is the grey→black→white shift in `s07–s10`.
- **Count-up numbers** (`#count01-03`) on inview.
- **Marquees:** logo strips are Swiper `loop, slidesPerView:3, speed:3000, autoplay delay 0` with `.swiper-wrapper{transition-timing-function:linear}`, a continuous ticker, plus a reversed row (`logoslider_rev`). The CSS news bar uses `@keyframes utageNewsBarMarquee{to{transform:translateX(-50%)}}`.
- No parallax, no pinned or horizontal-scroll sections. Sticky elements are only the fixed header and UI chrome.

## Custom cursor (mousestoker.js, PC ≥769px)
- `.c-pointer` and `.c-follower`: 96px fixed circles, `pointer-events:none`, `mix-blend-mode:exclusion` (white, `.is-blend`), following the mouse with TweenMax lag.
- Idle follower scale .111 (a small dot). On `a, button` hover → scale .666 (`Back.easeInOut(1.4)`, .3s).
- On `a.view` (works thumbnails) the pointer hides and the follower grows to scale 1 with a "VIEW" label (`titan_hover_cursor_view.png`).

## Hover effects
- **Expanding panels (OUR CREATIVE, `titan_hover_panels.png`):** three flex panels (BRANDING / DISPLAY / MOTION) with a video bg and a white 70% overlay. The hovered panel grows (`transition:flex .55s cubic-bezier(.4,0,.2,1)`), its overlay darkens and the text turns white, and the description opens (`max-height .5s`, opacity).
- **Case-study list (SERVICE, `s05`):** hovering a service name (`.case-study-name`) swaps a full-bleed background image (`li.show`, `300ms linear` fade, plus a large faint number at opacity .2).
- **`.hvrbtn` buttons:** a black `:before` fill animates `width .3s ease` (wipe), with an arrow chevron.
- **MENU circle:** an SVG circle stroke draws around it (`stroke-dashoffset 250→0, .6s`).
- Images: `.hvrbtn2 img{transition:.8s} :hover{opacity:.5}`.

## Navigation
- Fixed white top header: logo on the left, small uppercase Josefin links (BRANDING, PACKAGE, WEB, WORKS, PRICE, SERVICE▾, COMPANY, BLOG) and a black square **CONTACT** block on the right.
- Left-centre floating circular **MENU** button (`.btnNav`, 4.1vw, `mix-blend-mode:exclusion`, becomes a black outline after scroll). Click opens a **full-screen overlay** `.gnav_all` with white 50% + `backdrop-filter: blur(30px)` and an opacity .5s fade, and the button turns into "BACK". The overlay has large two-column links (Josefin Bold 45px, numbered 01–07 services, Japanese sublabels 14px), the tagline in Mincho on the right, and SNS links (`titan_menu_open.png`).
- SP: a hamburger circle at the top right, a fixed bottom bar 「問い合わせ / 電話する」, and a floating promo banner bottom-right (close ×).

## Typography / colour / layout
- `html{font-size:62.5%}` (1rem = 10px).
- Body: "Noto Sans JP", 18px, #000. h2/section titles: "Josefin Sans" 700, 37px, uppercase (e.g. "OUR CREATIVE"), centred, with a short rule below. Statement copy: "Shippori Mincho B1" 500, 45px, letter-spacing 20px, line-height 2.
- Monochrome palette: #FFFFFF, #000000, #222222, #E6E6E6, #F5F5F5, #7F7F7F. The colour comes only from photos and promo banners (#275C95/#164474 navy appear in a few elements).
- Lots of whitespace, content ~77vw wide, sizes often in vw (`calc(x/1920*100vw)`), PC/SP breakpoint 896px (cursor 769px).
