# Alansari.Tech Motion Library v2.0

1000 named motion presets for AI-assisted video editing (Instagram Reels / TikTok / Shorts).

## Instructions for the AI editor
- When the user names a motion by ID (e.g. `M-016`) or by name, implement it exactly as specified below.
- Default canvas: 1080x1920, 30fps. Pixel values are for a 1080-wide frame; scale proportionally for other sizes.
- Start every motion on the exact frame of the word or action the user names (use word-level transcript timestamps).
- Keep text and UI inside the Reels safe zone: y between 300 and 1550 px, x between 60 and 1020 px.
- Accent colour: #E3643F (Sunset Coral) with #0F5B66 (Gulf Teal), unless the user gives other colours. Text: bold Arabic display font (e.g. Alexandria 800), white with a soft shadow.
- "Behind the person" means a layer under the person, using a video matte (e.g. Robust Video Matting).
- Suggested pipeline: draw motions in an HTML page with render(t), render frame by frame with Playwright, composite over the video with ffmpeg. Add a light matching sound effect under the voice for each motion.
- Before the final render, export stills of each motion moment and check timing, overlaps and the safe zone.
- Motions can be chained, e.g. "M-016 then M-038".
- Each motion has a "Content the user must provide" line. If the user did not supply that content (text, image, screen recording, logo, handle…), ASK for it before rendering. Never invent screenshots, logos, faces or screen recordings, and never leave placeholder text in the final video.
- Variants (Fast, Slow, Gold, Boxed…) need the same content as the motion they come from.

## TXT — Text In

### M-001 · Fade Up
- **When to use:** The simplest entrance for any title or line.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.45s in · 0.3s out
- **Easing:** easeOutCubic
- **Spec:** Text starts 40px below its final position at opacity 0, rises into place while fading to 1 over 0.45s (easeOutCubic). Holds. Exit: fade to 0 while drifting up 12px over 0.3s.

### M-276 · Fade Up · Fast
- Variant of M-001. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-001

### M-551 · Fade Up · Boxed
- Variant of M-001. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-001

### M-826 · Fade Up · Slow
- Variant of M-001. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-001

### M-002 · Typewriter
- **When to use:** When text should type out letter by letter, like code or a prompt.
- **Content the user must provide:** text: the text to show
- **Duration:** ~0.07s per character
- **Easing:** steps (one char per step)
- **Spec:** Characters appear one at a time at a constant rate (about 14 chars/sec), with a blinking caret (0.6s blink) at the writing edge. For Arabic, reveal right-to-left by word or by clipping from the left. Hold, then erase or cut.

### M-290 · Typewriter · Fast
- Variant of M-002. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-002

### M-565 · Typewriter · Boxed
- Variant of M-002. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-002

### M-840 · Typewriter · Slow
- Variant of M-002. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-002

### M-003 · Letter Cascade
- **When to use:** A short English word that should grab attention.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.5s per letter · 0.07s stagger
- **Easing:** easeOutBack
- **Spec:** Each letter drops from 60px above with a -14° rotation and opacity 0, landing in place over 0.5s (easeOutBack). Letters are staggered 0.07s apart. Use on Latin words; for Arabic use word-level stagger to keep letters joined.

### M-304 · Letter Cascade · Fast
- Variant of M-003. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-003

### M-579 · Letter Cascade · Boxed
- Variant of M-003. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-003

### M-854 · Letter Cascade · Slow
- Variant of M-003. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-003

### M-004 · Mask Slide
- **When to use:** Elegant, cinematic titles.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.55s in · 0.45s out
- **Easing:** easeInOutQuart
- **Spec:** The text sits inside an invisible box with overflow hidden. It slides up from 110% below the box edge into place over 0.55s, holds, then continues upward out of the box over 0.45s. No fading.

### M-318 · Mask Slide · Fast
- Variant of M-004. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-004

### M-593 · Mask Slide · Boxed
- Variant of M-004. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-004

### M-868 · Mask Slide · Slow
- Variant of M-004. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-004

### M-005 · Blur In
- **When to use:** Calm lines or the opening of a video.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.7s in · 0.5s out
- **Easing:** easeOutQuad
- **Spec:** Text starts at scale 1.3, blur 30px, opacity 0 and settles to scale 1, blur 0, opacity 1 over 0.7s. Exit by blurring to 20px while fading out over 0.5s.

### M-332 · Blur In · Fast
- Variant of M-005. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-005

### M-607 · Blur In · Boxed
- Variant of M-005. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-005

### M-882 · Blur In · Slow
- Variant of M-005. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-005

### M-041 · Slide In Right
- **When to use:** A quick title entrance from the right.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.4s in · 0.3s out
- **Easing:** easeOutCubic
- **Spec:** Text enters from 70% of its width to the right, fading 0 to 1 over 0.4s, holds, then exits to the left with a fade over 0.3s.

### M-346 · Slide In Right · Fast
- Variant of M-041. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-041

### M-621 · Slide In Right · Boxed
- Variant of M-041. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-041

### M-896 · Slide In Right · Slow
- Variant of M-041. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-041

### M-042 · Slide In Left
- **When to use:** An entrance from the left, good for English text or lists.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.4s in · 0.3s out
- **Easing:** easeOutCubic
- **Spec:** Text enters from 70% of its width to the left, fading in over 0.4s, holds, then exits to the right with a fade over 0.3s.

### M-360 · Slide In Left · Fast
- Variant of M-042. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-042

### M-635 · Slide In Left · Boxed
- Variant of M-042. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-042

### M-910 · Slide In Left · Slow
- Variant of M-042. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-042

### M-043 · Drop In
- **When to use:** A title falls from above and bounces, playful.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.5s
- **Easing:** easeOutBounce
- **Spec:** Text drops from 160% above its place, overshoots 8% down, bounces back 4% up and settles over 0.5s. Exit by fading out.

### M-374 · Drop In · Fast
- Variant of M-043. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-043

### M-649 · Drop In · Boxed
- Variant of M-043. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-043

### M-924 · Drop In · Slow
- Variant of M-043. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-043

### M-044 · Zoom In Text
- **When to use:** A word grows from a dot to full size.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.5s
- **Easing:** easeOutExpo
- **Spec:** Text scales from 20% to 100% while fading in over 0.5s (easeOutExpo). Exit by scaling to 110% and fading out.

### M-388 · Zoom In Text · Fast
- Variant of M-044. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-044

### M-663 · Zoom In Text · Boxed
- Variant of M-044. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-044

### M-938 · Zoom In Text · Slow
- Variant of M-044. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-044

### M-045 · Zoom Out Text
- **When to use:** A strong word slams onto the screen.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.45s
- **Easing:** easeOutQuart
- **Spec:** Text starts at 240% scale and opacity 0 and shrinks to 100% while fading in over 0.45s, like it lands on the screen. Pair with a low "boom".

### M-400 · Zoom Out Text · Fast
- Variant of M-045. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-045

### M-675 · Zoom Out Text · Boxed
- Variant of M-045. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-045

### M-950 · Zoom Out Text · Slow
- Variant of M-045. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-045

### M-046 · Flip In
- **When to use:** A title flips in on the horizontal axis like a sign.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.5s in · 0.4s out
- **Easing:** easeOutBack
- **Spec:** Text rotates from 90° to 0° around the X axis with perspective while fading in over 0.5s. Exit by rotating to -90°.

### M-412 · Flip In · Fast
- Variant of M-046. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-046

### M-687 · Flip In · Boxed
- Variant of M-046. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-046

### M-962 · Flip In · Slow
- Variant of M-046. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-046

### M-047 · Rotate In
- **When to use:** A word spins in, good for "turnaround" moments.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.5s
- **Easing:** easeOutBack
- **Spec:** Text rotates from -90° and 60% scale to 0° and 100% while fading in over 0.5s. Exit with a small 30° turn and fade.

### M-423 · Rotate In · Fast
- Variant of M-047. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-047

### M-698 · Rotate In · Boxed
- Variant of M-047. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-047

### M-973 · Rotate In · Slow
- Variant of M-047. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-047

### M-048 · Word Stagger
- **When to use:** A short line where each word follows the one before.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.45s per word · 0.2s stagger
- **Easing:** easeOutCubic
- **Spec:** Each word rises 40px and fades in over 0.45s, starting 0.2s after the previous word. Hold the full line, then fade all out together.

### M-434 · Word Stagger · Fast
- Variant of M-048. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-048

### M-709 · Word Stagger · Boxed
- Variant of M-048. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-048

### M-984 · Word Stagger · Slow
- Variant of M-048. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-048

### M-049 · Elastic Pop
- **When to use:** A word pops with a rubbery squash and stretch.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.6s
- **Easing:** elastic
- **Spec:** Text scales from 0 to a squash (130% wide, 80% tall), then a stretch (85% wide, 115% tall), then settles at 100% over about 0.6s.

### M-444 · Elastic Pop · Fast
- Variant of M-049. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-049

### M-719 · Elastic Pop · Boxed
- Variant of M-049. put the text inside a solid light cream #F3E9D2 box with rounded corners and dark teal #102E33 text (a light box is used here because the motion own effect colors would disappear on a dark box). Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-049

### M-994 · Elastic Pop · Slow
- Variant of M-049. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-049

### M-050 · Split Reveal
- **When to use:** A title split in two halves that meet in the middle.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.5s
- **Easing:** easeOutQuart
- **Spec:** The top half of the text slides down from 70% above and the bottom half slides up from 70% below, meeting at the line over 0.5s.

### M-453 · Split Reveal · Fast
- Variant of M-050. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-050

### M-728 · Split Reveal · Boxed
- Variant of M-050. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-050

