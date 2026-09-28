# ZeeFrames — "What you get" carousel

A drop-in section for zeeframes.com: seven slides with tabs, arrows, a counter and
the dots pill of the testimonial slider. Live demo:
https://semenovmak111-create.github.io/zeeframes-carousel/

## Embed

1. Copy the `<section class="zcr" id="what-you-get" data-zcr>…</section>` block from `index.html`.
2. Add `carousel.css` to the page `<head>` and `carousel.js` before `</body>`.
3. Copy `assets/macbook-air-m1.webp` next to `carousel.css` (it is referenced as
   `assets/macbook-air-m1.webp`; change the `url()` in `.zcr-mbp` if you put it elsewhere).

The block uses the fonts the site already loads (Inter Tight, Inter) and the tokens
from `colors.css` (`--color-primary`, `--color-black-300`, `--color-rich-black`, …)
with fallbacks. All classes are prefixed `zcr-`. No external dependencies.

A light section (white, like the article list of /insights). Each slide is laid
out as the featured article card there: cream copy on the left — category pill,
heading, text, a ✦ line — and a full-bleed picture on the right: a device or a
light UI screen on a flat studio background, as in the home showcase.

## Behaviour

- Prev / next are the round outlined buttons of the testimonial slider, centred in
  the page margins left and right of the card. Below 992 px, where the margin is too
  narrow, the same buttons sit inside the card under the text.
- Tabs follow the WAI-ARIA tabs pattern: ← → move between slides (anywhere inside
  the block), Home / End jump to the first / last. The carousel loops.
- Swipe left / right on the slide; vertical scrolling stays native.
- Autoplay: 8 s per slide, shown by the filling dot. It pauses on hover, focus or
  when the block is off screen, and stops for good after the first manual action.
  The counter is announced (`aria-live`) once autoplay is off.
- `prefers-reduced-motion`: no autoplay, no rise, no shake — slides switch instantly.
- Slides 1–3 hold devices ported from the AMDC landing (iPhone call, laptop with
  listings, lock screen). They scale with the frame through their own `--u` / `--k`
  measure and keep their animations.