### M-051 · Scramble Decode
- **When to use:** English text resolves from random characters, great for cyber topics.
- **Content the user must provide:** text: the text to show
- **Duration:** ~1s decode
- **Easing:** linear
- **Spec:** Each character cycles through random symbols (A–Z, 0–9, #%&) every 2 frames, then locks to its final letter from left to right over about 1s.

### M-462 · Scramble Decode · Fast
- Variant of M-051. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-051

### M-737 · Scramble Decode · Boxed
- Variant of M-051. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-051

### M-052 · Wave Text
- **When to use:** English letters ripple in a wave.
- **Content the user must provide:** text: the text to show
- **Duration:** loop · 0.08s stagger
- **Easing:** easeInOutSine
- **Spec:** Each letter moves up 28% and back in a smooth wave, each starting 0.08s after the previous one, so a ripple runs across the word.

### M-470 · Wave Text · Fast
- Variant of M-052. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-052

### M-745 · Wave Text · Boxed
- Variant of M-052. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-052

### M-053 · Outline to Fill
- **When to use:** A title draws as an outline, then fills in.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.8s outline · 0.4s fill
- **Easing:** easeInOutCubic
- **Spec:** The text first appears as an accent outline only, revealed from the reading-start side over 0.8s, then the fill color fades in over 0.4s.

### M-478 · Outline to Fill · Fast
- Variant of M-053. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-053

### M-753 · Outline to Fill · Boxed
- Variant of M-053. put the text inside a solid light cream #F3E9D2 box with rounded corners and dark teal #102E33 text (a light box is used here because the motion own effect colors would disappear on a dark box). Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-053

### M-054 · Spotlight Reveal
- **When to use:** Hidden text revealed by a passing spotlight.
- **Content the user must provide:** text: the text to show
- **Duration:** 1.4s sweep
- **Easing:** easeInOutSine
- **Spec:** The text sits at 12% opacity. A soft circular spotlight (radius about 13% of the width) sweeps across it and shows the text at full brightness where it passes.

### M-486 · Spotlight Reveal · Fast
- Variant of M-054. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-054

### M-761 · Spotlight Reveal · Boxed
- Variant of M-054. put the text inside a solid light cream #F3E9D2 box with rounded corners and dark teal #102E33 text (a light box is used here because the motion own effect colors would disappear on a dark box). Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-054

### M-055 · Gradient Wipe Text
- **When to use:** A word changes color with a soft wipe.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.8s
- **Easing:** easeInOutCubic
- **Spec:** A two-color gradient (accent and white) is clipped to the text and slides across it over 0.8s, so the word changes color with a soft edge.

### M-494 · Gradient Wipe Text · Fast
- Variant of M-055. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-055

### M-769 · Gradient Wipe Text · Boxed
- Variant of M-055. put the text inside a solid light cream #F3E9D2 box with rounded corners and dark teal #102E33 text (a light box is used here because the motion own effect colors would disappear on a dark box). Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-055

### M-056 · Neon Flicker
- **When to use:** A neon sign title that flickers on.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.8s flicker
- **Easing:** steps
- **Spec:** The text has a white core and an accent glow (two text shadows). It turns on with 3–4 quick flickers (opacity 12% to 100%) in the first 0.8s, then stays lit.

### M-502 · Neon Flicker · Fast
- Variant of M-056. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-056

### M-777 · Neon Flicker · Boxed
- Variant of M-056. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-056

### M-057 · Stretch In
- **When to use:** A wide, fast entrance with energy.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.4s
- **Easing:** easeOutExpo
- **Spec:** Text starts squashed to 300% width and 20% height at opacity 0 and snaps to normal over 0.4s. Exit by stretching tall and thin.

### M-510 · Stretch In · Fast
- Variant of M-057. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-057

### M-785 · Stretch In · Boxed
- Variant of M-057. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-057

### M-058 · Skew Slide
- **When to use:** A fast slanted slide, like it is flying in.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.5s
- **Easing:** easeOutBack
- **Spec:** Text slides in from 60% to the right with a -30° skew, overshoots to +10° skew and straightens over 0.5s. Exit to the left skewing the other way.

### M-518 · Skew Slide · Fast
- Variant of M-058. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-058

### M-793 · Skew Slide · Boxed
- Variant of M-058. put the text inside a solid light cream #F3E9D2 box with rounded corners and dark teal #102E33 text (a light box is used here because the motion own effect colors would disappear on a dark box). Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-058

### M-059 · Kinetic Stack
- **When to use:** A three-word line stacking up in different sizes.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.5s per word · 0.3s stagger
- **Easing:** easeOutBounce
- **Spec:** Each word drops in from above (M-043 style) one under the other, 0.3s apart, each in a different size and weight, forming a tight stacked block.

### M-526 · Kinetic Stack · Fast
- Variant of M-059. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-059

### M-801 · Kinetic Stack · Boxed
- Variant of M-059. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-059

### M-060 · Slot Machine
- **When to use:** Letters spin like a slot machine and land on the word.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.9s · 0.15s stagger
- **Easing:** easeOutQuart
- **Spec:** Each letter sits in a one-row window and scrolls through a column of 5 random letters before landing on its final letter over 0.9s. Letters stop 0.15s apart from left to right.

### M-534 · Slot Machine · Fast
- Variant of M-060. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-060

### M-809 · Slot Machine · Boxed
- Variant of M-060. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-060

## EMP — Emphasis

### M-006 · Highlight Sweep
- **When to use:** Highlights a key word like a marker pen.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** 0.5s sweep
- **Easing:** easeInOutCubic
- **Spec:** A solid accent-colored box grows behind the word from 0% to 100% width over 0.5s (from the reading-start side: right for Arabic). The word color switches to dark for contrast. The box shrinks back on exit.

### M-277 · Highlight Sweep · Fast
- Variant of M-006. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-006

### M-552 · Highlight Sweep · Boxed
- Variant of M-006. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-006

### M-827 · Highlight Sweep · Slow
- Variant of M-006. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-006

### M-007 · Underline Draw
- **When to use:** A quiet emphasis on one word.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** 0.6s draw
- **Easing:** easeInOutQuint
- **Spec:** A rounded accent line (about 8% of the font size thick) draws under the word from the reading-start side to the end over 0.6s, holds, then retracts toward the far side.

### M-291 · Underline Draw · Fast
- Variant of M-007. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-007

### M-566 · Underline Draw · Boxed
- Variant of M-007. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-007

### M-841 · Underline Draw · Slow
- Variant of M-007. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-007

### M-008 · Scale Punch
- **When to use:** A strong word that needs a hit on the beat or a sound effect.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** 0.15s punch · 0.25s settle
- **Easing:** easeOutBack
- **Spec:** On the exact spoken frame the word jumps to 150% scale in 0.15s and turns accent color, then settles to 125% over 0.25s and holds. Return to 100% at the end. Pair it with a short "boom" or "pop" sound effect.

### M-305 · Scale Punch · Fast
- Variant of M-008. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-008

### M-580 · Scale Punch · Boxed
- Variant of M-008. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-008

### M-855 · Scale Punch · Slow
- Variant of M-008. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-008

### M-009 · Word Shake
- **When to use:** Surprise, anger or a warning.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** 0.6s shake
- **Easing:** linear (damped)
- **Spec:** The word shakes horizontally with ±6% offsets and ±4° rotation, alternating every 0.04–0.05s for about 0.6s, with the amplitude damping toward zero.

### M-319 · Word Shake · Fast
- Variant of M-009. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-009

### M-594 · Word Shake · Boxed
- Variant of M-009. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-009

### M-869 · Word Shake · Slow
- Variant of M-009. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-009

### M-010 · Glitch Text
- **When to use:** Tech, AI and hacking topics.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** 0.6s glitch burst
- **Easing:** steps
- **Spec:** For about 0.6s, two copies of the text (cyan #3FE0FF and red #FF3F6C) jitter ±5% offset and show through random horizontal slice masks, changing every 2–3 frames, while the main text skews ±8°. Then everything snaps back clean.

### M-333 · Glitch Text · Fast
- Variant of M-010. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-010

### M-608 · Glitch Text · Boxed
- Variant of M-010. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-010

### M-883 · Glitch Text · Slow
- Variant of M-010. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-010

### M-061 · Circle Around
- **When to use:** Circles a key word as if drawn with a pen.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** 0.6s draw
- **Easing:** easeInOutCubic
- **Spec:** A hand-drawn accent ellipse strokes around the word over 0.6s (animated stroke), holds, then erases. Slightly uneven so it feels hand-made.

### M-347 · Circle Around · Fast
- Variant of M-061. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-061

### M-622 · Circle Around · Boxed
- Variant of M-061. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-061

### M-897 · Circle Around · Slow
- Variant of M-061. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-061

### M-062 · Strike Through
- **When to use:** Crosses out a wrong or old word before the right one.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** 0.5s
- **Easing:** easeInOutQuint
- **Spec:** An accent line draws through the middle of the word from the reading-start side over 0.5s, holds, then retracts.

### M-361 · Strike Through · Fast
- Variant of M-062. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-062

### M-636 · Strike Through · Boxed
- Variant of M-062. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-062

### M-911 · Strike Through · Slow
- Variant of M-062. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-062

### M-063 · Box Outline Draw
- **When to use:** Frames a word inside a drawn box.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** 0.6s draw
- **Easing:** easeInOutCubic
- **Spec:** A rounded accent rectangle strokes itself around the word, starting from the top-right corner, over 0.6s. Holds, then erases.

### M-375 · Box Outline Draw · Fast
- Variant of M-063. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-063

### M-650 · Box Outline Draw · Boxed
- Variant of M-063. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-063

### M-925 · Box Outline Draw · Slow
- Variant of M-063. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-063

### M-064 · Color Pulse
- **When to use:** A word gently pulses between two colors.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** loop · 1.6s
- **Easing:** easeInOutSine
- **Spec:** The word color eases from white to the accent color and back in a 1.6s loop while it is on screen.

### M-389 · Color Pulse · Fast
- Variant of M-064. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-064

### M-664 · Color Pulse · Boxed
- Variant of M-064. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-064

### M-939 · Color Pulse · Slow
- Variant of M-064. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-064

### M-065 · Glow Pulse
- **When to use:** A word breathes with a soft glow.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** loop · 1.6s
- **Easing:** easeInOutSine
- **Spec:** An accent glow (text shadow, blur up to 6% of the width) grows and fades around the word in a 1.6s loop.

### M-401 · Glow Pulse · Fast
- Variant of M-065. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-065

### M-676 · Glow Pulse · Boxed
- Variant of M-065. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-065

### M-951 · Glow Pulse · Slow
- Variant of M-065. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-065

### M-066 · Wiggle
- **When to use:** A word wiggles to grab attention.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** 0.8s
- **Easing:** easeInOutSine
- **Spec:** The word rotates quickly ±8° and back several times with decreasing angle over about 0.8s, then rests.

### M-413 · Wiggle · Fast
- Variant of M-066. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-066

### M-688 · Wiggle · Boxed
- Variant of M-066. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-066

### M-963 · Wiggle · Slow
- Variant of M-066. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-066

### M-067 · Bounce Word
- **When to use:** A word hops twice, light and fun.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** 0.6s
- **Easing:** easeOutQuad
- **Spec:** The word jumps up 35% of its height and lands, then a second smaller jump of 14%, over about 0.6s.

### M-424 · Bounce Word · Fast
- Variant of M-067. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-067

### M-699 · Bounce Word · Boxed
- Variant of M-067. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-067

### M-974 · Bounce Word · Slow
- Variant of M-067. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-067

### M-068 · Arrow Point
- **When to use:** An arrow points at a word or an object on screen.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** loop · 1s
- **Easing:** easeInOutSine
- **Spec:** An accent arrow sits beside the target and nudges toward it by 30% of its length and back in a 1s loop.

### M-435 · Arrow Point · Fast
- Variant of M-068. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-068

### M-710 · Arrow Point · Boxed
- Variant of M-068. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-068

### M-985 · Arrow Point · Slow
- Variant of M-068. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-068

### M-069 · Zoom Blur Word
- **When to use:** A fast zoom hit on a single word.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** 0.3s
- **Easing:** easeOutExpo
- **Spec:** The word jumps to 160% with a 1.5% blur in 0.2s, then settles at 120% sharp over 0.3s. Return to 100% at the end.

### M-445 · Zoom Blur Word · Fast
- Variant of M-069. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-069

### M-720 · Zoom Blur Word · Boxed
- Variant of M-069. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-069

### M-995 · Zoom Blur Word · Slow
- Variant of M-069. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-069

### M-070 · Rubber Band
- **When to use:** A word squashes and stretches like rubber.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** 0.7s
- **Easing:** easeOut
- **Spec:** The word scales to 125%×75%, then 75%×125%, then smaller swings until it settles at 100% over 0.7s.

### M-454 · Rubber Band · Fast
- Variant of M-070. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-070

### M-729 · Rubber Band · Boxed
- Variant of M-070. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-070

### M-071 · Jello
- **When to use:** A word wobbles like jelly.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** 0.9s
- **Easing:** easeOut
- **Spec:** The word skews on both axes by -12°, then +6°, -3°, +1.5° and settles over 0.9s.

### M-463 · Jello · Fast
- Variant of M-071. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-071

### M-738 · Jello · Boxed
- Variant of M-071. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-071

### M-072 · Heartbeat
- **When to use:** A word pulses like a heartbeat.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** loop · 1.4s
- **Easing:** easeInOut
- **Spec:** Two quick pulses to 130% scale and back (like a heartbeat), then a pause, in a 1.4s loop.

### M-471 · Heartbeat · Fast
- Variant of M-072. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-072

### M-746 · Heartbeat · Boxed
- Variant of M-072. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-072

### M-073 · Marker Scribble
- **When to use:** A zigzag scribble under a word like a marker.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** 0.6s draw
- **Easing:** easeInOutCubic
- **Spec:** A loose zigzag accent stroke draws under the word from the reading-start side over 0.6s, holds, then erases.

### M-479 · Marker Scribble · Fast
- Variant of M-073. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-073

### M-754 · Marker Scribble · Boxed
- Variant of M-073. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-073

### M-074 · Spotlight Dim
- **When to use:** Everything dims except the word or face.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** 0.5s in
- **Easing:** easeInOutCubic
- **Spec:** A dark overlay (about 80% black) fades in over 0.5s with a soft circular hole around the subject, so only the subject stays lit. Fade out to release.

### M-487 · Spotlight Dim · Fast
- Variant of M-074. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-074

### M-762 · Spotlight Dim · Boxed
- Variant of M-074. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-074

### M-075 · Letter Spacing
- **When to use:** An English word spreads its letters for a premium feel.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** 0.8s
- **Easing:** easeInOutCubic
- **Spec:** The letter spacing grows smoothly from 0 to 0.35em over 0.8s while the word stays centered. Reverse at exit.

### M-495 · Letter Spacing · Fast
- Variant of M-075. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-075

### M-770 · Letter Spacing · Boxed
- Variant of M-075. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-075

### M-076 · Flash Hit
- **When to use:** A quick white flash on a strong word or cut.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** 0.15s
- **Easing:** easeOut
- **Spec:** A full-screen white flash rises to 90% opacity in 1–2 frames and fades out over 0.15s, exactly on the beat or word.

### M-503 · Flash Hit · Fast
- Variant of M-076. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-076

### M-778 · Flash Hit · Boxed
- Variant of M-076. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-076

### M-077 · Sparkle Stars
- **When to use:** Sparkles around a word or product for a "fresh" feel.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** loop · 1.2s
- **Easing:** easeInOutSine
- **Spec:** Three to five small four-point stars pop in around the word at random spots, scale 0 to 100% while rotating 90°, then shrink away, staggered by 0.3s.

### M-511 · Sparkle Stars · Fast
- Variant of M-077. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-077

### M-786 · Sparkle Stars · Boxed
- Variant of M-077. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-077

### M-078 · Swing
- **When to use:** A hanging word swings like a sign.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** 1s
- **Easing:** easeOut
- **Spec:** The word swings from its top edge: +16°, -11°, +7°, -4°, +2° and settles over about 1s.

### M-519 · Swing · Fast
- Variant of M-078. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-078

### M-794 · Swing · Boxed
- Variant of M-078. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-078

### M-079 · Tilt Pop
- **When to use:** A word grows with a small tilt, sticker style.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** 0.3s
- **Easing:** easeOutBack
- **Spec:** The word scales to 130% while rotating -8° in 0.3s, settles at 120% and -5°, holds, then returns.

### M-527 · Tilt Pop · Fast
- Variant of M-079. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-079

### M-802 · Tilt Pop · Boxed
- Variant of M-079. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-079

### M-080 · Chromatic Split
- **When to use:** A word splits into red and cyan channels, tech style.
- **Content the user must provide:** text: the word(s) to emphasize
- **Duration:** 0.5s
- **Easing:** easeOut
- **Spec:** Red and cyan copies of the word slide out sideways by 1.5% of the width and back in over 0.5s, like an RGB lens split.

### M-535 · Chromatic Split · Fast
- Variant of M-080. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-080

### M-810 · Chromatic Split · Boxed
- Variant of M-080. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-080

## CAP — Captions

### M-011 · Karaoke Highlight
- **When to use:** The main Reels caption: each word lights up as it is spoken.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** synced to each word
- **Easing:** instant (0.08s fade)
- **Spec:** A full caption line is shown in dimmed white (50% opacity). Each word turns accent color exactly at its spoken timestamp (word-level ASR timings) and stays colored. Bold display font about 64px at 1080 wide, centered, inside the safe zone (y 1350–1550).

### M-278 · Karaoke Highlight · Fast
- Variant of M-011. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-011

### M-553 · Karaoke Highlight · Boxed
- Variant of M-011. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-011

### M-828 · Karaoke Highlight · Slow
- Variant of M-011. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-011

### M-012 · Word Pop
- **When to use:** A fast, lively caption, word by word.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** 0.18s per word
- **Easing:** easeOutBack
- **Spec:** Each word appears at its spoken timestamp, scaling from 30% to 118% and settling to 100% in 0.18s. Earlier words stay. Clear the line when the sentence ends.

### M-292 · Word Pop · Fast
- Variant of M-012. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-012

### M-567 · Word Pop · Boxed
- Variant of M-012. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-012

### M-842 · Word Pop · Slow
- Variant of M-012. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-012

### M-013 · Bounce Caption
- **When to use:** A whole line drops in at once with a playful move.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** 0.55s in
- **Easing:** spring
- **Spec:** The whole caption line enters from 130% below with a spring: overshoot to -14%, rebound to +6%, settle at 0 over about 0.55s. Fade out on exit.

### M-306 · Bounce Caption · Fast
- Variant of M-013. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-013

### M-581 · Bounce Caption · Boxed
- Variant of M-013. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-013

### M-856 · Bounce Caption · Slow
- Variant of M-013. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-013

### M-014 · Boxed Word
- **When to use:** TikTok-style caption where the box follows your voice.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** synced to each word
- **Easing:** easeOutCubic 0.1s
- **Spec:** A rounded accent box sits behind the currently spoken word only, and the word turns dark. When the next word starts, the box jumps to it, with a 6% scale pop. Other words stay white.

### M-320 · Boxed Word · Fast
- Variant of M-014. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-014

### M-595 · Boxed Word · Boxed
- Variant of M-014. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-014

### M-870 · Boxed Word · Slow
- Variant of M-014. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-014

### M-015 · One-Word Caption
- **When to use:** Fast, punchy talk: one big word in the middle.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** one word at a time
- **Easing:** easeOutBack
- **Spec:** Only the current word is on screen, large (about 110px), centered. Each new word replaces the previous one with a quick scale from 60% to 110% to 100% over 0.15s. Optionally color key words in the accent.

### M-334 · One-Word Caption · Fast
- Variant of M-015. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-015

### M-609 · One-Word Caption · Boxed
- Variant of M-015. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-015

### M-884 · One-Word Caption · Slow
- Variant of M-015. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-015

### M-081 · Two-Line Caption
- **When to use:** A long sentence split into two lines that appear in turn.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** 0.45s per line · 0.4s stagger
- **Easing:** easeOutCubic
- **Spec:** Split the sentence into two balanced lines. Each line rises 40px and fades in over 0.45s, the second starting 0.4s after the first. Keep both inside the safe zone.

### M-348 · Two-Line Caption · Fast
- Variant of M-081. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-081

### M-623 · Two-Line Caption · Boxed
- Variant of M-081. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-081

### M-898 · Two-Line Caption · Slow
- Variant of M-081. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-081

### M-082 · Typewriter Caption
- **When to use:** A caption that types itself out with your voice.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** synced to speech
- **Easing:** steps
- **Spec:** The caption reveals character by character from the reading-start side, paced so it finishes when the sentence ends. No caret.

### M-362 · Typewriter Caption · Fast
- Variant of M-082. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-082

### M-637 · Typewriter Caption · Boxed
- Variant of M-082. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-082

### M-912 · Typewriter Caption · Slow
- Variant of M-082. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-082

### M-083 · Fade Words
- **When to use:** A calm caption, each word fades in.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** 0.25s per word
- **Easing:** easeOutQuad
- **Spec:** Each word fades from 0 to 100% opacity over 0.25s at its spoken timestamp. Earlier words stay. Clear the line at the end of the sentence.

### M-376 · Fade Words · Fast
- Variant of M-083. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-083

### M-651 · Fade Words · Boxed
- Variant of M-083. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-083

### M-926 · Fade Words · Slow
- Variant of M-083. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-083

### M-084 · Slide-Up Words
- **When to use:** A lively caption, each word slides up.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** 0.25s per word
- **Easing:** easeOutCubic
- **Spec:** Each word slides up from 60% below its line while fading in over 0.25s at its spoken timestamp.

### M-390 · Slide-Up Words · Fast
- Variant of M-084. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-084

### M-665 · Slide-Up Words · Boxed
- Variant of M-084. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-084

### M-940 · Slide-Up Words · Slow
- Variant of M-084. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-084

### M-085 · Underline Active Word
- **When to use:** A full caption with an underline that follows the spoken word.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** synced to each word
- **Easing:** easeOutCubic 0.1s
- **Spec:** The whole line is visible in white. A rounded accent bar sits under the word being spoken and jumps to the next word at its timestamp.

### M-402 · Underline Active Word · Fast
- Variant of M-085. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-085

### M-677 · Underline Active Word · Boxed
- Variant of M-085. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-085

### M-952 · Underline Active Word · Slow
- Variant of M-085. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-085

### M-086 · Scale Active Word
- **When to use:** The spoken word grows and turns accent.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** synced to each word
- **Easing:** easeOutBack 0.12s
- **Spec:** The word being spoken scales to 125% and turns the accent color; it returns to normal when the next word starts.

### M-414 · Scale Active Word · Fast
- Variant of M-086. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-086

### M-689 · Scale Active Word · Boxed
- Variant of M-086. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-086

### M-964 · Scale Active Word · Slow
- Variant of M-086. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-086

### M-087 · Color Sweep Line
- **When to use:** A color fill sweeps along the whole line as you speak.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** sentence length
- **Easing:** linear
- **Spec:** A two-color gradient is clipped to the caption text and slides from the reading-start side to the end over the sentence duration, so spoken parts turn accent.

### M-425 · Color Sweep Line · Fast
- Variant of M-087. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-087

### M-700 · Color Sweep Line · Boxed
- Variant of M-087. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-087

### M-975 · Color Sweep Line · Slow
- Variant of M-087. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-087

### M-088 · Keyword Color
- **When to use:** A plain caption where only the key word lights up.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** 0.2s
- **Easing:** easeOutBack
- **Spec:** The caption stays white. Only the key word turns accent and scales to 112% at its timestamp, and stays like that until the line clears.

### M-436 · Keyword Color · Fast
- Variant of M-088. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-088

### M-711 · Keyword Color · Boxed
- Variant of M-088. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-088

### M-986 · Keyword Color · Slow
- Variant of M-088. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-088

### M-089 · Pill Caption
- **When to use:** A caption inside a dark pill, readable on any footage.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** 0.3s in
- **Easing:** easeOutBack
- **Spec:** The caption sits inside a dark rounded pill (85% opacity, generous padding). The pill pops from 60% to 105% to 100% over 0.3s.

### M-446 · Pill Caption · Fast
- Variant of M-089. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-089

### M-721 · Pill Caption · Boxed
- Variant of M-089. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-089

### M-996 · Pill Caption · Slow
- Variant of M-089. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-089

### M-090 · Outline Caption
- **When to use:** White caption with a thick black outline, classic and clear.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** 0.45s in
- **Easing:** easeOutCubic
- **Spec:** White bold caption with a black outline about 7% of the font size (stroke painted under the fill), no shadow. Enters with a fade-up.

### M-455 · Outline Caption · Fast
- Variant of M-090. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-090

### M-730 · Outline Caption · Boxed
- Variant of M-090. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-090

### M-091 · Shadow Pop
- **When to use:** A caption with a solid colored drop shadow that pops, pop-art style.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** 0.3s
- **Easing:** easeOutBack
- **Spec:** A solid accent shadow (no blur) grows to 1.2% offset down-right while the text moves 1% up-left, so it looks lifted. Reverse at exit.

### M-464 · Shadow Pop · Fast
- Variant of M-091. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-091

### M-739 · Shadow Pop · Boxed
- Variant of M-091. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-091

### M-092 · Blur Words
- **When to use:** A soft cinematic caption, words resolve from blur.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** 0.3s per word
- **Easing:** easeOutQuad
- **Spec:** Each word goes from 2% blur and opacity 0 to sharp and visible over 0.3s at its spoken timestamp.

### M-472 · Blur Words · Fast
- Variant of M-092. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-092

### M-747 · Blur Words · Boxed
- Variant of M-092. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-092

### M-093 · Drop Words
- **When to use:** Each word drops from above with a small bounce.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** 0.25s per word
- **Easing:** easeOutBack
- **Spec:** Each word drops from 80% above its line, overshoots 10% and settles over 0.25s at its spoken timestamp.

### M-480 · Drop Words · Fast
- Variant of M-093. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-093

### M-755 · Drop Words · Boxed
- Variant of M-093. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-093

### M-094 · Rotate Words
- **When to use:** Words twist in, lively and playful.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** 0.3s per word
- **Easing:** easeOutBack
- **Spec:** Each word rotates in from -25° and 50% scale to upright and full size over 0.3s at its spoken timestamp.

### M-488 · Rotate Words · Fast
- Variant of M-094. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-094

### M-763 · Rotate Words · Boxed
- Variant of M-094. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-094

### M-095 · Highlighter Active
- **When to use:** A highlighter sweeps over each spoken word.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** synced to each word
- **Easing:** easeOutCubic 0.15s
- **Spec:** An accent highlight box grows behind the spoken word from the reading-start side over 0.15s and disappears when the next word starts.

### M-496 · Highlighter Active · Fast
- Variant of M-095. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-095

### M-771 · Highlighter Active · Boxed
- Variant of M-095. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-095

### M-096 · Size Mix
- **When to use:** A caption where important words are bigger.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** 0.2s per word
- **Easing:** easeOutBack
- **Spec:** Words pop in one by one (M-012 style), but key words are set 1.6× larger and in the accent color, so the line reads like a poster.

### M-504 · Size Mix · Fast
- Variant of M-096. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-096

### M-779 · Size Mix · Boxed
- Variant of M-096. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-096

### M-097 · Speaker Label
- **When to use:** When several people talk, the name tag sits above the caption.
- **Content the user must provide:** text: the name and role
- **Duration:** 0.3s
- **Easing:** easeOutCubic
- **Spec:** A small accent tag with the speaker name slides in above the caption 0.1s before the line, then the caption fades up under it.

### M-512 · Speaker Label · Fast
- Variant of M-097. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-097

### M-787 · Speaker Label · Boxed
- Variant of M-097. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-097

### M-098 · Bottom Bar Caption
- **When to use:** A caption inside a wide bottom bar, like the news.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** 0.4s bar · 0.3s text
- **Easing:** easeOutExpo
- **Spec:** A dark full-width bar grows from the right edge (0.4s), then the caption fades in inside it (0.3s). Text and bar retract at the end.

### M-520 · Bottom Bar Caption · Fast
- Variant of M-098. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-098

### M-795 · Bottom Bar Caption · Boxed
- Variant of M-098. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-098

### M-099 · Glitch Caption
- **When to use:** A tech caption that glitches as it lands.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** 0.4s glitch
- **Easing:** steps
- **Spec:** The caption enters with a 0.4s glitch burst: red and cyan copies jitter through random slice masks, then the line snaps clean (see M-010).

### M-528 · Glitch Caption · Fast
- Variant of M-099. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-099

### M-803 · Glitch Caption · Boxed
- Variant of M-099. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-099

### M-100 · Progress Caption
- **When to use:** A caption with a thin progress bar filling for the sentence.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** sentence length
- **Easing:** linear
- **Spec:** Under the caption, a thin rounded accent bar fills from the reading-start side across the sentence duration, showing how long the line lasts.

### M-536 · Progress Caption · Fast
- Variant of M-100. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-100

### M-811 · Progress Caption · Boxed
- Variant of M-100. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-100

### M-272 · Bilingual Caption
- **When to use:** Arabic on top and English below, for a wider audience.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** synced
- **Easing:** easeOutCubic
- **Spec:** Show the Arabic caption in the main style and its English translation under it in a smaller lighter line; both enter together.

### M-542 · Bilingual Caption · Fast
- Variant of M-272. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-272

### M-817 · Bilingual Caption · Boxed
- Variant of M-272. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-272

### M-273 · Text on Path
- **When to use:** Text flowing along a curved path.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** loop
- **Easing:** linear
- **Spec:** Lay the caption along a curved SVG path and slide its start offset so the words travel along the curve.

### M-544 · Text on Path · Fast
- Variant of M-273. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-273

### M-819 · Text on Path · Boxed
- Variant of M-273. put a thick solid dark teal #102E33 backing stroke (about 1.2% of the frame width, rounded joins) around the letters so the white text sits on a dark teal shape.
- **Content the user must provide:** same as M-273

### M-274 · Full-Screen Kinetic
- **When to use:** Huge words that swap and fill the whole screen.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** per word
- **Easing:** cut
- **Spec:** Each word fills most of the frame in a bold display font and replaces the previous one on its timestamp, alternating background and text colors.

### M-546 · Full-Screen Kinetic · Fast
- Variant of M-274. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-274

### M-821 · Full-Screen Kinetic · Boxed
- Variant of M-274. inset the full-screen card about 6% from the frame edges with rounded corners (about 5% radius) and a dark teal #102E33 outer border, instead of filling the whole frame.
- **Content the user must provide:** same as M-274

### M-275 · Tagged Caption
- **When to use:** The first word sits in a colored tag, the rest plain.
- **Content the user must provide:** It comes from your voice automatically, so you type nothing.
- **Duration:** 0.3s
- **Easing:** easeOutBack
- **Spec:** The caption pops in (M-089) with its first word inside a small accent box, like a label, followed by the rest of the line.

### M-548 · Tagged Caption · Fast
- Variant of M-275. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-275

### M-823 · Tagged Caption · Boxed
- Variant of M-275. put the text inside a solid dark teal #102E33 box with rounded corners and white text. Any accent effect of the motion stays on top of it.
- **Content the user must provide:** same as M-275

## TRN — Transitions

### M-016 · Circle Reveal
- **When to use:** Swap the background or scene from a point, like your finger or face.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.6s
- **Easing:** easeOutCubic
- **Spec:** The new scene is revealed through a circular mask that grows from a chosen point (e.g. a fingertip) from radius 0 to full-frame diagonal over 0.6s, with a 30px soft edge. A thin accent ring expands just ahead of the edge and fades out.

### M-279 · Circle Reveal · Fast
- Variant of M-016. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-016

### M-554 · Circle Reveal · Slow
- Variant of M-016. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-016

### M-829 · Circle Reveal · Gold
- Variant of M-016. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-016

### M-017 · Linear Wipe
- **When to use:** A clear transition between two clips or places.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.5s
- **Easing:** easeInOutCubic
- **Spec:** The new scene wipes in across the frame behind a moving vertical edge over 0.5s. The edge has a white 4px line with an accent glow.

### M-293 · Linear Wipe · Fast
- Variant of M-017. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-017

### M-568 · Linear Wipe · Slow
- Variant of M-017. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-017

### M-843 · Linear Wipe · Gold
- Variant of M-017. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-017

### M-018 · Light Sweep
- **When to use:** A magic change, like "look how it changed".
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.7s
- **Easing:** easeInOutSine
- **Spec:** A bright warm diagonal light band (about 15% of the frame wide, angled 105°) sweeps across the frame over 0.7s. The scene swaps to the new one exactly as the band passes the center.

### M-307 · Light Sweep · Fast
- Variant of M-018. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-018

### M-582 · Light Sweep · Slow
- Variant of M-018. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-018

### M-857 · Light Sweep · Gold
- Variant of M-018. add a thin gold #FFC857 light streak (about 1.2% wide) that sweeps across the frame at the moment of the transition.
- **Content the user must provide:** same as M-018

### M-019 · Zoom Blur
- **When to use:** A fast, punchy cut between two clips.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.4s out · 0.4s in
- **Easing:** easeInExpo / easeOutExpo
- **Spec:** The outgoing clip scales to 170% with a radial blur of about 10px and fades out over 0.4s (easeInExpo). The incoming clip starts at 160% blurred and settles to 100% sharp over 0.4s (easeOutExpo).

### M-321 · Zoom Blur · Fast
- Variant of M-019. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-019

### M-596 · Zoom Blur · Slow
- Variant of M-019. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-019

### M-871 · Zoom Blur · Gold
- Variant of M-019. add a thin gold #FFC857 light streak (about 1.2% wide) that sweeps across the frame at the moment of the transition.
- **Content the user must provide:** same as M-019

### M-020 · Whip Pan
- **When to use:** Cut between two shots as if the camera spun.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.35s
- **Easing:** easeInOutQuart
- **Spec:** The outgoing clip slides out to one side with heavy horizontal motion blur, and the incoming clip slides in from the opposite side over 0.35s total. Add a fast "whoosh" sound.

### M-335 · Whip Pan · Fast
- Variant of M-020. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-020

### M-610 · Whip Pan · Slow
- Variant of M-020. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-020

### M-885 · Whip Pan · Gold
- Variant of M-020. add a thin gold #FFC857 light streak (about 1.2% wide) that sweeps across the frame at the moment of the transition.
- **Content the user must provide:** same as M-020

### M-101 · Fade Through Black
- **When to use:** A calm transition through a moment of black.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.3s out · 0.3s in
- **Easing:** easeInOutSine
- **Spec:** The outgoing clip fades to full black over 0.3s, holds black for 2–4 frames, then the new clip fades in from black over 0.3s.

### M-349 · Fade Through Black · Fast
- Variant of M-101. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-101

### M-624 · Fade Through Black · Slow
- Variant of M-101. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-101

### M-899 · Fade Through Black · Gold
- Variant of M-101. add a thin gold #FFC857 light streak (about 1.2% wide) that sweeps across the frame at the moment of the transition.
- **Content the user must provide:** same as M-101

### M-102 · Cross Dissolve
- **When to use:** The classic soft blend from one shot into the next.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.5s
- **Easing:** linear
- **Spec:** The new clip fades in on top of the old one from 0 to 100% over 0.5s while both play.

### M-363 · Cross Dissolve · Fast
- Variant of M-102. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-102

### M-638 · Cross Dissolve · Slow
- Variant of M-102. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-102

### M-913 · Cross Dissolve · Gold
- Variant of M-102. add a thin gold #FFC857 light streak (about 1.2% wide) that sweeps across the frame at the moment of the transition.
- **Content the user must provide:** same as M-102

### M-103 · Slide Push
- **When to use:** The new shot pushes the old one off screen.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.45s
- **Easing:** easeInOutQuart
- **Spec:** The new clip slides in from the right edge while pushing the old clip out to the left at the same speed over 0.45s.

### M-377 · Slide Push · Fast
- Variant of M-103. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-103

### M-652 · Slide Push · Slow
- Variant of M-103. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-103

### M-927 · Slide Push · Gold
- Variant of M-103. add a thin gold #FFC857 light streak (about 1.2% wide) that sweeps across the frame at the moment of the transition.
- **Content the user must provide:** same as M-103

### M-104 · Diagonal Wipe
- **When to use:** A slanted wipe, livelier than a straight one.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.5s
- **Easing:** easeInOutCubic
- **Spec:** The new clip is revealed behind a soft-edged diagonal line (135°) that travels from the top-left corner to the bottom-right over 0.5s.

### M-391 · Diagonal Wipe · Fast
- Variant of M-104. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-104

### M-666 · Diagonal Wipe · Slow
- Variant of M-104. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-104

### M-941 · Diagonal Wipe · Gold
- Variant of M-104. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-104

### M-105 · Iris Close/Open
- **When to use:** A circle closes on one shot and opens on the next, old-film style.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.4s close · 0.4s open
- **Easing:** easeInOutCubic
- **Spec:** A circular mask shrinks to zero on the face of the outgoing clip (0.4s), then the new clip opens from the same point with a growing circle (0.4s). Black between.

### M-403 · Iris Close/Open · Fast
- Variant of M-105. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-105

### M-678 · Iris Close/Open · Slow
- Variant of M-105. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-105

### M-953 · Iris Close/Open · Gold
- Variant of M-105. add a thin gold #FFC857 light streak (about 1.2% wide) that sweeps across the frame at the moment of the transition.
- **Content the user must provide:** same as M-105

### M-106 · Clock Wipe
- **When to use:** The new shot sweeps in like a clock hand.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.6s
- **Easing:** easeInOutSine
- **Spec:** The new clip is revealed by a radial sweep around the center, starting at 12 o clock and going clockwise a full 360° over 0.6s.

### M-415 · Clock Wipe · Fast
- Variant of M-106. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-106

### M-690 · Clock Wipe · Slow
- Variant of M-106. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-106

### M-965 · Clock Wipe · Gold
- Variant of M-106. add a thin gold #FFC857 light streak (about 1.2% wide) that sweeps across the frame at the moment of the transition.
- **Content the user must provide:** same as M-106

### M-107 · Blinds
- **When to use:** The new shot opens through vertical blinds.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.5s
- **Easing:** easeInOutCubic
- **Spec:** The frame is split into 6 vertical strips. Each strip reveals the new clip by growing from its right edge to full width over 0.5s.

### M-426 · Blinds · Fast
- Variant of M-107. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-107

### M-701 · Blinds · Slow
- Variant of M-107. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-107

### M-976 · Blinds · Gold
- Variant of M-107. add a thin gold #FFC857 light streak (about 1.2% wide) that sweeps across the frame at the moment of the transition.
- **Content the user must provide:** same as M-107

### M-108 · Split Doors
- **When to use:** The shot splits in half and opens like doors.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.6s
- **Easing:** easeInOutQuart
- **Spec:** The outgoing clip is cut down the middle; the two halves slide apart to the left and right over 0.6s, revealing the new clip behind them.

### M-437 · Split Doors · Fast
- Variant of M-108. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-108

### M-712 · Split Doors · Slow
- Variant of M-108. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-108

### M-987 · Split Doors · Gold
- Variant of M-108. add a thin gold #FFC857 light streak (about 1.2% wide) that sweeps across the frame at the moment of the transition.
- **Content the user must provide:** same as M-108

### M-109 · Diamond Reveal
- **When to use:** The new shot opens from a growing diamond.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.6s
- **Easing:** easeOutCubic
- **Spec:** The new clip is revealed through a diamond-shaped mask that grows from the face point until it covers the frame over 0.6s.

### M-447 · Diamond Reveal · Fast
- Variant of M-109. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-109

### M-722 · Diamond Reveal · Slow
- Variant of M-109. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-109

### M-997 · Diamond Reveal · Gold
- Variant of M-109. add a thin gold #FFC857 light streak (about 1.2% wide) that sweeps across the frame at the moment of the transition.
- **Content the user must provide:** same as M-109

### M-110 · Glitch Transition
- **When to use:** A glitchy cut, great for cyber content.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.4s
- **Easing:** steps
- **Spec:** For 0.4s the new clip flashes in through random horizontal slices with ±8% offsets, changing every 2 frames, then locks in clean. Add a digital noise sound.

### M-456 · Glitch Transition · Fast
- Variant of M-110. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-110

### M-731 · Glitch Transition · Slow
- Variant of M-110. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-110

### M-111 · Spin Transition
- **When to use:** The old shot spins out, the new one spins in.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.5s
- **Easing:** easeInOutCubic
- **Spec:** The outgoing clip rotates 180° while shrinking to 20% and fading out; the new clip rotates in from -180° and 20% to full size over 0.5s.

### M-465 · Spin Transition · Fast
- Variant of M-111. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-111

### M-740 · Spin Transition · Slow
- Variant of M-111. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-111

### M-112 · Flash White
- **When to use:** A cut hidden in a white flash, bold and sudden.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.25s
- **Easing:** easeOut
- **Spec:** A full white flash peaks in 2 frames exactly on the cut, then fades over 0.25s to reveal the new clip.

### M-473 · Flash White · Fast
- Variant of M-112. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-112

### M-748 · Flash White · Slow
- Variant of M-112. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-112

### M-113 · Color Flash
- **When to use:** A cut hidden in a brand-color flash.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.3s
- **Easing:** easeOut
- **Spec:** Same as M-112 but the flash is the brand accent color at 90% opacity.

### M-481 · Color Flash · Fast
- Variant of M-113. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-113

### M-756 · Color Flash · Slow
- Variant of M-113. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-113

### M-114 · Corner Reveal
- **When to use:** The new shot grows in from a corner.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.6s
- **Easing:** easeOutCubic
- **Spec:** The new clip is revealed through a circle that grows from the bottom-left corner until it covers the frame over 0.6s.

### M-489 · Corner Reveal · Fast
- Variant of M-114. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-114

### M-764 · Corner Reveal · Slow
- Variant of M-114. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-114

### M-115 · Cube Rotate
- **When to use:** The two shots act as faces of a rotating cube.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.6s
- **Easing:** easeInOutCubic
- **Spec:** With 3D perspective, the outgoing clip rotates 90° away on its left edge while the new clip rotates in from -90° on its right edge, like a turning cube, over 0.6s.

### M-497 · Cube Rotate · Fast
- Variant of M-115. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-115

### M-772 · Cube Rotate · Slow
- Variant of M-115. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-115

### M-116 · Zoom Through
- **When to use:** The camera dives into one shot and comes out in the next.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.5s
- **Easing:** easeInExpo / easeOutCubic
- **Spec:** The outgoing clip scales to 400% and fades out quickly (0.3s); the new clip grows from 60% to 100% while fading in (0.3s), overlapping slightly.

### M-505 · Zoom Through · Fast
- Variant of M-116. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-116

### M-780 · Zoom Through · Slow
- Variant of M-116. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-116

### M-117 · Strip Slide
- **When to use:** The new shot slides in as horizontal strips, one after another.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.5s · 0.06s stagger
- **Easing:** easeOutQuart
- **Spec:** The new clip is cut into 5 horizontal strips; each strip slides in from the right over 0.5s, starting 0.06s after the one above it.

### M-513 · Strip Slide · Fast
- Variant of M-117. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-117

### M-788 · Strip Slide · Slow
- Variant of M-117. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-117

### M-118 · Light Leak
- **When to use:** A warm light leak washes over the cut, film style.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.8s
- **Easing:** easeInOutSine
- **Spec:** Warm orange and red light blobs (screen blend) drift across the frame over 0.8s; the cut to the new clip happens at the brightest moment.

### M-521 · Light Leak · Fast
- Variant of M-118. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-118

### M-796 · Light Leak · Slow
- Variant of M-118. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-118

### M-119 · Smooth Cut
- **When to use:** A cut between similar shots that hides the jump.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.3s
- **Easing:** easeOutQuad
- **Spec:** The new clip fades in over 0.3s while scaling from 105% to 100%, which hides small position jumps between two similar takes.

### M-529 · Smooth Cut · Fast
- Variant of M-119. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-119

### M-804 · Smooth Cut · Slow
- Variant of M-119. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-119

### M-120 · Swipe Up
- **When to use:** Like swiping a story up to the next clip.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.4s
- **Easing:** easeInOutQuart
- **Spec:** The outgoing clip slides up out of the top edge while the new clip slides up from the bottom edge at the same speed over 0.4s.

### M-537 · Swipe Up · Fast
- Variant of M-120. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-120

### M-812 · Swipe Up · Slow
- Variant of M-120. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-120

### M-267 · Shape Morph
- **When to use:** A shape morphs smoothly into another.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.6s
- **Easing:** easeInOutCubic
- **Spec:** Interpolate between shapes (circle → rounded square → leaf) by animating corner radii and rotation, or by morphing matching SVG paths.

### M-543 · Shape Morph · Fast
- Variant of M-267. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-267

### M-818 · Shape Morph · Slow
- Variant of M-267. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-267

### M-268 · Liquid Reveal
- **When to use:** A liquid blob grows to cover the cut.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.7s
- **Easing:** easeInOutCubic
- **Spec:** An organic blob shape in the accent color grows from the center while its border radius wobbles, covers the frame, then fades to reveal the new clip.

### M-545 · Liquid Reveal · Fast
- Variant of M-268. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-268

### M-820 · Liquid Reveal · Slow
- Variant of M-268. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-268

### M-269 · Ink Splash Reveal
- **When to use:** The new shot appears through growing ink splashes.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.7s
- **Easing:** easeOutCubic
- **Spec:** Reveal the new clip through a mask of several overlapping circles (ink splash shape) that scales up from the center to cover the frame.

### M-547 · Ink Splash Reveal · Fast
- Variant of M-269. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-269

### M-822 · Ink Splash Reveal · Slow
- Variant of M-269. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-269

### M-270 · Film Burn
- **When to use:** A hot film-burn flare hides the cut.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.8s
- **Easing:** easeInOutSine
- **Spec:** A bright white-yellow-orange burn blob expands from one corner (screen blend), peaks at full brightness on the cut, then fades.

### M-549 · Film Burn · Fast
- Variant of M-270. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-270

### M-824 · Film Burn · Slow
- Variant of M-270. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-270

### M-271 · Match Cut Slide
- **When to use:** A movement in one shot continues in the next.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.5s
- **Easing:** easeInOutCubic
- **Spec:** Cut on the motion: the outgoing clip moves out in the direction of the action and the incoming clip continues the same direction and speed.

### M-550 · Match Cut Slide · Fast
- Variant of M-271. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-271

### M-825 · Match Cut Slide · Slow
- Variant of M-271. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-271

## CAM — Camera

### M-021 · Punch-In
- **When to use:** Hides cuts between lines, or stresses a line.
- **Content the user must provide:** No content needed from you.
- **Duration:** instant (1 frame)
- **Easing:** cut
- **Spec:** The frame jumps instantly from 100% to 125% scale, centered on the face, on a cut or a key word. Hold, then jump back to 100% on the next cut. No easing.

### M-280 · Punch-In · Fast
- Variant of M-021. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-021

### M-555 · Punch-In · Slow
- Variant of M-021. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-021

### M-830 · Punch-In · Gold
- Variant of M-021. apply a warm gold #FFC857 color tint (about 8% opacity, soft-light) on the footage for the length of the move.
- **Content the user must provide:** same as M-021

### M-022 · Slow Push-In
- **When to use:** A serious moment or a story.
- **Content the user must provide:** No content needed from you.
- **Duration:** whole shot (3–6s)
- **Easing:** linear / easeInOutSine
- **Spec:** The frame scales smoothly from 100% to about 116% across the whole shot, centered slightly above the face.

### M-294 · Slow Push-In · Fast
- Variant of M-022. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-022

### M-569 · Slow Push-In · Slow
- Variant of M-022. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-022

### M-844 · Slow Push-In · Gold
- Variant of M-022. apply a warm gold #FFC857 color tint (about 8% opacity, soft-light) on the footage for the length of the move.
- **Content the user must provide:** same as M-022

### M-023 · Camera Shake
- **When to use:** With a hit, an explosion or a strong word.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.3–1s
- **Easing:** noise
- **Spec:** Overscale the frame to 108% to hide the edges, then shift it with random ±1.5% offsets and ±0.8° rotation, changing every 2–3 frames. Damp the shake toward the end.

### M-308 · Camera Shake · Fast
- Variant of M-023. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-023

### M-583 · Camera Shake · Slow
- Variant of M-023. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-023

### M-858 · Camera Shake · Gold
- Variant of M-023. apply a warm gold #FFC857 color tint (about 8% opacity, soft-light) on the footage for the length of the move.
- **Content the user must provide:** same as M-023

### M-024 · Zoom-Out Card
- **When to use:** Like "zoom out", or to show something next to the video.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.6s out · 0.5s back
- **Easing:** easeInOutCubic + bounce
- **Spec:** The whole video shrinks to 60% scale with -3° tilt, about 48px rounded corners and a deep drop shadow over a dark patterned backdrop (0.6s). Hold, then it returns to full frame with a small 104% overshoot (0.5s).

### M-322 · Zoom-Out Card · Fast
- Variant of M-024. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-024

### M-597 · Zoom-Out Card · Slow
- Variant of M-024. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-024

### M-872 · Zoom-Out Card · Gold
- Variant of M-024. apply a warm gold #FFC857 color tint (about 8% opacity, soft-light) on the footage for the length of the move.
- **Content the user must provide:** same as M-024

### M-025 · Ken Burns
- **When to use:** Bring a still photo to life.
- **Content the user must provide:** file: the image(s)
- **Duration:** whole shot (4–8s)
- **Easing:** easeInOutSine
- **Spec:** A still image slowly scales from 112% to 132% while panning diagonally by about 10% of the frame across the whole duration.

### M-336 · Ken Burns · Fast
- Variant of M-025. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-025

### M-611 · Ken Burns · Slow
- Variant of M-025. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-025

### M-886 · Ken Burns · Gold
- Variant of M-025. apply a warm gold #FFC857 color tint (about 8% opacity, soft-light) on the footage for the length of the move.
- **Content the user must provide:** same as M-025

### M-121 · Dolly Zoom
- **When to use:** The background stretches while you stay put, a shock or realization.
- **Content the user must provide:** No content needed from you.
- **Duration:** 1–2s
- **Easing:** easeInOutSine
- **Spec:** Using the person matte, scale the background layer from 100% to about 150% while scaling the person layer from 100% to about 86% from the bottom center, so the subject seems fixed while the room warps.

### M-350 · Dolly Zoom · Fast
- Variant of M-121. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-121

### M-625 · Dolly Zoom · Slow
- Variant of M-121. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-121

### M-900 · Dolly Zoom · Gold
- Variant of M-121. apply a warm gold #FFC857 color tint (about 8% opacity, soft-light) on the footage for the length of the move.
- **Content the user must provide:** same as M-121

### M-122 · Pan
- **When to use:** Moves the frame left and right across a shot or photo.
- **Content the user must provide:** No content needed from you.
- **Duration:** 2–4s
- **Easing:** easeInOutSine
- **Spec:** Overscale the frame to 125% and move it horizontally from +8% to -8% of the width across the shot.

### M-364 · Pan · Fast
- Variant of M-122. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-122

### M-639 · Pan · Slow
- Variant of M-122. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-122

### M-914 · Pan · Gold
- Variant of M-122. apply a warm gold #FFC857 color tint (about 8% opacity, soft-light) on the footage for the length of the move.
- **Content the user must provide:** same as M-122

### M-123 · Tilt Up
- **When to use:** The frame moves bottom to top, like revealing a person or building.
- **Content the user must provide:** No content needed from you.
- **Duration:** 2–4s
- **Easing:** easeInOutSine
- **Spec:** Overscale the frame to 125% and move it vertically from +9% to -7% of the height across the shot.

### M-378 · Tilt Up · Fast
- Variant of M-123. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-123

### M-653 · Tilt Up · Slow
- Variant of M-123. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-123

### M-928 · Tilt Up · Gold
- Variant of M-123. apply a warm gold #FFC857 color tint (about 8% opacity, soft-light) on the footage for the length of the move.
- **Content the user must provide:** same as M-123

### M-124 · Rack Focus
- **When to use:** Focus shifts between the person and the background.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.6s
- **Easing:** easeInOutCubic
- **Spec:** Using the person matte, blur the background from 0 to about 1.2% while the person goes from 1.2% blur to sharp over 0.6s, or the reverse.

### M-392 · Rack Focus · Fast
- Variant of M-124. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-124

### M-667 · Rack Focus · Slow
- Variant of M-124. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-124

### M-942 · Rack Focus · Gold
- Variant of M-124. apply a warm gold #FFC857 color tint (about 8% opacity, soft-light) on the footage for the length of the move.
- **Content the user must provide:** same as M-124

### M-125 · Whip Zoom
- **When to use:** A quick zoom with motion blur onto the face.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.25s
- **Easing:** easeOutExpo
- **Spec:** Scale the frame to 150% with about 1.2% motion blur in 0.15s, then settle to 130% and sharp over 0.2s. Pair with a short whoosh.

### M-404 · Whip Zoom · Fast
- Variant of M-125. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-125

### M-679 · Whip Zoom · Slow
- Variant of M-125. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-125

### M-954 · Whip Zoom · Gold
- Variant of M-125. apply a warm gold #FFC857 color tint (about 8% opacity, soft-light) on the footage for the length of the move.
- **Content the user must provide:** same as M-125

### M-126 · Handheld Drift
- **When to use:** Makes a locked-off shot feel handheld.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop · 4s
- **Easing:** easeInOutSine
- **Spec:** Overscale to 108% and drift the frame slowly with small offsets (±1.2%) and rotation (±0.5°) on a smooth 4s path.

### M-416 · Handheld Drift · Fast
- Variant of M-126. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-126

### M-691 · Handheld Drift · Slow
- Variant of M-126. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-126

### M-966 · Handheld Drift · Gold
- Variant of M-126. apply a warm gold #FFC857 color tint (about 8% opacity, soft-light) on the footage for the length of the move.
- **Content the user must provide:** same as M-126

### M-127 · Dutch Tilt
- **When to use:** Tilting the frame adds tension or unease.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.5s
- **Easing:** easeInOutCubic
- **Spec:** Rotate the frame to -9° while scaling to 120% to hide the corners over 0.5s, hold, then return.

### M-427 · Dutch Tilt · Fast
- Variant of M-127. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-127

### M-702 · Dutch Tilt · Slow
- Variant of M-127. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-127

### M-977 · Dutch Tilt · Gold
- Variant of M-127. apply a warm gold #FFC857 color tint (about 8% opacity, soft-light) on the footage for the length of the move.
- **Content the user must provide:** same as M-127

### M-128 · Snap Zoom Out
- **When to use:** Starts close then snaps wide to show the whole scene.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.2s
- **Easing:** easeOutExpo
- **Spec:** Start at 150% on a detail, then snap out to 100% in about 0.2s on a beat or word.

### M-438 · Snap Zoom Out · Fast
- Variant of M-128. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-128

### M-713 · Snap Zoom Out · Slow
- Variant of M-128. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-128

### M-988 · Snap Zoom Out · Gold
- Variant of M-128. apply a warm gold #FFC857 color tint (about 8% opacity, soft-light) on the footage for the length of the move.
- **Content the user must provide:** same as M-128

### M-129 · Crash Zoom
- **When to use:** A hard zoom onto the face with a shake, for surprise.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.2s + 0.3s shake
- **Easing:** easeOutExpo
- **Spec:** Snap the frame to about 190% centered on the face in 0.15s, add a short horizontal shake (±1.5%), then hold. Pair with a dramatic hit.

### M-448 · Crash Zoom · Fast
- Variant of M-129. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-129

### M-723 · Crash Zoom · Slow
- Variant of M-129. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-129

### M-998 · Crash Zoom · Gold
- Variant of M-129. apply a warm gold #FFC857 color tint (about 8% opacity, soft-light) on the footage for the length of the move.
- **Content the user must provide:** same as M-129

### M-130 · Orbit
- **When to use:** Feels like the camera is circling you slightly.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop · 4s
- **Easing:** easeInOutSine
- **Spec:** Apply a 3D Y-axis rotation of ±14° with perspective and a 112% scale, swinging smoothly every 4s.

### M-457 · Orbit · Fast
- Variant of M-130. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-130

### M-732 · Orbit · Slow
- Variant of M-130. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-130

### M-131 · Double Punch
- **When to use:** Two punch-ins in a row for strong emphasis.
- **Content the user must provide:** No content needed from you.
- **Duration:** 2 cuts
- **Easing:** cut
- **Spec:** Jump to 115% on the first beat and to 132% on the second, with no easing, then cut back to 100%.

### M-466 · Double Punch · Fast
- Variant of M-131. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-131

### M-741 · Double Punch · Slow
- Variant of M-131. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-131

### M-132 · Split Screen
- **When to use:** Shows two shots side by side, like a comparison.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.5s in
- **Easing:** easeOutCubic
- **Spec:** Two clips slide in from the left and right edges into each half of the frame over 0.5s, with a thin gap between them.

### M-474 · Split Screen · Fast
- Variant of M-132. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-132

### M-749 · Split Screen · Slow
- Variant of M-132. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-132

### M-133 · Picture in Picture
- **When to use:** A small video in the corner, like a reaction cam.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.4s in
- **Easing:** easeOutBack
- **Spec:** A rounded window with a white border and shadow (about 38% of the width) pops into the top corner from scale 0 over 0.4s and plays the second clip.

### M-482 · Picture in Picture · Fast
- Variant of M-133. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-133

### M-757 · Picture in Picture · Slow
- Variant of M-133. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-133

### M-134 · Mirror Flip
- **When to use:** The frame flips horizontally, like "the opposite is true".
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.5s
- **Easing:** easeInOutCubic
- **Spec:** Flip the frame horizontally (scaleX from 1 to -1) over 0.5s, hold, then flip back.

### M-490 · Mirror Flip · Fast
- Variant of M-134. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-134

### M-765 · Mirror Flip · Slow
- Variant of M-134. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-134

### M-135 · Freeze Frame
- **When to use:** The shot freezes with muted color and a tag.
- **Content the user must provide:** text: the text to show
- **Duration:** hold 1–2s
- **Easing:** cut
- **Spec:** On the chosen frame, hold the image, desaturate it about 85% with a little more contrast, and pop a small label tag. Resume playback after the hold.

### M-498 · Freeze Frame · Fast
- Variant of M-135. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-135

### M-773 · Freeze Frame · Slow
- Variant of M-135. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-135

### M-136 · Slow Motion
- **When to use:** An important moment slows down so viewers catch it.
- **Content the user must provide:** No content needed from you.
- **Duration:** ramp 0.2s
- **Easing:** easeOutCubic
- **Spec:** Ramp the clip speed from 100% down to about 25% over 0.2s at the key moment (use frame blending or interpolation), hold, then ramp back.

### M-506 · Slow Motion · Fast
- Variant of M-136. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-136

### M-781 · Slow Motion · Slow
- Variant of M-136. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-136

### M-137 · Speed Ramp
- **When to use:** Motion slows then speeds up suddenly, action style.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.8s
- **Easing:** custom curve
- **Spec:** Combine a slow push (100% to 104%) with a sudden fast push to 130% in about 0.15s, then ease into a slow drift. Time the fast part to the beat.

### M-514 · Speed Ramp · Fast
- Variant of M-137. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-137

### M-789 · Speed Ramp · Slow
- Variant of M-137. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-137

### M-138 · Letterbox Bars
- **When to use:** Black bars top and bottom for a film look.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.5s in
- **Easing:** easeInOutCubic
- **Spec:** Two black bars slide in from the top and bottom edges over 0.5s, each about 16% of the width tall, and stay during the cinematic part.

### M-522 · Letterbox Bars · Fast
- Variant of M-138. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-138

### M-797 · Letterbox Bars · Slow
- Variant of M-138. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-138

### M-139 · Vignette Focus
- **When to use:** The edges darken so the eye goes to the face.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.6s in
- **Easing:** easeInOutSine
- **Spec:** Fade in an elliptical dark vignette (transparent center, about 90% black at the edges) over 0.6s around the face.

### M-530 · Vignette Focus · Fast
- Variant of M-139. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-139

### M-805 · Vignette Focus · Slow
- Variant of M-139. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-139

### M-140 · Bounce Zoom
- **When to use:** A zoom that bounces a little before settling.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.5s
- **Easing:** spring
- **Spec:** Zoom to 132%, bounce back to 116%, then 124%, and settle at 122% over about 0.5s.

### M-538 · Bounce Zoom · Fast
- Variant of M-140. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-140

### M-813 · Bounce Zoom · Slow
- Variant of M-140. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-140

## FX — Effects

### M-026 · Particle Dissolve
- **When to use:** A logo or object breaks apart and vanishes, like a finger snap.
- **Content the user must provide:** No content needed from you.
- **Duration:** 1.2s
- **Easing:** easeOutQuad
- **Spec:** The object breaks into 150–400 small particles sampled from its own pixels. Each particle flies outward on a random vector (60–250px) with slight upward drift, shrinks and fades out over 1.2s. The original disappears in the first 0.1s.

### M-281 · Particle Dissolve · Fast
- Variant of M-026. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-026

### M-556 · Particle Dissolve · Slow
- Variant of M-026. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-026

### M-831 · Particle Dissolve · Gold
- Variant of M-026. color the effect elements (particles, flare, dust) gold #FFC857 instead of white.
- **Content the user must provide:** same as M-026

### M-027 · Shockwave
- **When to use:** With a finger snap or a tap.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.8s
- **Easing:** easeOutCubic
- **Spec:** From the tap point, a white flash dot pops in and out (0.25s), then two accent rings expand from 0 to about 3.5x and fade, 0.12s apart. Optionally add a slight refraction on the video under the rings.

### M-295 · Shockwave · Fast
- Variant of M-027. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-027

### M-570 · Shockwave · Slow
- Variant of M-027. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-027

### M-845 · Shockwave · Gold
- Variant of M-027. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-027

### M-028 · Pulse Rings
- **When to use:** Behind your head when you talk about something important.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop · 1s per ring
- **Easing:** linear
- **Spec:** Concentric accent rings spawn behind the person (on the background layer, masked by the person matte) every 1/3 of the loop, expanding from 50% to 300% and fading to 0.

### M-309 · Pulse Rings · Fast
- Variant of M-028. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-028

### M-584 · Pulse Rings · Slow
- Variant of M-028. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-028

### M-859 · Pulse Rings · Gold
- Variant of M-028. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-028

### M-029 · Light Rays
- **When to use:** A "wow" moment or a new announcement.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop · 8s per turn
- **Easing:** linear
- **Spec:** Soft accent-colored rays (conic gradient, 6° rays every 22°) rotate slowly behind the person. A radial mask fades them out at about 45% radius. Place them on the layer behind the person matte.

### M-323 · Light Rays · Fast
- Variant of M-029. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-029

### M-598 · Light Rays · Slow
- Variant of M-029. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-029

### M-873 · Light Rays · Gold
- Variant of M-029. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-029

### M-030 · Confetti Burst
- **When to use:** A celebration, an achievement or a big number.
- **Content the user must provide:** No content needed from you.
- **Duration:** 1.5s
- **Easing:** easeOut then gravity
- **Spec:** 40–80 small rectangles in 4 brand colors burst from a point with random velocity (mostly upward, ±60°), spin randomly, then fall with gravity and fade out over 1.5s.

### M-337 · Confetti Burst · Fast
- Variant of M-030. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-030

### M-612 · Confetti Burst · Slow
- Variant of M-030. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-030

### M-887 · Confetti Burst · Gold
- Variant of M-030. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-030

### M-141 · Sparkle Trail
- **When to use:** A glowing point travels and leaves a trail.
- **Content the user must provide:** No content needed from you.
- **Duration:** 1s
- **Easing:** easeInOutSine
- **Spec:** A bright warm point moves along a curved path; 10–20 copies follow it with 0.05s delays, each shrinking and fading, forming a sparkle trail.

### M-351 · Sparkle Trail · Fast
- Variant of M-141. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-141

### M-626 · Sparkle Trail · Slow
- Variant of M-141. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-141

### M-901 · Sparkle Trail · Gold
- Variant of M-141. color the effect elements (particles, flare, dust) gold #FFC857 instead of white.
- **Content the user must provide:** same as M-141

### M-142 · Dust Burst
- **When to use:** Dust puffs out when something lands.
- **Content the user must provide:** No content needed from you.
- **Duration:** 1s
- **Easing:** easeOutCubic
- **Spec:** From the impact point, 15–30 soft blurred puffs in sand tones spread out and slightly up, growing to 160% and fading over 1s.

### M-365 · Dust Burst · Fast
- Variant of M-142. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-142

### M-640 · Dust Burst · Slow
- Variant of M-142. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-142

### M-915 · Dust Burst · Gold
- Variant of M-142. color the effect elements (particles, flare, dust) gold #FFC857 instead of white.
- **Content the user must provide:** same as M-142

### M-143 · Lens Flare
- **When to use:** A sun flare drifts across the frame for warmth.
- **Content the user must provide:** No content needed from you.
- **Duration:** 1.5s
- **Easing:** linear
- **Spec:** A bright warm core with a soft halo and 3 small colored ghost circles moves diagonally across the frame (screen blend) over about 1.5s.

### M-379 · Lens Flare · Fast
- Variant of M-143. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-143

### M-654 · Lens Flare · Slow
- Variant of M-143. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-143

### M-929 · Lens Flare · Gold
- Variant of M-143. color the effect elements (particles, flare, dust) gold #FFC857 instead of white.
- **Content the user must provide:** same as M-143

### M-144 · Scan Line
- **When to use:** A light line scans the frame like a scanner, techy.
- **Content the user must provide:** No content needed from you.
- **Duration:** 1.2s
- **Easing:** linear
- **Spec:** A bright mint horizontal line with a wide glow travels from the top to the bottom of the frame over 1.2s.

### M-393 · Scan Line · Fast
- Variant of M-144. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-144

### M-668 · Scan Line · Slow
- Variant of M-144. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-144

### M-943 · Scan Line · Gold
- Variant of M-144. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-144

### M-145 · Code Rain
- **When to use:** Falling code characters, perfect for cyber topics.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop
- **Easing:** linear
- **Spec:** Columns of mint monospace characters fall at different speeds behind the person (background layer), each column fading at its tail.

### M-405 · Code Rain · Fast
- Variant of M-145. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-145

### M-680 · Code Rain · Slow
- Variant of M-145. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-145

### M-955 · Code Rain · Gold
- Variant of M-145. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-145

### M-146 · Hologram
- **When to use:** The person looks like a futuristic hologram.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop
- **Easing:** linear
- **Spec:** Tint the person cyan, add moving horizontal scanlines over them (screen blend) and a subtle opacity flicker every couple of seconds.

### M-417 · Hologram · Fast
- Variant of M-146. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-146

### M-692 · Hologram · Slow
- Variant of M-146. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-146

### M-967 · Hologram · Gold
- Variant of M-146. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-146

### M-147 · Electric Arc
- **When to use:** A flickering electric arc for energy moments.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.6s
- **Easing:** steps
- **Spec:** A jagged light-blue zigzag line with a glow flickers on and off 2–3 times between two points; redraw the zigzag randomly each flicker.

### M-428 · Electric Arc · Fast
- Variant of M-147. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-147

### M-703 · Electric Arc · Slow
- Variant of M-147. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-147

### M-978 · Electric Arc · Gold
- Variant of M-147. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-147

### M-148 · Heat Glow
- **When to use:** A warm pulsing aura behind the person.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop · 2s
- **Easing:** easeInOutSine
- **Spec:** A large orange radial glow sits behind the person (background layer) and pulses between 90% and 108% scale every 2s.

### M-439 · Heat Glow · Fast
- Variant of M-148. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-148

### M-714 · Heat Glow · Slow
- Variant of M-148. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-148

### M-989 · Heat Glow · Gold
- Variant of M-148. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-148

### M-149 · Floating Particles
- **When to use:** Small light specks float upward for a calm mood.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop
- **Easing:** linear
- **Spec:** Spawn 12–25 small warm glowing dots at random x positions near the bottom; each drifts upward with slight sideways drift over 3–5s and fades.

### M-449 · Floating Particles · Fast
- Variant of M-149. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-149

### M-724 · Floating Particles · Slow
- Variant of M-149. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-149

### M-999 · Floating Particles · Gold
- Variant of M-149. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-149

### M-150 · Radial Ripple
- **When to use:** Rings spread from a point like touching water.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop · 1.5s
- **Easing:** easeOutCubic
- **Spec:** Thin mint rings spawn at a point every 0.5s, expanding from 30% to 450% and fading out.

### M-458 · Radial Ripple · Fast
- Variant of M-150. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-150

### M-733 · Radial Ripple · Slow
- Variant of M-150. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-150

### M-151 · Grid Floor
- **When to use:** A moving 3D grid floor, retro-tech style.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop · 1s
- **Easing:** linear
- **Spec:** Draw a mint line grid on a plane tilted 60° in perspective at the bottom of the frame, scrolling toward the viewer one cell per second.

### M-467 · Grid Floor · Fast
- Variant of M-151. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-151

### M-742 · Grid Floor · Slow
- Variant of M-151. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-151

### M-152 · Spark Burst
- **When to use:** Spark streaks shoot out from a point on a hit or idea.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.5s
- **Easing:** easeOutExpo
- **Spec:** Twelve thin warm streaks shoot radially outward from a point, stretching as they go and fading over 0.5s.

### M-475 · Spark Burst · Fast
- Variant of M-152. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-152

### M-750 · Spark Burst · Slow
- Variant of M-152. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-152

### M-153 · Orbit Dots
- **When to use:** Dots orbit around a logo or word.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop · 3s
- **Easing:** linear
- **Spec:** Three accent dots travel around a dashed circle centered on the subject, evenly spaced, one full turn every 3s.

### M-483 · Orbit Dots · Fast
- Variant of M-153. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-153

### M-758 · Orbit Dots · Slow
- Variant of M-153. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-153

### M-154 · Glow Outline
- **When to use:** A glowing edge around the person makes them pop.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop · 2s
- **Easing:** easeInOutSine
- **Spec:** Using the person matte, add an accent outer glow (drop shadow on the matte edge) that pulses from 0 to about 2.5% blur every 2s.

### M-491 · Glow Outline · Fast
- Variant of M-154. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-154

### M-766 · Glow Outline · Slow
- Variant of M-154. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-154

### M-155 · VHS Glitch
- **When to use:** Old videotape look for nostalgia.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop
- **Easing:** steps
- **Spec:** Add short horizontal frame jumps (±3%), brief color shifts, and a soft bright noise band that rolls up the frame every couple of seconds.

### M-499 · VHS Glitch · Fast
- Variant of M-155. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-155

### M-774 · VHS Glitch · Slow
- Variant of M-155. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-155

### M-156 · Film Grain
- **When to use:** Grain and light flicker for a film feel.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop
- **Easing:** steps
- **Spec:** Overlay fine moving noise at about 35% opacity, jumping position every frame, plus a tiny brightness flicker (±10%).

### M-507 · Film Grain · Fast
- Variant of M-156. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-156

### M-782 · Film Grain · Slow
- Variant of M-156. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-156

### M-157 · Shine Sweep
- **When to use:** A shine passes over a word or logo like metal.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.8s
- **Easing:** easeInOutSine
- **Spec:** A narrow bright diagonal band clipped to the text or logo sweeps across it from one side to the other over 0.8s.

### M-515 · Shine Sweep · Fast
- Variant of M-157. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-157

### M-790 · Shine Sweep · Slow
- Variant of M-157. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-157

### M-158 · Bokeh Lights
- **When to use:** Soft out-of-focus light circles behind the person.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop · 4s
- **Easing:** easeInOutSine
- **Spec:** Place 6–10 blurred warm circles of different sizes on the background layer; each drifts a little and gently grows and fades on a 4s loop.

### M-523 · Bokeh Lights · Fast
- Variant of M-158. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-158

### M-798 · Bokeh Lights · Slow
- Variant of M-158. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-158

### M-159 · Speed Lines
- **When to use:** Manga speed lines around the face for shock or hype.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop · 0.4s
- **Easing:** steps
- **Spec:** Draw thin white radial lines around the subject with a clear center, jittering in angle and scale every few frames.

### M-531 · Speed Lines · Fast
- Variant of M-159. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-159

### M-806 · Speed Lines · Slow
- Variant of M-159. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-159

### M-160 · Face Tracking Box
- **When to use:** A box that tracks the face with a score, AI style.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop
- **Easing:** easeInOutSine
- **Spec:** Detect the face and draw four mint corner brackets around it that follow it smoothly, with a small mono label above like "FACE 98%".

### M-539 · Face Tracking Box · Fast
- Variant of M-160. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-160

### M-814 · Face Tracking Box · Slow
- Variant of M-160. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-160

## SOC — Social

### M-031 · Follow Tap
- **When to use:** When you say "follow me".
- **Content the user must provide:** text: the @handle
- **Duration:** 1.4s
- **Easing:** easeOutCubic
- **Spec:** A finger tap indicator (white circle with soft halo) glides onto a Follow button, presses it (button scales to 88%), and the button flips from accent "متابعة" to gray "تتابعه ✓". Add a soft click sound.

### M-282 · Follow Tap · Fast
- Variant of M-031. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-031

### M-557 · Follow Tap · Slow
- Variant of M-031. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-031

### M-832 · Follow Tap · Gold
- Variant of M-031. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-031

### M-032 · Comment Typing
- **When to use:** When you say "write it in the comments".
- **Content the user must provide:** text: the keyword
- **Duration:** 1.5s typing
- **Easing:** steps
- **Spec:** An Instagram-style comment field shows placeholder text, then the keyword types in letter by letter (right-to-left for Arabic) and the blue send button pulses (scale 75% to 115% to 100%). Follow with M-035 or M-034.

### M-296 · Comment Typing · Fast
- Variant of M-032. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-032

### M-571 · Comment Typing · Slow
- Variant of M-032. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-032

### M-846 · Comment Typing · Gold
- Variant of M-032. add a soft gold #FFC857 glow (about 1.5% blur) around the main icon or card.
- **Content the user must provide:** same as M-032

### M-033 · Like Burst
- **When to use:** Asking for a like, or a sweet moment.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.6s
- **Easing:** easeOutBack
- **Spec:** A red heart pops from 0 to 135% and settles at 100% (0.35s). At the same time 8 small dots shoot radially outward 27% of the frame and fade. Optionally show a "+1" floating up.

### M-310 · Like Burst · Fast
- Variant of M-033. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-033

### M-585 · Like Burst · Slow
- Variant of M-033. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-033

### M-860 · Like Burst · Gold
- Variant of M-033. add a soft gold #FFC857 glow (about 1.5% blur) around the main icon or card.
- **Content the user must provide:** same as M-033

### M-034 · DM Notification
- **When to use:** "The prompt will reach you in DMs".
- **Content the user must provide:** text: the title; text: the text to show
- **Duration:** 0.5s in · 2s hold
- **Easing:** spring
- **Spec:** A phone-style notification card (app icon, bold title, one-line preview) drops from above the top edge with a spring (overshoot about 10%), holds about 2s, then slides back up. Add a soft notification chime.

### M-324 · DM Notification · Fast
- Variant of M-034. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-034

### M-599 · DM Notification · Slow
- Variant of M-034. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-034

### M-874 · DM Notification · Gold
- Variant of M-034. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-034

### M-035 · Paper Plane
- **When to use:** Sending a message or a comment.
- **Content the user must provide:** No content needed from you.
- **Duration:** 1.2s
- **Easing:** easeInOutSine
- **Spec:** A paper-plane icon flies along a curved path from the lower left to the upper right, rotating to follow the path and shrinking at the end, leaving a dashed trail that draws behind it.

### M-338 · Paper Plane · Fast
- Variant of M-035. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-035

### M-613 · Paper Plane · Slow
- Variant of M-035. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-035

### M-888 · Paper Plane · Gold
- Variant of M-035. add a soft gold #FFC857 glow (about 1.5% blur) around the main icon or card.
- **Content the user must provide:** same as M-035

### M-161 · Bell Ring
- **When to use:** When you say "turn on notifications".
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.8s
- **Easing:** easeOutCubic
- **Spec:** A bell icon swings from its top: +22°, -20°, +14°, -10°, +5° over 0.8s, then a red count badge pops on its corner. Add a soft ding.

### M-352 · Bell Ring · Fast
- Variant of M-161. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-161

### M-627 · Bell Ring · Slow
- Variant of M-161. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-161

### M-902 · Bell Ring · Gold
- Variant of M-161. add a soft gold #FFC857 glow (about 1.5% blur) around the main icon or card.
- **Content the user must provide:** same as M-161

### M-162 · Share Tap
- **When to use:** When you say "share it with your friends".
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.6s
- **Easing:** easeOutBack
- **Spec:** A tap indicator presses the share (paper plane) icon; the icon squashes to 80% then pops to 120% and settles, with a small burst of dots.

### M-366 · Share Tap · Fast
- Variant of M-162. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-162

### M-641 · Share Tap · Slow
- Variant of M-162. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-162

### M-916 · Share Tap · Gold
- Variant of M-162. add a soft gold #FFC857 glow (about 1.5% blur) around the main icon or card.
- **Content the user must provide:** same as M-162

### M-163 · Save Bookmark
- **When to use:** When you say "save this for later".
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.5s
- **Easing:** easeOutCubic
- **Spec:** A bookmark outline icon fills up from bottom to top with white over 0.5s, then pops to 120% and settles.

### M-380 · Save Bookmark · Fast
- Variant of M-163. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-163

### M-655 · Save Bookmark · Slow
- Variant of M-163. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-163

### M-930 · Save Bookmark · Gold
- Variant of M-163. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-163

### M-164 · Story Ring
- **When to use:** A profile photo with a rotating colorful story ring.
- **Content the user must provide:** file: the profile picture
- **Duration:** loop · 3s
- **Easing:** linear
- **Spec:** A circular avatar sits inside a gradient ring (brand colors) that rotates one full turn every 3s, like an unseen story.

### M-394 · Story Ring · Fast
- Variant of M-164. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-164

### M-669 · Story Ring · Slow
- Variant of M-164. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-164

### M-944 · Story Ring · Gold
- Variant of M-164. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-164

### M-165 · Swipe Up Arrow
- **When to use:** When you want viewers to swipe up or tap the link.
- **Content the user must provide:** text: the text to show
- **Duration:** loop · 1.2s
- **Easing:** easeOutCubic
- **Spec:** Two stacked chevrons move up 40% and fade, repeating every 1.2s, above a short label such as "اسحب".

### M-406 · Swipe Up Arrow · Fast
- Variant of M-165. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-165

### M-681 · Swipe Up Arrow · Slow
- Variant of M-165. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-165

### M-956 · Swipe Up Arrow · Gold
- Variant of M-165. add a soft gold #FFC857 glow (about 1.5% blur) around the main icon or card.
- **Content the user must provide:** same as M-165

### M-166 · Poll Sticker
- **When to use:** A two-option poll whose results fill up.
- **Content the user must provide:** text: the question; text: the items (comma-separated)
- **Duration:** 0.8s fill
- **Easing:** easeOutCubic
- **Spec:** A light card with a question and two option rows. Accent bars fill each row to its percentage over 0.8s, with the percentages shown.

### M-418 · Poll Sticker · Fast
- Variant of M-166. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-166

### M-693 · Poll Sticker · Slow
- Variant of M-166. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-166

### M-968 · Poll Sticker · Gold
- Variant of M-166. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-166

### M-167 · Typing Dots
- **When to use:** A chat "typing…" bubble.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop · 1s
- **Easing:** easeInOutSine
- **Spec:** A chat bubble with three dots; each dot rises and brightens in turn, 0.15s apart, looping every second.

### M-429 · Typing Dots · Fast
- Variant of M-167. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-167

### M-704 · Typing Dots · Slow
- Variant of M-167. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-167

### M-979 · Typing Dots · Gold
- Variant of M-167. add a soft gold #FFC857 glow (about 1.5% blur) around the main icon or card.
- **Content the user must provide:** same as M-167

### M-168 · Chat Bubbles
- **When to use:** A conversation appearing message by message.
- **Content the user must provide:** text: the messages (one per line)
- **Duration:** 0.25s per bubble
- **Easing:** easeOutBack
- **Spec:** Message bubbles pop in one at a time from their tail corner (scale 0 to 105% to 100% over 0.25s), alternating sides like a real chat.

### M-440 · Chat Bubbles · Fast
- Variant of M-168. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-168

### M-715 · Chat Bubbles · Slow
- Variant of M-168. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-168

### M-990 · Chat Bubbles · Gold
- Variant of M-168. add a soft gold #FFC857 glow (about 1.5% blur) around the main icon or card.
- **Content the user must provide:** same as M-168

### M-169 · Floating Hearts
- **When to use:** Hearts float upward like a live stream.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop
- **Easing:** easeOut
- **Spec:** Small hearts spawn near the bottom corner every 0.2–0.4s and float up about 90% of the frame with a gentle sideways sway, growing slightly and fading.

### M-450 · Floating Hearts · Fast
- Variant of M-169. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-169

### M-725 · Floating Hearts · Slow
- Variant of M-169. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-169

### M-1000 · Floating Hearts · Gold
- Variant of M-169. add a soft gold #FFC857 glow (about 1.5% blur) around the main icon or card.
- **Content the user must provide:** same as M-169

### M-170 · View Counter
- **When to use:** A view count ticking up.
- **Content the user must provide:** text: the number and its label
- **Duration:** 1.2s count
- **Easing:** easeOutExpo
- **Spec:** An eye icon with a number counting up from 0 to the target (see M-040), in tabular mono digits.

### M-459 · View Counter · Fast
- Variant of M-170. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-170

### M-734 · View Counter · Slow
- Variant of M-170. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-170

### M-171 · Profile Card
- **When to use:** Introduces your account with a card rising from below.
- **Content the user must provide:** file: the profile picture; text: the name and role; text: the @handle
- **Duration:** 0.5s in
- **Easing:** spring
- **Spec:** A light rounded card with avatar, name, handle and a follow button slides up from below the frame with a spring and a 4% overshoot, holds, then slides back.

### M-468 · Profile Card · Fast
- Variant of M-171. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-171

### M-743 · Profile Card · Slow
- Variant of M-171. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-171

### M-172 · Link Sticker
- **When to use:** When you say "link in bio".
- **Content the user must provide:** text: the link
- **Duration:** 0.4s + wiggle
- **Easing:** easeOutBack
- **Spec:** A white pill sticker with a link icon and the URL pops in (0.4s), then wiggles gently every couple of seconds to invite a tap.

### M-476 · Link Sticker · Fast
- Variant of M-172. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-172

### M-751 · Link Sticker · Slow
- Variant of M-172. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-172

### M-173 · Countdown
- **When to use:** A 3-2-1 countdown before a big moment.
- **Content the user must provide:** No content needed from you.
- **Duration:** 1s per number
- **Easing:** easeOutBack
- **Spec:** Big mono digits 3, 2, 1 replace each other every second, each popping from 60% to 110% to 100% and fading out. Add a tick sound per number.

### M-484 · Countdown · Fast
- Variant of M-173. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-173

### M-759 · Countdown · Slow
- Variant of M-173. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-173

### M-174 · Question Sticker
- **When to use:** An "ask me a question" box like Stories.
- **Content the user must provide:** text: the question
- **Duration:** 0.4s in
- **Easing:** easeOutBack
- **Spec:** A light card with an accent header "اسألني سؤال" and a text field pops in, then a short question types into the field.

### M-492 · Question Sticker · Fast
- Variant of M-174. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-174

### M-767 · Question Sticker · Slow
- Variant of M-174. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-174

### M-175 · Mention Tag
- **When to use:** An account tag pops onto a person or object.
- **Content the user must provide:** text: the @handle
- **Duration:** 0.3s
- **Easing:** easeOutBack
- **Spec:** A dark rounded tag with a small pointer and the @handle pops from the tagged point (scale 0 to 110% to 100% over 0.3s).

### M-500 · Mention Tag · Fast
- Variant of M-175. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-175

### M-775 · Mention Tag · Slow
- Variant of M-175. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-175

### M-176 · Verified Badge
- **When to use:** A blue verified check next to your name.
- **Content the user must provide:** text: the name and role
- **Duration:** 0.4s
- **Easing:** easeOutBack
- **Spec:** A blue circular check badge spins in from -180° and 0 scale to a 130% pop and settles next to the name over 0.4s.

### M-508 · Verified Badge · Fast
- Variant of M-176. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-176

### M-783 · Verified Badge · Slow
- Variant of M-176. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-176

### M-177 · Comment Stack
- **When to use:** Comments pile up one after another, like audience reactions.
- **Content the user must provide:** text: the messages (one per line)
- **Duration:** 0.3s per comment
- **Easing:** easeOutCubic
- **Spec:** Comment rows (avatar dot + short text) slide up and fade in one by one, 0.5s apart, stacking into a list.

### M-516 · Comment Stack · Fast
- Variant of M-177. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-177

### M-791 · Comment Stack · Slow
- Variant of M-177. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-177

### M-178 · Notification Badge
- **When to use:** A red count badge bounces onto an icon.
- **Content the user must provide:** text: the number and its label
- **Duration:** 0.3s
- **Easing:** easeOutBack
- **Spec:** A red rounded badge with a number pops onto the top corner of an icon (0 to 130% to 100% over 0.3s), then the icon gives a small pop.

### M-524 · Notification Badge · Fast
- Variant of M-178. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-178

### M-799 · Notification Badge · Slow
- Variant of M-178. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-178

### M-179 · Sound On
- **When to use:** When you want viewers to turn the sound on.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop · 1.2s
- **Easing:** easeInOutSine
- **Spec:** A speaker icon with three sound waves that light up one after another, 0.2s apart, looping every 1.2s.

### M-532 · Sound On · Fast
- Variant of M-179. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-179

### M-807 · Sound On · Slow
- Variant of M-179. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-179

### M-180 · Search Typing
- **When to use:** When you say "search for…".
- **Content the user must provide:** text: the text to show
- **Duration:** 1.2s typing
- **Easing:** steps
- **Spec:** A light rounded search bar with a magnifier icon; the query types in letter by letter from the reading-start side.

### M-540 · Search Typing · Fast
- Variant of M-180. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-180

### M-815 · Search Typing · Slow
- Variant of M-180. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-180

## LGO — Logos & Titles

### M-036 · Logo Float
- **When to use:** A logo floating gently behind you.
- **Content the user must provide:** file: your logo (transparent PNG)
- **Duration:** loop · 3s
- **Easing:** easeInOutSine
- **Spec:** The logo hovers behind the person (background layer, under the person matte) with a gentle ±9% vertical bob on a 3s sine loop and a soft glow.

### M-283 · Logo Float · Fast
- Variant of M-036. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-036

### M-558 · Logo Float · Slow
- Variant of M-036. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-036

### M-833 · Logo Float · Gold
- Variant of M-036. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-036

### M-037 · Logo Spin-In
- **When to use:** Opening or closing a video.
- **Content the user must provide:** file: your logo (transparent PNG)
- **Duration:** 0.7s
- **Easing:** easeOutBack
- **Spec:** The logo spins in from -220° and scale 0 to 0° and 112%, then settles at 100% over 0.7s total. Exit: shrink to 0 with a 90° turn.

### M-297 · Logo Spin-In · Fast
- Variant of M-037. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-037

### M-572 · Logo Spin-In · Slow
- Variant of M-037. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-037

### M-847 · Logo Spin-In · Gold
- Variant of M-037. add a soft gold #FFC857 glow (about 1.5% blur) around the logo or main element.
- **Content the user must provide:** same as M-037

### M-038 · Title Card Drop
- **When to use:** The tool or topic name, like a "Claude Opus 5.5" card.
- **Content the user must provide:** text: the title; text: the subtitle
- **Duration:** 0.55s in
- **Easing:** spring
- **Spec:** A dark rounded card with an accent border, an icon on one side and a two-line title (bold mono title plus an accent subtitle) drops from above the frame with a spring and about a 10% overshoot. Holds, then slides back up.

### M-311 · Title Card Drop · Fast
- Variant of M-038. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-038

### M-586 · Title Card Drop · Slow
- Variant of M-038. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-038

### M-861 · Title Card Drop · Gold
- Variant of M-038. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-038

### M-039 · Lower Third
- **When to use:** Introduce your name or handle.
- **Content the user must provide:** text: the name and role; text: the subtitle
- **Duration:** 0.4s bar · 0.3s text
- **Easing:** easeOutExpo
- **Spec:** An accent bar grows in from the right edge (0.4s), then the name and the subtitle slide in 12% and fade in inside it (0.3s, 0.08s stagger). Holds, then the text fades and the bar retracts.

### M-325 · Lower Third · Fast
- Variant of M-039. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-039

### M-600 · Lower Third · Slow
- Variant of M-039. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-039

### M-875 · Lower Third · Gold
- Variant of M-039. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-039

### M-040 · Number Counter
- **When to use:** A stat or big number counting up.
- **Content the user must provide:** text: the number and its label
- **Duration:** 1.2s count
- **Easing:** easeOutExpo
- **Spec:** A number counts up from 0 to the target value over 1.2s (easeOutExpo, fast at first, then slowing), in tabular monospaced digits with an accent color, and a label beneath. Optionally scale-punch the final value (M-008).

### M-339 · Number Counter · Fast
- Variant of M-040. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-040

### M-614 · Number Counter · Slow
- Variant of M-040. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-040

### M-889 · Number Counter · Gold
- Variant of M-040. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-040

### M-181 · Logo Mask Reveal
- **When to use:** A logo rises from behind an invisible line, premium style.
- **Content the user must provide:** file: your logo (transparent PNG)
- **Duration:** 0.6s
- **Easing:** easeInOutQuart
- **Spec:** The logo sits inside a box with hidden overflow and slides up from below its edge into place over 0.6s (see M-004).

### M-353 · Logo Mask Reveal · Fast
- Variant of M-181. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-181

### M-628 · Logo Mask Reveal · Slow
- Variant of M-181. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-181

### M-903 · Logo Mask Reveal · Gold
- Variant of M-181. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-181

### M-182 · Logo Stroke Draw
- **When to use:** The logo draws its outline, then fills.
- **Content the user must provide:** file: your logo (transparent PNG)
- **Duration:** 1s draw · 0.4s fill
- **Easing:** easeInOutCubic
- **Spec:** Animate the logo vector outline stroke from 0 to full length over 1s, then fade in the fill over 0.4s.

### M-367 · Logo Stroke Draw · Fast
- Variant of M-182. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-182

### M-642 · Logo Stroke Draw · Slow
- Variant of M-182. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-182

### M-917 · Logo Stroke Draw · Gold
- Variant of M-182. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-182

### M-183 · Logo Glitch
- **When to use:** The logo glitches with split colors, techy.
- **Content the user must provide:** file: your logo (transparent PNG)
- **Duration:** 0.4s burst
- **Easing:** steps
- **Spec:** For about 0.4s the logo jumps a few percent in random directions with red and cyan offset copies, then snaps back clean.

### M-381 · Logo Glitch · Fast
- Variant of M-183. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-183

### M-656 · Logo Glitch · Slow
- Variant of M-183. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-183

### M-931 · Logo Glitch · Gold
- Variant of M-183. add a soft gold #FFC857 glow (about 1.5% blur) around the logo or main element.
- **Content the user must provide:** same as M-183

### M-184 · Logo Bounce
- **When to use:** The logo drops in and bounces twice.
- **Content the user must provide:** file: your logo (transparent PNG)
- **Duration:** 0.8s
- **Easing:** easeOutBounce
- **Spec:** The logo falls from above the frame, lands, bounces up 30% then 10% and settles over about 0.8s.

### M-395 · Logo Bounce · Fast
- Variant of M-184. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-184

### M-670 · Logo Bounce · Slow
- Variant of M-184. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-184

### M-945 · Logo Bounce · Gold
- Variant of M-184. add a soft gold #FFC857 glow (about 1.5% blur) around the logo or main element.
- **Content the user must provide:** same as M-184

### M-185 · Logo Shine
- **When to use:** A shine passes over a logo badge.
- **Content the user must provide:** file: your logo (transparent PNG)
- **Duration:** 0.8s
- **Easing:** easeInOutSine
- **Spec:** A bright diagonal band sweeps across the logo badge from one side to the other over 0.8s, clipped to the badge shape.

### M-407 · Logo Shine · Fast
- Variant of M-185. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-185

### M-682 · Logo Shine · Slow
- Variant of M-185. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-185

### M-957 · Logo Shine · Gold
- Variant of M-185. add a soft gold #FFC857 glow (about 1.5% blur) around the logo or main element.
- **Content the user must provide:** same as M-185

### M-186 · Logo Assemble
- **When to use:** Particles gather into the logo, the reverse of M-026.
- **Content the user must provide:** file: your logo (transparent PNG)
- **Duration:** 1s
- **Easing:** easeOutCubic
- **Spec:** Hundreds of particles start scattered and fly inward to their positions in the logo over 1s; when they arrive, the solid logo fades in and the particles disappear.

### M-419 · Logo Assemble · Fast
- Variant of M-186. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-186

### M-694 · Logo Assemble · Slow
- Variant of M-186. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-186

### M-969 · Logo Assemble · Gold
- Variant of M-186. add a soft gold #FFC857 glow (about 1.5% blur) around the logo or main element.
- **Content the user must provide:** same as M-186

### M-187 · End Card
- **When to use:** The closing card: logo, handle and a follow prompt.
- **Content the user must provide:** file: your logo (transparent PNG); text: the @handle
- **Duration:** 0.6s in
- **Easing:** easeOutCubic
- **Spec:** The logo scales in, then the handle and a "تابعني" line fade up under it 0.15s apart. Hold until the end of the video.

### M-430 · End Card · Fast
- Variant of M-187. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-187

### M-705 · End Card · Slow
- Variant of M-187. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-187

### M-980 · End Card · Gold
- Variant of M-187. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-187

### M-188 · Watermark Corner
- **When to use:** Your logo small in the corner for the whole video.
- **Content the user must provide:** file: your logo (transparent PNG)
- **Duration:** 0.6s in
- **Easing:** easeOutCubic
- **Spec:** The logo flies from the center to a top corner while shrinking, then stays there at about 55% opacity and 12% of the width for the rest of the video.

### M-441 · Watermark Corner · Fast
- Variant of M-188. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-188

### M-716 · Watermark Corner · Slow
- Variant of M-188. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-188

### M-991 · Watermark Corner · Gold
- Variant of M-188. add a soft gold #FFC857 glow (about 1.5% blur) around the logo or main element.
- **Content the user must provide:** same as M-188

### M-189 · Badge Stamp
- **When to use:** A stamp hits the screen, like "approved" or "free".
- **Content the user must provide:** text: the text to show
- **Duration:** 0.3s
- **Easing:** easeInQuad
- **Spec:** A circular stamp with bold text drops from 240% scale to about 92% and settles at 100% in 0.3s, tilted -14°, with a small screen shake on impact.

### M-451 · Badge Stamp · Fast
- Variant of M-189. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-189

### M-726 · Badge Stamp · Slow
- Variant of M-189. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-189

### M-190 · Title Underline Card
- **When to use:** A big title, an underline drawing in, and a subtitle.
- **Content the user must provide:** text: the title; text: the subtitle
- **Duration:** 0.9s total
- **Easing:** easeOutCubic
- **Spec:** The title fades up (0.4s), an accent underline draws under it (0.4s), then the subtitle fades in (0.3s).

### M-460 · Title Underline Card · Fast
- Variant of M-190. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-190

### M-735 · Title Underline Card · Slow
- Variant of M-190. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-190

### M-191 · Chapter Title
- **When to use:** A big number and title for each part of the video.
- **Content the user must provide:** text: the title
- **Duration:** 0.6s
- **Easing:** easeOutCubic
- **Spec:** A large accent mono number (01, 02…) slides in, then the chapter title fades up beside or under it 0.15s later.

### M-469 · Chapter Title · Fast
- Variant of M-191. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-191

### M-744 · Chapter Title · Slow
- Variant of M-191. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-191

### M-192 · Price Tag
- **When to use:** A price or discount tag swings in.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.6s
- **Easing:** easeOutBack
- **Spec:** A yellow tag-shaped label swings in from its hole side, from -90° to +12°, -6° and settles over 0.6s.

### M-477 · Price Tag · Fast
- Variant of M-192. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-192

### M-752 · Price Tag · Slow
- Variant of M-192. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-192

### M-193 · Progress Bar
- **When to use:** A bar fills with a percentage, like loading or progress.
- **Content the user must provide:** text: the number and its label
- **Duration:** 1.2s
- **Easing:** easeInOutCubic
- **Spec:** A rounded track fills with an accent gradient from the reading-start side over 1.2s while a percentage counts up above it.

### M-485 · Progress Bar · Fast
- Variant of M-193. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-193

### M-760 · Progress Bar · Slow
- Variant of M-193. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-193

### M-194 · Checklist Tick
- **When to use:** Items get ticked one by one, like steps.
- **Content the user must provide:** text: the items (comma-separated)
- **Duration:** 0.3s per tick · 0.5s stagger
- **Easing:** easeOutCubic
- **Spec:** Each list item has a box; a mint check mark draws inside it (0.3s), items ticking 0.5s apart.

### M-493 · Checklist Tick · Fast
- Variant of M-194. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-194

### M-768 · Checklist Tick · Slow
- Variant of M-194. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-194

### M-195 · Step Numbers
- **When to use:** Numbers 1, 2, 3 pop in with a connecting line.
- **Content the user must provide:** text: the items (comma-separated)
- **Duration:** 0.25s per step
- **Easing:** easeOutBack
- **Spec:** Circular accent number badges pop in one by one, 0.4s apart, while a line draws behind them connecting each step.

### M-501 · Step Numbers · Fast
- Variant of M-195. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-195

### M-776 · Step Numbers · Slow
- Variant of M-195. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-195

### M-196 · Quote Card
- **When to use:** A quote or key line with its author.
- **Content the user must provide:** text: the quote and who said it
- **Duration:** 0.8s
- **Easing:** easeOutCubic
- **Spec:** A large accent quote mark scales in, then the quote text fades up line by line, then the author name fades in, each 0.2s apart.

### M-509 · Quote Card · Fast
- Variant of M-196. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-196

### M-784 · Quote Card · Slow
- Variant of M-196. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-196

### M-197 · Stat Bars
- **When to use:** A bar chart grows in, for numbers and comparisons.
- **Content the user must provide:** text: the values or percentages
- **Duration:** 0.6s · 0.1s stagger
- **Easing:** easeOutCubic
- **Spec:** Vertical bars grow from the baseline to their values over 0.6s, each starting 0.1s after the previous one, with alternating brand colors.

### M-517 · Stat Bars · Fast
- Variant of M-197. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-197

### M-792 · Stat Bars · Slow
- Variant of M-197. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-197

### M-198 · Pie Fill
- **When to use:** A ring fills to a percentage.
- **Content the user must provide:** text: the number and its label
- **Duration:** 1s
- **Easing:** easeOutCubic
- **Spec:** A thick ring fills clockwise with the accent color from 0 to the target percentage over 1s, with the number in the middle.

### M-525 · Pie Fill · Fast
- Variant of M-198. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-198

### M-800 · Pie Fill · Slow
- Variant of M-198. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-198

### M-199 · Map Pin Drop
- **When to use:** A location pin drops onto a place, like "Kuwait".
- **Content the user must provide:** text: the place name
- **Duration:** 0.5s
- **Easing:** easeOutBounce
- **Spec:** A pin falls from above, lands with a small bounce, and a ripple ring spreads under it on impact, with the place name fading in below.

### M-533 · Map Pin Drop · Fast
- Variant of M-199. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-199

### M-808 · Map Pin Drop · Slow
- Variant of M-199. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-199

### M-200 · Signature Write
- **When to use:** Your signature writes itself at the end of the video.
- **Content the user must provide:** file: your signature image
- **Duration:** 1.5s
- **Easing:** easeInOutSine
- **Spec:** Animate a handwritten signature path stroke from start to end over about 1.5s with a slight ease, as if written live. Hold, then fade.

### M-541 · Signature Write · Fast
- Variant of M-200. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-200

### M-816 · Signature Write · Slow
- Variant of M-200. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-200

## PER — Person FX

### M-201 · Text Behind Person
- **When to use:** A huge title behind your head with you in front, a top trend.
- **Content the user must provide:** text: the title
- **Duration:** 0.6s in
- **Easing:** easeOutCubic
- **Spec:** Place a very large bold title on a layer between the background and the person (use the person matte), so the head overlaps the letters. The title rises in with M-004 style.

### M-284 · Text Behind Person · Fast
- Variant of M-201. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-201

### M-559 · Text Behind Person · Slow
- Variant of M-201. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-201

### M-834 · Text Behind Person · Gold
- Variant of M-201. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-201

### M-202 · Color Pop
- **When to use:** The background goes black and white while you stay in color.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.4s
- **Easing:** easeInOutSine
- **Spec:** Using the person matte, desaturate only the background to 0% and darken it slightly over 0.4s; the person keeps full color.

### M-298 · Color Pop · Fast
- Variant of M-202. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-202

### M-573 · Color Pop · Slow
- Variant of M-202. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-202

### M-848 · Color Pop · Gold
- Variant of M-202. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-202

### M-203 · Echo Trail
- **When to use:** Transparent copies of you trail behind your movement.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop
- **Easing:** easeInOutSine
- **Spec:** Duplicate the person layer 2–4 times, each delayed by 3–5 frames and at decreasing opacity (30%, 15%…), so movement leaves an echo trail.

### M-312 · Echo Trail · Fast
- Variant of M-203. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-203

### M-587 · Echo Trail · Slow
- Variant of M-203. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-203

### M-862 · Echo Trail · Gold
- Variant of M-203. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-203

### M-204 · Clone Trio
- **When to use:** Multiple copies of you in the same shot.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.3s per clone
- **Easing:** easeOutBack
- **Spec:** Composite 2–3 mattes of the person from different takes side by side; each clone pops in (scale 90% to 100% with fade) 0.3s apart.

### M-326 · Clone Trio · Fast
- Variant of M-204. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-204

### M-601 · Clone Trio · Slow
- Variant of M-204. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-204

### M-876 · Clone Trio · Gold
- Variant of M-204. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-204

### M-205 · Doodle Outline
- **When to use:** Animated hand-drawn doodles around the person.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.8s draw
- **Easing:** easeInOutCubic
- **Spec:** Draw loose white hand-drawn strokes (a crown, sparks, an outline arc) around the head that write on over 0.8s and wiggle slightly while held.

### M-340 · Doodle Outline · Fast
- Variant of M-205. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-205

### M-615 · Doodle Outline · Slow
- Variant of M-205. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-205

### M-890 · Doodle Outline · Gold
- Variant of M-205. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-205

### M-206 · Sticker Cutout
- **When to use:** The person becomes a white-bordered sticker that pops.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.4s
- **Easing:** easeOutBack
- **Spec:** Using the person matte, add a thick white outline (about 1% of the width) and a soft drop shadow, then pop the sticker in with a slight tilt (scale 0 to 108% to 100%).

### M-354 · Sticker Cutout · Fast
- Variant of M-206. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-206

### M-629 · Sticker Cutout · Slow
- Variant of M-206. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-206

### M-904 · Sticker Cutout · Gold
- Variant of M-206. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-206

### M-207 · Pop-Out Frame
- **When to use:** The person breaks out of a frame, a 3D feel.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.5s
- **Easing:** easeOutBack
- **Spec:** A rounded frame shows the background; the person matte is layered above it so the head sticks out over the top edge of the frame. The frame scales in first.

### M-368 · Pop-Out Frame · Fast
- Variant of M-207. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-207

### M-643 · Pop-Out Frame · Slow
- Variant of M-207. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-207

### M-918 · Pop-Out Frame · Gold
- Variant of M-207. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-207

### M-208 · Portrait Mode
- **When to use:** A blurred background with the person sharp, like a phone portrait.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.5s
- **Easing:** easeInOutCubic
- **Spec:** Using the person matte, blur only the background to about 1.5% over 0.5s while the person stays sharp.

### M-382 · Portrait Mode · Fast
- Variant of M-208. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-208

### M-657 · Portrait Mode · Slow
- Variant of M-208. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-208

### M-932 · Portrait Mode · Gold
- Variant of M-208. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-208

### M-209 · Silhouette Fill
- **When to use:** The person turns into a solid brand-color silhouette, poster style.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.3s
- **Easing:** easeOutQuad
- **Spec:** Using the person matte, fill the person with a flat accent color (keep the matte edge soft) and fade it in over 0.3s on a beat.

### M-396 · Silhouette Fill · Fast
- Variant of M-209. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-209

### M-671 · Silhouette Fill · Slow
- Variant of M-209. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-209

### M-946 · Silhouette Fill · Gold
- Variant of M-209. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-209

### M-210 · Neon Outline
- **When to use:** A glowing neon edge traced around the person.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop flicker
- **Easing:** steps
- **Spec:** Trace the person matte edge with a 0.8% mint line plus a wide glow, and flicker it on like neon (see M-056).

### M-408 · Neon Outline · Fast
- Variant of M-210. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-210

### M-683 · Neon Outline · Slow
- Variant of M-210. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-210

### M-958 · Neon Outline · Gold
- Variant of M-210. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-210

### M-211 · Spotlight Follow
- **When to use:** Everything goes dark except a light circle that follows you.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop
- **Easing:** easeInOutSine
- **Spec:** Darken the frame about 85% except a soft circle around the person; the circle tracks the head position every frame.

### M-420 · Spotlight Follow · Fast
- Variant of M-211. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-211

### M-695 · Spotlight Follow · Slow
- Variant of M-211. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-211

### M-970 · Spotlight Follow · Gold
- Variant of M-211. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-211

### M-212 · Halftone Person
- **When to use:** The person rendered in halftone dots like old print.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.4s
- **Easing:** easeOutQuad
- **Spec:** Inside the person matte, overlay an accent halftone dot pattern (dot size tied to brightness) with a multiply blend.

### M-431 · Halftone Person · Fast
- Variant of M-212. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-212

### M-706 · Halftone Person · Slow
- Variant of M-212. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-212

### M-981 · Halftone Person · Gold
- Variant of M-212. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-212

### M-213 · Background Flash Swap
- **When to use:** The background color flips on every beat while you stay.
- **Content the user must provide:** No content needed from you.
- **Duration:** per beat
- **Easing:** cut
- **Spec:** Using the person matte, replace the background with a solid color that changes on every beat (cycle 3–4 brand colors).

### M-442 · Background Flash Swap · Fast
- Variant of M-213. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-213

### M-717 · Background Flash Swap · Slow
- Variant of M-213. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-213

### M-992 · Background Flash Swap · Gold
- Variant of M-213. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-213

## AUD — Audio & Beat

### M-214 · Waveform
- **When to use:** A waveform that moves with your voice.
- **Content the user must provide:** It runs on the video’s own voice or music, so you upload nothing.
- **Duration:** live
- **Easing:** linear
- **Spec:** Analyze the voice track loudness (RMS) per frame and draw 30–60 thin rounded accent bars whose heights follow the audio around a center line.

### M-285 · Waveform · Fast
- Variant of M-214. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-214

### M-560 · Waveform · Slow
- Variant of M-214. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-214

### M-835 · Waveform · Gold
- Variant of M-214. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-214

### M-215 · Equalizer Bars
- **When to use:** Bars that bounce with the audio or music.
- **Content the user must provide:** It runs on the video’s own voice or music, so you upload nothing.
- **Duration:** live
- **Easing:** easeOut
- **Spec:** Split the audio spectrum into 6–10 frequency bands and draw a vertical gradient bar per band whose height follows that band with quick attack and slower release.

### M-299 · Equalizer Bars · Fast
- Variant of M-215. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-215

### M-574 · Equalizer Bars · Slow
- Variant of M-215. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-215

### M-849 · Equalizer Bars · Gold
- Variant of M-215. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-215

### M-216 · Circular Visualizer
- **When to use:** Audio bars arranged in a circle around your photo.
- **Content the user must provide:** file: the profile picture
- **Duration:** live
- **Easing:** easeOut
- **Spec:** Place 24–48 accent bars radially around a circular avatar; each bar length follows one frequency band of the audio.

### M-313 · Circular Visualizer · Fast
- Variant of M-216. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-216

### M-588 · Circular Visualizer · Slow
- Variant of M-216. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-216

### M-863 · Circular Visualizer · Gold
- Variant of M-216. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-216

### M-217 · Beat Flash
- **When to use:** A light flash on every beat of the music.
- **Content the user must provide:** It runs on the video’s own voice or music, so you upload nothing.
- **Duration:** per beat · 0.15s
- **Easing:** easeOut
- **Spec:** Detect beats in the music track; on each beat flash a white overlay to about 40–85% and fade it out over 0.15s.

### M-327 · Beat Flash · Fast
- Variant of M-217. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-217

### M-602 · Beat Flash · Slow
- Variant of M-217. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-217

### M-877 · Beat Flash · Gold
- Variant of M-217. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-217

### M-218 · Beat Zoom
- **When to use:** The frame pulses a zoom on every beat.
- **Content the user must provide:** It runs on the video’s own voice or music, so you upload nothing.
- **Duration:** per beat · 0.2s
- **Easing:** easeOutCubic
- **Spec:** On each detected beat, jump the frame scale to 112% and ease back to 100% over about 0.2s.

### M-341 · Beat Zoom · Fast
- Variant of M-218. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-218

### M-616 · Beat Zoom · Slow
- Variant of M-218. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-218

### M-891 · Beat Zoom · Gold
- Variant of M-218. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-218

### M-219 · Beat Shake
- **When to use:** A short shake on every heavy beat.
- **Content the user must provide:** It runs on the video’s own voice or music, so you upload nothing.
- **Duration:** per beat · 0.15s
- **Easing:** linear
- **Spec:** On each strong beat (kick), shake the overscaled frame (106%) with 2–3 quick offsets of ±2% over 0.15s.

### M-355 · Beat Shake · Fast
- Variant of M-219. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-219

### M-630 · Beat Shake · Slow
- Variant of M-219. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-219

### M-905 · Beat Shake · Gold
- Variant of M-219. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-219

### M-220 · Audio Pulse Ring
- **When to use:** A ring around your photo that swells with your voice.
- **Content the user must provide:** file: the profile picture
- **Duration:** live
- **Easing:** easeOut
- **Spec:** Draw an accent ring around a circular avatar; its scale (100–118%) and opacity follow the voice loudness each frame.

### M-369 · Audio Pulse Ring · Fast
- Variant of M-220. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-220

### M-644 · Audio Pulse Ring · Slow
- Variant of M-220. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-220

### M-919 · Audio Pulse Ring · Gold
- Variant of M-220. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-220

### M-221 · Waveform Caption
- **When to use:** A caption with a small live waveform under it.
- **Content the user must provide:** It runs on the video’s own voice or music, so you upload nothing.
- **Duration:** live
- **Easing:** linear
- **Spec:** Show the caption as usual and draw a compact waveform (M-214) just under it, following the voice.

### M-383 · Waveform Caption · Fast
- Variant of M-221. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-221

### M-658 · Waveform Caption · Slow
- Variant of M-221. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-221

### M-933 · Waveform Caption · Gold
- Variant of M-221. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-221

### M-222 · Mic Pulse
- **When to use:** A microphone icon with ripples, for podcasts and voice.
- **Content the user must provide:** It runs on the video’s own voice or music, so you upload nothing.
- **Duration:** loop · 1.5s
- **Easing:** easeOutCubic
- **Spec:** A mic icon sits at the center while thin rings expand from it every 0.5s and fade (see M-150).

### M-397 · Mic Pulse · Fast
- Variant of M-222. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-222

### M-672 · Mic Pulse · Slow
- Variant of M-222. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-222

### M-947 · Mic Pulse · Gold
- Variant of M-222. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-222

### M-223 · Podcast Card
- **When to use:** A podcast episode card with a photo and waveform.
- **Content the user must provide:** file: the profile picture; text: the title
- **Duration:** 0.5s in
- **Easing:** spring
- **Spec:** A light card with avatar, episode title, show name and a small live waveform slides up with a spring and holds.

### M-409 · Podcast Card · Fast
- Variant of M-223. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-223

### M-684 · Podcast Card · Slow
- Variant of M-223. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-223

### M-959 · Podcast Card · Gold
- Variant of M-223. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-223

### M-224 · Volume Meter
- **When to use:** A level meter rising and falling with the voice.
- **Content the user must provide:** It runs on the video’s own voice or music, so you upload nothing.
- **Duration:** live
- **Easing:** linear
- **Spec:** Stack 8–12 segments vertically; segments light up from the bottom with loudness (green, then yellow, then red at the top).

### M-421 · Volume Meter · Fast
- Variant of M-224. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-224

### M-696 · Volume Meter · Slow
- Variant of M-224. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-224

### M-971 · Volume Meter · Gold
- Variant of M-224. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-224

### M-225 · BPM Counter
- **When to use:** A BPM number with a dot pulsing on the beat.
- **Content the user must provide:** It runs on the video’s own voice or music, so you upload nothing.
- **Duration:** per beat
- **Easing:** easeOut
- **Spec:** Show the tempo as a mono number with "BPM" and a dot that flashes to 150% on every beat.

### M-432 · BPM Counter · Fast
- Variant of M-225. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-225

### M-707 · BPM Counter · Slow
- Variant of M-225. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-225

### M-982 · BPM Counter · Gold
- Variant of M-225. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-225

## SCR — Screens & UI

### M-226 · App Window Pop
- **When to use:** A desktop app window pops up while you explain.
- **Content the user must provide:** text: the title; file: a screenshot or screen recording (it appears inside the frame)
- **Duration:** 0.4s
- **Easing:** easeOutBack
- **Spec:** A rounded window with three title-bar dots and a title scales from 60% to 104% to 100% with a fade over 0.4s, showing your screenshot or screen recording inside.

### M-286 · App Window Pop · Fast
- Variant of M-226. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-226

### M-561 · App Window Pop · Slow
- Variant of M-226. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-226

### M-836 · App Window Pop · Gold
- Variant of M-226. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-226

### M-227 · Phone Scroll
- **When to use:** Shows an app or page scrolling inside a phone.
- **Content the user must provide:** file: a screenshot or screen recording (it appears inside the frame)
- **Duration:** 2s scroll
- **Easing:** easeInOutCubic
- **Spec:** A phone frame with rounded corners shows your screen recording or a long screenshot that scrolls up smoothly inside it, then eases to a stop.

### M-300 · Phone Scroll · Fast
- Variant of M-227. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-227

### M-575 · Phone Scroll · Slow
- Variant of M-227. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-227

### M-850 · Phone Scroll · Gold
- Variant of M-227. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-227

### M-228 · Laptop Mockup
- **When to use:** Places your screen recording inside a laptop.
- **Content the user must provide:** file: your screen recording
- **Duration:** 0.6s in
- **Easing:** easeOutCubic
- **Spec:** A laptop mockup (screen bezel and base) rises 10% with a fade over 0.6s; your screen recording plays inside the screen area.

### M-314 · Laptop Mockup · Fast
- Variant of M-228. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-228

### M-589 · Laptop Mockup · Slow
- Variant of M-228. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-228

### M-864 · Laptop Mockup · Gold
- Variant of M-228. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-228

### M-229 · Browser Window
- **When to use:** A website inside a browser window with a URL bar.
- **Content the user must provide:** text: the link; file: a screenshot or screen recording (it appears inside the frame)
- **Duration:** 0.4s
- **Easing:** easeOutBack
- **Spec:** A browser window with dots, a URL bar showing your site, and the page content pops in; the URL can type itself first (see M-180).

### M-328 · Browser Window · Fast
- Variant of M-229. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-229

### M-603 · Browser Window · Slow
- Variant of M-229. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-229

### M-878 · Browser Window · Gold
- Variant of M-229. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-229

### M-230 · Phone Slide In
- **When to use:** A phone with your app slides in next to you.
- **Content the user must provide:** file: a screenshot or screen recording (it appears inside the frame)
- **Duration:** 0.5s
- **Easing:** easeOutCubic
- **Spec:** A phone mockup slides in from the side edge with a slight tilt that straightens over 0.5s, then holds beside the speaker.

### M-342 · Phone Slide In · Fast
- Variant of M-230. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-230

### M-617 · Phone Slide In · Slow
- Variant of M-230. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-230

### M-892 · Phone Slide In · Gold
- Variant of M-230. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-230

### M-231 · Cursor Click
- **When to use:** A mouse cursor glides over and clicks a button.
- **Content the user must provide:** text: the button or spot to click
- **Duration:** 1s
- **Easing:** easeInOutCubic
- **Spec:** A cursor arrow moves along a smooth curve to a button, scales to 85% on click, and a white ring expands from the click point.

### M-356 · Cursor Click · Fast
- Variant of M-231. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-231

### M-631 · Cursor Click · Slow
- Variant of M-231. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-231

### M-906 · Cursor Click · Gold
- Variant of M-231. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-231

### M-232 · Zoom to Cursor
- **When to use:** A zoom that follows the cursor in a screen recording.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.6s
- **Easing:** easeInOutCubic
- **Spec:** In a screen recording, zoom to about 180% centered on the cursor position over 0.6s, follow it smoothly while zoomed, then zoom back out.

### M-370 · Zoom to Cursor · Fast
- Variant of M-232. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-232

### M-645 · Zoom to Cursor · Slow
- Variant of M-232. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-232

### M-920 · Zoom to Cursor · Gold
- Variant of M-232. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-232

### M-233 · Modal Pop
- **When to use:** A dialog pops up over a dimmed background.
- **Content the user must provide:** text: the title; text: the text to show
- **Duration:** 0.3s
- **Easing:** easeOutBack
- **Spec:** The background dims to about 55% black while a rounded dialog card scales from 90% to 102% to 100% over 0.3s.

### M-384 · Modal Pop · Fast
- Variant of M-233. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-233

### M-659 · Modal Pop · Slow
- Variant of M-233. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-233

### M-934 · Modal Pop · Gold
- Variant of M-233. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-233

### M-234 · Toggle Switch
- **When to use:** A switch flips from off to on.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.3s
- **Easing:** easeInOutCubic
- **Spec:** A pill toggle: the knob slides to the other side over 0.3s while the track color changes from gray to the accent.

### M-398 · Toggle Switch · Fast
- Variant of M-234. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-234

### M-673 · Toggle Switch · Slow
- Variant of M-234. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-234

### M-948 · Toggle Switch · Gold
- Variant of M-234. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-234

### M-235 · Loading Spinner
- **When to use:** A "one moment" spinner before the result.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop · 0.8s
- **Easing:** linear
- **Spec:** A ring with one accent segment rotates one full turn every 0.8s; replace it with the result when it finishes.

### M-410 · Loading Spinner · Fast
- Variant of M-235. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-235

### M-685 · Loading Spinner · Slow
- Variant of M-235. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-235

### M-960 · Loading Spinner · Gold
- Variant of M-235. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-235

### M-236 · Notification Stack
- **When to use:** Notifications stacking up, like many messages arriving.
- **Content the user must provide:** text: the messages (one per line)
- **Duration:** 0.3s each
- **Easing:** spring
- **Spec:** Notification cards drop in from the top one after another, 0.4s apart; each new card pushes the earlier ones down slightly.

### M-422 · Notification Stack · Fast
- Variant of M-236. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-236

### M-697 · Notification Stack · Slow
- Variant of M-236. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-236

### M-972 · Notification Stack · Gold
- Variant of M-236. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-236

### M-237 · Keyboard Shortcut
- **When to use:** Shows a shortcut like Ctrl + C being pressed.
- **Content the user must provide:** text: the keys (e.g. Ctrl + C)
- **Duration:** 0.6s
- **Easing:** easeOut
- **Spec:** Key caps appear side by side; each key presses down (moves 2% and turns accent) in order, 0.15s apart.

### M-433 · Keyboard Shortcut · Fast
- Variant of M-237. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-237

### M-708 · Keyboard Shortcut · Slow
- Variant of M-237. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-237

### M-983 · Keyboard Shortcut · Gold
- Variant of M-237. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-237

### M-238 · Tab Switch
- **When to use:** Tabs change and the content slides.
- **Content the user must provide:** text: the items (comma-separated)
- **Duration:** 0.35s
- **Easing:** easeInOutCubic
- **Spec:** An accent underline slides from one tab to the next while the content panel slides across in the same direction over 0.35s.

### M-443 · Tab Switch · Fast
- Variant of M-238. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-238

### M-718 · Tab Switch · Slow
- Variant of M-238. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-238

### M-993 · Tab Switch · Gold
- Variant of M-238. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-238

### M-239 · Form Fill
- **When to use:** Form fields fill in one after another, for tutorials.
- **Content the user must provide:** text: the fields and their values
- **Duration:** ~0.8s per field
- **Easing:** steps
- **Spec:** Each labelled field types its value in order (see M-082), and a checkmark appears at the end of each field when done.

### M-452 · Form Fill · Fast
- Variant of M-239. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-239

### M-727 · Form Fill · Slow
- Variant of M-239. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-239

### M-240 · Upload Progress
- **When to use:** A file uploading with a progress bar.
- **Content the user must provide:** text: the file name
- **Duration:** 1.2s
- **Easing:** easeInOutCubic
- **Spec:** A file card with an icon and name shows a progress bar filling from 0 to 100% while the percentage counts up, then a check appears.

### M-461 · Upload Progress · Fast
- Variant of M-240. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-240

### M-736 · Upload Progress · Slow
- Variant of M-240. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-240

## TRK — Tracking

### M-241 · Label Follow
- **When to use:** A label that sticks to a moving object.
- **Content the user must provide:** text: what to track (e.g. the red cup); text: the text to show
- **Duration:** live
- **Easing:** tracked
- **Spec:** Track a point on the object (optical flow or a tracker) and attach a label with a small pointer above it; the label follows the point every frame with slight smoothing.

### M-287 · Label Follow · Fast
- Variant of M-241. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-241

### M-562 · Label Follow · Slow
- Variant of M-241. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-241

### M-837 · Label Follow · Gold
- Variant of M-241. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-241

### M-242 · Tracking Ring
- **When to use:** A ring that follows an object to point it out.
- **Content the user must provide:** text: what to track (e.g. the red cup)
- **Duration:** live
- **Easing:** tracked
- **Spec:** Track the object and draw a mint ring slightly larger than it, centered on the tracked point, with a soft pulse.

### M-301 · Tracking Ring · Fast
- Variant of M-242. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-242

### M-576 · Tracking Ring · Slow
- Variant of M-242. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-242

### M-851 · Tracking Ring · Gold
- Variant of M-242. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-242

### M-243 · Face Blur
- **When to use:** Hides a face or a plate for privacy.
- **Content the user must provide:** No content needed from you.
- **Duration:** live
- **Easing:** tracked
- **Spec:** Detect and track the face (or plate) and cover it with a rounded box that blurs what is behind it about 2.5%, following it every frame.

### M-315 · Face Blur · Fast
- Variant of M-243. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-243

### M-590 · Face Blur · Slow
- Variant of M-243. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-243

### M-865 · Face Blur · Gold
- Variant of M-243. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-243

### M-244 · Callout Line
- **When to use:** A line draws from an object to a note beside it.
- **Content the user must provide:** text: what to track (e.g. the red cup); text: the text to show
- **Duration:** 0.6s
- **Easing:** easeInOutCubic
- **Spec:** A thin line draws from the tracked point to a corner over 0.6s, then a small note box fades in at the end of the line.

### M-329 · Callout Line · Fast
- Variant of M-244. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-244

### M-604 · Callout Line · Slow
- Variant of M-244. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-244

### M-879 · Callout Line · Gold
- Variant of M-244. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-244

### M-245 · Screen Replace
- **When to use:** Puts another image inside a phone screen in the video.
- **Content the user must provide:** file: a screenshot or screen recording (it appears inside the frame)
- **Duration:** live
- **Easing:** tracked
- **Spec:** Track the four corners of the screen in the footage and warp your image or recording onto that quad every frame (corner pin), with a slight glare overlay.

### M-343 · Screen Replace · Fast
- Variant of M-245. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-245

### M-618 · Screen Replace · Slow
- Variant of M-245. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-245

### M-893 · Screen Replace · Gold
- Variant of M-245. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-245

### M-246 · Arrow Follow
- **When to use:** An arrow that keeps pointing at a moving thing.
- **Content the user must provide:** text: what to track (e.g. the red cup)
- **Duration:** live
- **Easing:** tracked
- **Spec:** Track the object and keep an accent arrow just above it pointing down, bobbing slightly while it follows.

### M-357 · Arrow Follow · Fast
- Variant of M-246. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-246

### M-632 · Arrow Follow · Slow
- Variant of M-246. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-246

### M-907 · Arrow Follow · Gold
- Variant of M-246. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-246

### M-247 · Emoji Follow
- **When to use:** A sticker or emoji that follows a moving object.
- **Content the user must provide:** text: what to track (e.g. the red cup); file: the sticker or emoji image
- **Duration:** live
- **Easing:** tracked
- **Spec:** Track the object and stick a sticker (or emoji image) on it, scaled to its size and following its position and rotation.

### M-371 · Emoji Follow · Fast
- Variant of M-247. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-247

### M-646 · Emoji Follow · Slow
- Variant of M-247. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-247

### M-921 · Emoji Follow · Gold
- Variant of M-247. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-247

### M-248 · Path Trace
- **When to use:** Draws the path an object travelled.
- **Content the user must provide:** text: what to track (e.g. the red cup)
- **Duration:** live
- **Easing:** linear
- **Spec:** Track the object and draw a dashed accent line along its past positions that builds up as it moves.

### M-385 · Path Trace · Fast
- Variant of M-248. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-248

### M-660 · Path Trace · Slow
- Variant of M-248. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-248

### M-935 · Path Trace · Gold
- Variant of M-248. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-248

## D3 — 3D

### M-249 · 3D Spin Text
- **When to use:** A word spinning around its vertical axis in 3D.
- **Content the user must provide:** text: the text to show
- **Duration:** loop · 3s
- **Easing:** linear
- **Spec:** Rotate the text around the Y axis with perspective, one full turn every 3s; keep the back face visible or mirrored.

### M-288 · 3D Spin Text · Fast
- Variant of M-249. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-249

### M-563 · 3D Spin Text · Slow
- Variant of M-249. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-249

### M-838 · 3D Spin Text · Gold
- Variant of M-249. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-249

### M-250 · Extruded Text
- **When to use:** Thick extruded text like a solid object.
- **Content the user must provide:** text: the text to show
- **Duration:** loop · 4s
- **Easing:** easeInOutSine
- **Spec:** Give the text a stacked, darker accent depth (6–10 offset layers) and gently tilt it in 3D (±14°) on a 4s loop.

### M-302 · Extruded Text · Fast
- Variant of M-250. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-250

### M-577 · Extruded Text · Slow
- Variant of M-250. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-250

### M-852 · Extruded Text · Gold
- Variant of M-250. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-250

### M-251 · Parallax 2.5D
- **When to use:** A still photo moves in layers as if it has depth.
- **Content the user must provide:** file: the image(s)
- **Duration:** loop · 4s
- **Easing:** easeInOutSine
- **Spec:** Separate the subject from the background (matte or depth map); move the background slowly one way and the subject the other way, with a 115% scale to hide edges.

### M-316 · Parallax 2.5D · Fast
- Variant of M-251. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-251

### M-591 · Parallax 2.5D · Slow
- Variant of M-251. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-251

### M-866 · Parallax 2.5D · Gold
- Variant of M-251. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-251

### M-252 · Card Flip
- **When to use:** A card flips to reveal the answer.
- **Content the user must provide:** text: the text to show
- **Duration:** 0.6s
- **Easing:** easeInOutCubic
- **Spec:** A card rotates 180° around the Y axis with perspective over 0.6s, showing its back side with the reveal text.

### M-330 · Card Flip · Fast
- Variant of M-252. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-252

### M-605 · Card Flip · Slow
- Variant of M-252. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-252

### M-880 · Card Flip · Gold
- Variant of M-252. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-252

### M-253 · Cube Spin
- **When to use:** A spinning 3D cube for a logo or product.
- **Content the user must provide:** file: your logo (transparent PNG)
- **Duration:** loop · 4s
- **Easing:** linear
- **Spec:** Build a cube from six faces with preserve-3d, tilt it -20° on X and rotate it a full turn on Y every 4s; put the logo on the faces.

### M-344 · Cube Spin · Fast
- Variant of M-253. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-253

### M-619 · Cube Spin · Slow
- Variant of M-253. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-253

### M-894 · Cube Spin · Gold
- Variant of M-253. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-253

### M-254 · Tilt Card
- **When to use:** A card tilting as if held in your hand.
- **Content the user must provide:** file: the image(s)
- **Duration:** loop · 4s
- **Easing:** easeInOutSine
- **Spec:** Tilt a card on X and Y (±12–16°) with perspective on a smooth 4s loop, with a soft shadow beneath it.

### M-358 · Tilt Card · Fast
- Variant of M-254. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-254

### M-633 · Tilt Card · Slow
- Variant of M-254. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-254

### M-908 · Tilt Card · Gold
- Variant of M-254. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-254

### M-255 · Layer Explode
- **When to use:** Design layers separate apart in 3D.
- **Content the user must provide:** file: the image(s)
- **Duration:** 0.8s
- **Easing:** easeInOutCubic
- **Spec:** Tilt a stack of layers into an isometric view and push each layer apart on Z (0, 8%, 16%…), then bring them back together.

### M-372 · Layer Explode · Fast
- Variant of M-255. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-255

### M-647 · Layer Explode · Slow
- Variant of M-255. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-255

### M-922 · Layer Explode · Gold
- Variant of M-255. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-255

### M-256 · 3D Carousel
- **When to use:** Cards rotating on a 3D ring to show several items.
- **Content the user must provide:** file: the image(s)
- **Duration:** loop · 6s
- **Easing:** linear
- **Spec:** Place 5–8 cards evenly around a 3D ring (rotateY steps + translateZ) and rotate the ring slowly.

### M-386 · 3D Carousel · Fast
- Variant of M-256. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-256

### M-661 · 3D Carousel · Slow
- Variant of M-256. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-256

### M-936 · 3D Carousel · Gold
- Variant of M-256. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-256

### M-257 · Float Shadow
- **When to use:** A product or logo floats with a shadow that changes below it.
- **Content the user must provide:** file: the image(s)
- **Duration:** loop · 3s
- **Easing:** easeInOutSine
- **Spec:** Bob the object up 6% with a slight rotation while its drop shadow grows softer and lighter at the top of the motion.

### M-399 · Float Shadow · Fast
- Variant of M-257. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-257

### M-674 · Float Shadow · Slow
- Variant of M-257. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-257

### M-949 · Float Shadow · Gold
- Variant of M-257. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-257

### M-258 · Coin Flip
- **When to use:** A coin tosses and flips, like heads or tails.
- **Content the user must provide:** file: your logo (transparent PNG)
- **Duration:** 1.2s
- **Easing:** easeInOutQuad
- **Spec:** A two-sided coin rises and falls while spinning several times around the Y axis over about 1.2s, landing on one face.

### M-411 · Coin Flip · Fast
- Variant of M-258. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-258

### M-686 · Coin Flip · Slow
- Variant of M-258. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-258

### M-961 · Coin Flip · Gold
- Variant of M-258. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-258

## TIM — Time FX

### M-259 · Reverse
- **When to use:** The clip plays backwards for surprise or fun.
- **Content the user must provide:** No content needed from you.
- **Duration:** clip length
- **Easing:** linear
- **Spec:** Play the selected segment backwards (frames in reverse order) and show a small "◀◀" tag in the corner.

### M-289 · Reverse · Fast
- Variant of M-259. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-259

### M-564 · Reverse · Slow
- Variant of M-259. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-259

### M-839 · Reverse · Gold
- Variant of M-259. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-259

### M-260 · Boomerang
- **When to use:** A short clip plays forward and back in a loop.
- **Content the user must provide:** No content needed from you.
- **Duration:** loop · 1s
- **Easing:** linear
- **Spec:** Take a 0.5–1s segment and play it forward then backward repeatedly, like a boomerang.

### M-303 · Boomerang · Fast
- Variant of M-260. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-260

### M-578 · Boomerang · Slow
- Variant of M-260. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-260

### M-853 · Boomerang · Gold
- Variant of M-260. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-260

### M-261 · Stop Motion
- **When to use:** Choppy, frame-by-frame motion like stop motion.
- **Content the user must provide:** No content needed from you.
- **Duration:** 12fps
- **Easing:** steps
- **Spec:** Drop the frame rate to about 8–12fps by holding each frame for 3–4 frames, giving a choppy stop-motion feel.

### M-317 · Stop Motion · Fast
- Variant of M-261. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-261

### M-592 · Stop Motion · Slow
- Variant of M-261. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-261

### M-867 · Stop Motion · Gold
- Variant of M-261. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-261

### M-262 · Strobe
- **When to use:** Frozen copies of a move stay behind it.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.8s
- **Easing:** steps
- **Spec:** Every 4 frames, freeze a copy of the person at about 35% opacity so the motion leaves a trail of still poses.

### M-331 · Strobe · Fast
- Variant of M-262. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-262

### M-606 · Strobe · Slow
- Variant of M-262. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-262

### M-881 · Strobe · Gold
- Variant of M-262. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-262

### M-263 · Time-Lapse Clock
- **When to use:** Clock hands spin fast, like "hours later".
- **Content the user must provide:** text: the text to show
- **Duration:** 1.5s
- **Easing:** linear
- **Spec:** A clock face with the minute hand spinning many turns and the hour hand moving slowly, for 1–2s, with a "+3h" style label.

### M-345 · Time-Lapse Clock · Fast
- Variant of M-263. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-263

### M-620 · Time-Lapse Clock · Slow
- Variant of M-263. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-263

### M-895 · Time-Lapse Clock · Gold
- Variant of M-263. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-263

### M-264 · Day to Night
- **When to use:** The lighting shifts as if time passes.
- **Content the user must provide:** No content needed from you.
- **Duration:** 2s
- **Easing:** easeInOutSine
- **Spec:** Grade the shot from warm daylight to a cool, darker night look over about 2s (color temperature, exposure and saturation).

### M-359 · Day to Night · Fast
- Variant of M-264. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-264

### M-634 · Day to Night · Slow
- Variant of M-264. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-264

### M-909 · Day to Night · Gold
- Variant of M-264. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-264

### M-265 · Fast Forward
- **When to use:** The clip speeds up with a ▶▶ tag.
- **Content the user must provide:** No content needed from you.
- **Duration:** clip length
- **Easing:** linear
- **Spec:** Play the segment at 2–4× speed with a "▶▶ 4×" tag and a light motion blur.

### M-373 · Fast Forward · Fast
- Variant of M-265. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-265

### M-648 · Fast Forward · Slow
- Variant of M-265. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-265

### M-923 · Fast Forward · Gold
- Variant of M-265. add a thin gold #FFC857 rim (about 0.5% wide) and a soft gold glow around the main element of this motion.
- **Content the user must provide:** same as M-265

### M-266 · Rewind Glitch
- **When to use:** A fast rewind with tape-like noise lines.
- **Content the user must provide:** No content needed from you.
- **Duration:** 0.6s
- **Easing:** steps
- **Spec:** Play the last second backwards at 3× with VHS noise lines (M-155) and a "◀◀ REW" tag, then cut back to normal.

### M-387 · Rewind Glitch · Fast
- Variant of M-266. the same motion 40% faster (multiply every duration by 0.6).
- **Content the user must provide:** same as M-266

### M-662 · Rewind Glitch · Slow
- Variant of M-266. the same motion 60% slower and smoother (multiply every duration by 1.6).
- **Content the user must provide:** same as M-266

### M-937 · Rewind Glitch · Gold
- Variant of M-266. use gold #FFC857 instead of the coral accent.
- **Content the user must provide:** same as M-266

## Fonts

- When the user names a font by ID (e.g. `FA-02`) or by name, use exactly that font. Arabic fonts are FA-xx, English fonts are FE-xx.
- All fonts are free (OFL). If the font is not installed, download it from the Google Fonts link or the site file and register it (@font-face or install) before rendering.
- Use an Arabic font for Arabic text. English fonts do not cover Arabic glyphs.
- For variable fonts pick the weight you need (e.g. 800 for titles).

| ID | Name | Lang | Type | Weights | Google Fonts |
|---|---|---|---|---|---|
| FA-01 | Alan Sans | Arabic | Sans | 300–900 (variable) | https://fonts.google.com/specimen/Alan+Sans |
| FA-02 | Alexandria | Arabic | Sans | 100–900 (variable) | https://fonts.google.com/specimen/Alexandria |
| FA-03 | Alkalami | Arabic | Serif | 400 | https://fonts.google.com/specimen/Alkalami |
| FA-04 | Almarai | Arabic | Sans | 300, 400, 700, 800 | https://fonts.google.com/specimen/Almarai |
| FA-05 | Alyamama | Arabic | Serif | 300–900 (variable) | https://fonts.google.com/specimen/Alyamama |
| FA-06 | Amiri | Arabic | Serif | 400, 700 | https://fonts.google.com/specimen/Amiri |
| FA-07 | Amiri Quran | Arabic | Serif | 400 | https://fonts.google.com/specimen/Amiri+Quran |
| FA-08 | Aref Ruqaa | Arabic | Serif | 400, 700 | https://fonts.google.com/specimen/Aref+Ruqaa |
| FA-09 | Aref Ruqaa Ink | Arabic | Serif | 400, 700 | https://fonts.google.com/specimen/Aref+Ruqaa+Ink |
| FA-10 | Badeen Display | Arabic | Display | 400 | https://fonts.google.com/specimen/Badeen+Display |
| FA-11 | Baloo Bhaijaan 2 | Arabic | Display | 400–800 (variable) | https://fonts.google.com/specimen/Baloo+Bhaijaan+2 |
| FA-12 | Beiruti | Arabic | Sans | 200–900 (variable) | https://fonts.google.com/specimen/Beiruti |
| FA-13 | Blaka | Arabic | Display | 400 | https://fonts.google.com/specimen/Blaka |
| FA-14 | Blaka Hollow | Arabic | Display | 400 | https://fonts.google.com/specimen/Blaka+Hollow |
| FA-15 | Blaka Ink | Arabic | Display | 400 | https://fonts.google.com/specimen/Blaka+Ink |
| FA-16 | Cairo | Arabic | Display | 200–1000 (variable) | https://fonts.google.com/specimen/Cairo |
| FA-17 | Cairo Play | Arabic | Display | 200–1000 (variable) | https://fonts.google.com/specimen/Cairo+Play |
| FA-18 | Cascadia Code | Arabic | Sans | 200–700 (variable) | https://fonts.google.com/specimen/Cascadia+Code |
| FA-19 | Cascadia Mono | Arabic | Sans | 200–700 (variable) | https://fonts.google.com/specimen/Cascadia+Mono |
| FA-20 | Changa | Arabic | Sans | 200–800 (variable) | https://fonts.google.com/specimen/Changa |
| FA-21 | El Messiri | Arabic | Sans | 400–700 (variable) | https://fonts.google.com/specimen/El+Messiri |
| FA-22 | Estedad | Arabic | Sans | 100–900 (variable) | https://fonts.google.com/specimen/Estedad |
| FA-23 | Firjar | Arabic | Sans | 100–800 (variable) | https://fonts.google.com/specimen/Firjar |
| FA-24 | Fustat | Arabic | Sans | 200–800 (variable) | https://fonts.google.com/specimen/Fustat |
| FA-25 | Gulzar | Arabic | Serif | 400 | https://fonts.google.com/specimen/Gulzar |
| FA-26 | Handjet | Arabic | Display | 100–900 (variable) | https://fonts.google.com/specimen/Handjet |
| FA-27 | Harmattan | Arabic | Sans | 400, 500, 600, 700 | https://fonts.google.com/specimen/Harmattan |
| FA-28 | IBM Plex Sans Arabic | Arabic | Sans | 100, 200, 300, 400, 500, 600, 700 | https://fonts.google.com/specimen/IBM+Plex+Sans+Arabic |
| FA-29 | Jomhuria | Arabic | Display | 400 | https://fonts.google.com/specimen/Jomhuria |
| FA-30 | Katibeh | Arabic | Display | 400 | https://fonts.google.com/specimen/Katibeh |
| FA-31 | Kufam | Arabic | Sans | 400–900 (variable) | https://fonts.google.com/specimen/Kufam |
| FA-32 | Lalezar | Arabic | Sans | 400 | https://fonts.google.com/specimen/Lalezar |
| FA-33 | Lateef | Arabic | Serif | 200, 300, 400, 500, 600, 700, 800 | https://fonts.google.com/specimen/Lateef |
| FA-34 | Lemonada | Arabic | Display | 300–700 (variable) | https://fonts.google.com/specimen/Lemonada |
| FA-35 | Mada | Arabic | Sans | 200–900 (variable) | https://fonts.google.com/specimen/Mada |
| FA-36 | Marhey | Arabic | Display | 300–700 (variable) | https://fonts.google.com/specimen/Marhey |
| FA-37 | Markazi Text | Arabic | Serif | 400–700 (variable) | https://fonts.google.com/specimen/Markazi+Text |
| FA-38 | Mirza | Arabic | Serif | 400, 500, 600, 700 | https://fonts.google.com/specimen/Mirza |
| FA-39 | Noto Kufi Arabic | Arabic | Sans | 100–900 (variable) | https://fonts.google.com/specimen/Noto+Kufi+Arabic |
| FA-40 | Noto Naskh Arabic | Arabic | Serif | 400–700 (variable) | https://fonts.google.com/specimen/Noto+Naskh+Arabic |
| FA-41 | Noto Naskh Arabic UI | Arabic | Serif | 400–700 (variable) | https://fonts.google.com/specimen/Noto+Naskh+Arabic+UI |
| FA-42 | Noto Nastaliq Urdu | Arabic | Serif | 400–700 (variable) | https://fonts.google.com/specimen/Noto+Nastaliq+Urdu |
| FA-43 | Noto Sans Arabic | Arabic | Sans | 100–900 (variable) | https://fonts.google.com/specimen/Noto+Sans+Arabic |
| FA-44 | Noto Sans Arabic UI | Arabic | Sans | 100–900 (variable) | https://fonts.google.com/specimen/Noto+Sans+Arabic+UI |
| FA-45 | Oi | Arabic | Display | 400 | https://fonts.google.com/specimen/Oi |
| FA-46 | Parastoo | Arabic | Serif | 400–700 (variable) | https://fonts.google.com/specimen/Parastoo |
| FA-47 | Playpen Sans Arabic | Arabic | Handwriting | 100–800 (variable) | https://fonts.google.com/specimen/Playpen+Sans+Arabic |
| FA-48 | Qahiri | Arabic | Sans | 400 | https://fonts.google.com/specimen/Qahiri |
| FA-49 | Rakkas | Arabic | Display | 400 | https://fonts.google.com/specimen/Rakkas |
| FA-50 | Readex Pro | Arabic | Sans | 160–700 (variable) | https://fonts.google.com/specimen/Readex+Pro |
| FA-51 | Reem Kufi | Arabic | Sans | 400–700 (variable) | https://fonts.google.com/specimen/Reem+Kufi |
| FA-52 | Reem Kufi Fun | Arabic | Sans | 400–700 (variable) | https://fonts.google.com/specimen/Reem+Kufi+Fun |
| FA-53 | Reem Kufi Ink | Arabic | Sans | 400 | https://fonts.google.com/specimen/Reem+Kufi+Ink |
| FA-54 | Rubik | Arabic | Sans | 300–900 (variable) | https://fonts.google.com/specimen/Rubik |
| FA-55 | Ruwudu | Arabic | Serif | 400, 500, 600, 700 | https://fonts.google.com/specimen/Ruwudu |
| FA-56 | Scheherazade New | Arabic | Serif | 400, 500, 600, 700 | https://fonts.google.com/specimen/Scheherazade+New |
| FA-57 | Tajawal | Arabic | Sans | 200, 300, 400, 500, 700, 800, 900 | https://fonts.google.com/specimen/Tajawal |
| FA-58 | Thabit | Arabic | Serif | 400, 700 | https://fonts.google.com/specimen/Thabit |
| FA-59 | Vazirmatn | Arabic | Sans | 100–900 (variable) | https://fonts.google.com/specimen/Vazirmatn |
| FA-60 | Vibes | Arabic | Display | 400 | https://fonts.google.com/specimen/Vibes |
| FA-61 | Zain | Arabic | Sans | 200, 300, 400, 700, 800, 900 | https://fonts.google.com/specimen/Zain |
| FE-01 | Abril Fatface | English | Display | 400 | https://fonts.google.com/specimen/Abril+Fatface |
| FE-02 | Anton | English | Display | 400 | https://fonts.google.com/specimen/Anton |
| FE-03 | Archivo | English | Sans | 100–900 (variable) | https://fonts.google.com/specimen/Archivo |
| FE-04 | Audiowide | English | Display | 400 | https://fonts.google.com/specimen/Audiowide |
| FE-05 | Bangers | English | Display | 400 | https://fonts.google.com/specimen/Bangers |
| FE-06 | Barlow | English | Sans | 100, 200, 300, 400, 500, 600, 700, 800, 900 | https://fonts.google.com/specimen/Barlow |
| FE-07 | Barlow Condensed | English | Sans | 100, 200, 300, 400, 500, 600, 700, 800, 900 | https://fonts.google.com/specimen/Barlow+Condensed |
| FE-08 | Bebas Neue | English | Display | 400 | https://fonts.google.com/specimen/Bebas+Neue |
| FE-09 | Bricolage Grotesque | English | Sans | 200–800 (variable) | https://fonts.google.com/specimen/Bricolage+Grotesque |
| FE-10 | Caveat | English | Handwriting | 400–700 (variable) | https://fonts.google.com/specimen/Caveat |
| FE-11 | Chakra Petch | English | Sans | 300, 400, 500, 600, 700 | https://fonts.google.com/specimen/Chakra+Petch |
| FE-12 | Chivo | English | Sans | 100–900 (variable) | https://fonts.google.com/specimen/Chivo |
| FE-13 | Cormorant Garamond | English | Serif | 300–700 (variable) | https://fonts.google.com/specimen/Cormorant+Garamond |
| FE-14 | Dancing Script | English | Handwriting | 400–700 (variable) | https://fonts.google.com/specimen/Dancing+Script |
| FE-15 | DM Sans | English | Sans | 100–1000 (variable) | https://fonts.google.com/specimen/DM+Sans |
| FE-16 | DM Serif Display | English | Serif | 400 | https://fonts.google.com/specimen/DM+Serif+Display |
| FE-17 | Exo 2 | English | Sans | 100–900 (variable) | https://fonts.google.com/specimen/Exo+2 |
| FE-18 | Fira Code | English | Mono | 300–700 (variable) | https://fonts.google.com/specimen/Fira+Code |
| FE-19 | Fira Sans | English | Sans | 100, 200, 300, 400, 500, 600, 700, 800, 900 | https://fonts.google.com/specimen/Fira+Sans |
| FE-20 | Fraunces | English | Serif | 100–900 (variable) | https://fonts.google.com/specimen/Fraunces |
| FE-21 | IBM Plex Mono | English | Mono | 100, 200, 300, 400, 500, 600, 700 | https://fonts.google.com/specimen/IBM+Plex+Mono |
| FE-22 | IBM Plex Sans | English | Sans | 100–700 (variable) | https://fonts.google.com/specimen/IBM+Plex+Sans |
| FE-23 | IBM Plex Serif | English | Serif | 100, 200, 300, 400, 500, 600, 700 | https://fonts.google.com/specimen/IBM+Plex+Serif |
| FE-24 | Inter | English | Sans | 100–900 (variable) | https://fonts.google.com/specimen/Inter |
| FE-25 | JetBrains Mono | English | Mono | 100–800 (variable) | https://fonts.google.com/specimen/JetBrains+Mono |
| FE-26 | Josefin Sans | English | Sans | 100–700 (variable) | https://fonts.google.com/specimen/Josefin+Sans |
| FE-27 | Jost | English | Sans | 100–900 (variable) | https://fonts.google.com/specimen/Jost |
| FE-28 | Lexend | English | Sans | 100–900 (variable) | https://fonts.google.com/specimen/Lexend |
| FE-29 | Libre Baskerville | English | Serif | 400–700 (variable) | https://fonts.google.com/specimen/Libre+Baskerville |
| FE-30 | Lobster | English | Display | 400 | https://fonts.google.com/specimen/Lobster |
| FE-31 | Lora | English | Serif | 400–700 (variable) | https://fonts.google.com/specimen/Lora |
| FE-32 | Manrope | English | Sans | 200–800 (variable) | https://fonts.google.com/specimen/Manrope |
| FE-33 | Merriweather | English | Serif | 300–900 (variable) | https://fonts.google.com/specimen/Merriweather |
| FE-34 | Michroma | English | Sans | 400 | https://fonts.google.com/specimen/Michroma |
| FE-35 | Monoton | English | Display | 400 | https://fonts.google.com/specimen/Monoton |
| FE-36 | Montserrat | English | Sans | 100–900 (variable) | https://fonts.google.com/specimen/Montserrat |
| FE-37 | Nunito | English | Sans | 200–1000 (variable) | https://fonts.google.com/specimen/Nunito |
| FE-38 | Open Sans | English | Sans | 300–800 (variable) | https://fonts.google.com/specimen/Open+Sans |
| FE-39 | Orbitron | English | Sans | 400–900 (variable) | https://fonts.google.com/specimen/Orbitron |
| FE-40 | Oswald | English | Sans | 200–700 (variable) | https://fonts.google.com/specimen/Oswald |
| FE-41 | Outfit | English | Sans | 100–900 (variable) | https://fonts.google.com/specimen/Outfit |
| FE-42 | Pacifico | English | Handwriting | 400 | https://fonts.google.com/specimen/Pacifico |
| FE-43 | Permanent Marker | English | Handwriting | 400 | https://fonts.google.com/specimen/Permanent+Marker |
| FE-44 | Playfair Display | English | Serif | 400–900 (variable) | https://fonts.google.com/specimen/Playfair+Display |
| FE-45 | Plus Jakarta Sans | English | Sans | 200–800 (variable) | https://fonts.google.com/specimen/Plus+Jakarta+Sans |
| FE-46 | Poppins | English | Sans | 100, 200, 300, 400, 500, 600, 700, 800, 900 | https://fonts.google.com/specimen/Poppins |
| FE-47 | Quicksand | English | Sans | 300–700 (variable) | https://fonts.google.com/specimen/Quicksand |
| FE-48 | Rajdhani | English | Sans | 300, 400, 500, 600, 700 | https://fonts.google.com/specimen/Rajdhani |
| FE-49 | Raleway | English | Sans | 100–900 (variable) | https://fonts.google.com/specimen/Raleway |
| FE-50 | Righteous | English | Display | 400 | https://fonts.google.com/specimen/Righteous |
| FE-51 | Roboto | English | Sans | 100–900 (variable) | https://fonts.google.com/specimen/Roboto |
| FE-52 | Russo One | English | Sans | 400 | https://fonts.google.com/specimen/Russo+One |
| FE-53 | Sora | English | Sans | 100–800 (variable) | https://fonts.google.com/specimen/Sora |
| FE-54 | Source Sans 3 | English | Sans | 200–900 (variable) | https://fonts.google.com/specimen/Source+Sans+3 |
| FE-55 | Space Grotesk | English | Sans | 300–700 (variable) | https://fonts.google.com/specimen/Space+Grotesk |
| FE-56 | Space Mono | English | Mono | 400, 700 | https://fonts.google.com/specimen/Space+Mono |
| FE-57 | Syne | English | Display | 400–800 (variable) | https://fonts.google.com/specimen/Syne |
| FE-58 | Tektur | English | Sans | 400–900 (variable) | https://fonts.google.com/specimen/Tektur |
| FE-59 | Ubuntu | English | Sans | 300, 400, 500, 700 | https://fonts.google.com/specimen/Ubuntu |
| FE-60 | Unbounded | English | Sans | 200–900 (variable) | https://fonts.google.com/specimen/Unbounded |
| FE-61 | Urbanist | English | Sans | 100–900 (variable) | https://fonts.google.com/specimen/Urbanist |
| FE-62 | Work Sans | English | Sans | 100–900 (variable) | https://fonts.google.com/specimen/Work+Sans |

---
@alansari.tech · Instagram: instagram.com/alansari.tech · Telegram: t.me/alansari_tech