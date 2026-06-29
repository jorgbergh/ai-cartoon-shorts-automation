# Episode 01 — Axolotl (ready-to-paste pack)

---

## ⭐ READ THIS FIRST — how the pieces fit together

Your finished video is **7 short clips played one after another**. Each clip is made in two
moves:

```
STEP 1: Runway makes ONE still picture for the scene   →   this is the scene's first frame.
STEP 2: Runway animates THAT picture for ~5 seconds    →   now it's a moving clip.
Repeat for all 7 scenes, then assemble the 7 clips in CapCut (+ voice, captions, music).
```

**The common misunderstanding (worth clearing up):** you might picture making "avatar pictures
from different angles" and pasting *those* into the video generator. That's one step off. The
avatar angles (the **reference sheet**) get pasted back into the **image tool** — Runway, or
Gemini if you already use it — so the tool can draw Finn the same way each time. What goes into
the **image-to-video tool (Runway)** is the finished **scene picture**. So:

```
Finn reference sheet   ──►  goes INTO Runway/Gemini   (job: keep Finn consistent)
A finished scene image ──►  goes INTO Runway          (job: add ~5 seconds of motion)
```

**Each scene image IS a finished frame of your video** — Runway just brings it to life.
7 scenes → 7 images → 7 clips → 1 video.

**Why make the still first?** You control how Finn and the axolotl look far better in an image
tool. If you let the video tool invent the picture from scratch, the character drifts in every
clip. So we *lock the picture*, then ask the video tool only to add *motion*.

### The two kinds of images (don't mix them up)
1. **Finn reference sheet** — made ONCE (Section A). A few pictures of Finn to lock his look so
   he's identical across every episode. You reuse these forever, by feeding them back into
   Runway or Gemini. They are *not* clips in the video.
2. **The 7 scene images** — made fresh for THIS episode (Section F). These are the actual
   frames of this video. Each one gets animated by Runway.

> **For this episode specifically:** Finn only appears in **Scene 2**. The other 6 scenes are
> the axolotl. So the reference sheet matters most for *future* videos (keeping Finn identical
> across many episodes) — but make it now so he's locked from the start.

All facts here are true. Axolotl is pronounced **"ACK-suh-LOT-ul"** — if ElevenLabs says it
wrong, type it in the script as `ax-oh-LOT-ull`.

---

## A. Finn reference sheet — make this ONCE (consistency setup)

**Purpose:** create a locked, reusable look for Finn. You are NOT putting these in the video —
you're building a visual "anchor" so every later picture of Finn matches.

In Runway's image tool, paste this. If you already prefer Gemini for still images, Gemini is
also fine here:

```
Create a character reference sheet for an original cartoon wildlife explorer named Finn (not a
real person). Show him in 4 poses on a plain light-grey background: front view, side view,
pointing excitedly, and a surprised face.

Finn's design (keep identical in all 4): young adult, warm light-tan skin, messy brown hair,
big round expressive dark eyes, small nose, wide cheerful smile. Outfit: khaki explorer shirt
with rolled-up sleeves, olive-green neck bandana, round brown field/safari hat, brown boots.
Slightly stocky, rounded, friendly proportions.

Style: clean 3D cartoon (Pixar-like but simple), soft rounded shapes, bright warm lighting,
vibrant colors, family-friendly.
```

When you like the result, save it as your reusable Finn reference image. For every scene image
with Finn in it, upload or reference this same image and start your prompt with **"Same Finn
from the reference sheet, …"** — that's what keeps him consistent.

---

## B. Reusable building blocks (so every image matches)

You'll paste these into the scene prompts in Section F. Keeping them word-for-word is what makes
the whole video look like one series.

**Axolotl look:**
```
a cute cartoon axolotl: pale pink body, smooth salamander shape, wide friendly dark eyes, a
gentle permanent smile, and six feathery bright-pink external gills (three branching from each
side of its head), small stubby legs. Cute but recognizable, not scary.
```

**Series style (end every prompt with this):**
```
Clean 3D cartoon style, soft rounded shapes, bright warm lighting, vibrant colors, shallow
depth of field, family-friendly, detailed but uncluttered. Color palette: warm sandy tones for
Finn, soft pink for the axolotl, turquoise water, lush green plants. Vertical 9:16 format,
1080x1920, subject framed in the upper-middle so there is empty space in the lower third for
captions.
```

**Negative prompt (paste into the tool's "negative" box if it has one):**
```
no text, no watermark, no logo, not photorealistic, no extra limbs, no deformed anatomy,
no scary or gory imagery, no human celebrity likeness, no blurry faces.
```

---

## C. Voiceover script — paste into ElevenLabs

> Paste ONLY the 7 lines below (not the labels). Pick an energetic, young, friendly male voice.
> Target ~35 seconds. If it sounds flat, lower **Stability** slightly for more energy.

```
This animal can regrow its legs, its heart — even part of its brain.
Hey! I'm Finn, and this is the axolotl.
Those fluffy pink branches? Those are its gills — growing on the outside of its head.
And it never grows up. It stays a baby its whole life.
Cut off its leg, and it grows a brand-new one. Bones, nerves, everything.
But here's the weird part. In the wild, they're almost gone — nearly all of them live in one lake in Mexico.
Wait… did this one just smile at me?
```

---

## F. The 7 scenes (each becomes one clip)

For each scene you get:
- **Caption** — the on-screen text (CapCut can auto-make these; this is for checking).
- **Voiceover line** — the part of the script this clip plays under.
- **① IMAGE PROMPT** — paste into **Runway's image tool** to make the still frame. Gemini is
  also okay if you already use it for images.
- **② MOTION** — paste into **Runway image-to-video** when you animate that still.
- **SFX** — a sound effect to add in CapCut.

> Each prompt already includes WHO is in frame, the SHOT TYPE, the CAMERA ANGLE, the SETTING,
> and the LIGHTING — that's what makes a usable finished frame. Remember to paste the **Series
> style** block (Section B) at the end of each one, and add the **axolotl look** block where the
> axolotl appears.

---

### Scene 1 — HOOK (0–3s)
- **Caption:** `IT CAN REGROW` → `ITS OWN BRAIN`
- **Voiceover:** "This animal can regrow its legs, its heart — even part of its brain."
- **① IMAGE PROMPT (Runway image tool):**
```
Extreme macro close-up, eye-level, of [axolotl look], filling the upper two-thirds of a
vertical frame, underwater in clear turquoise water. Its feathery pink gills float gently. Soft
god-rays of sunlight come from above. Dreamy, slightly magical mood. [Series style block]
```
- **② MOTION (Runway image-to-video):** `slow push-in on the axolotl's face; gills wave gently; it blinks once`
- **SFX:** soft underwater shimmer + a tiny magical chime

---

### Scene 2 — FINN INTRO (3–6s)
- **Caption:** `MEET FINN`
- **Voiceover:** "Hey! I'm Finn, and this is the axolotl."
- **① IMAGE PROMPT (Runway image tool — use the Finn reference sheet):**
```
Same Finn from the reference sheet. Medium shot, low camera angle looking slightly up at him,
Finn crouching at the edge of a bright cartoon pond, grinning and pointing down toward the
water with one hand, lush green plants framing the sides, sunny daytime. Finn positioned on the
left so the water shows on the right. [Series style block]
```
- **② MOTION (Runway image-to-video):** `Finn leans in and points at the water with an excited grin; leaves rustle behind him`
- **SFX:** leaf rustle + a friendly "pop"

---

### Scene 3 — FACT 1, the gills (6–13s)
- **Caption:** `GILLS ON THE` → `OUTSIDE OF ITS HEAD`
- **Voiceover:** "Those fluffy pink branches? Those are its gills — growing on the outside of its head."
- **① IMAGE PROMPT (Runway image tool):**
```
Side profile, medium close-up of [axolotl look], underwater, the camera focused on the feathery
bright-pink external gills branching from the side of its head. Crisp detail on the gills, a few
small rising bubbles, clear turquoise water, soft light. [Series style block]
```
- **② MOTION (Runway image-to-video):** `gentle side-orbit around the axolotl; the feathery gills sway in the current`
- **SFX:** soft gentle bubbles

---

### Scene 4 — FACT 2, never grows up (13–20s)
- **Caption:** `IT NEVER` → `GROWS UP`
- **Voiceover:** "And it never grows up. It stays a baby its whole life."
- **① IMAGE PROMPT (Runway image tool):**
```
Full-body shot of a small, extra-cute [axolotl look] swimming happily across clear water, big
sparkling eyes, playful joyful expression, soft colorful bokeh background, bright and wholesome,
baby-creature feel. Centered with room below for captions. [Series style block]
```
- **② MOTION (Runway image-to-video):** `the little axolotl wiggles and swims happily across the frame`
- **SFX:** a cute twinkle / soft "boing"

---

### Scene 5 — FACT 3, regrowing a limb (20–28s)
- **Caption:** `LOSE A LEG?` → `GROWS A NEW ONE`
- **Voiceover:** "Cut off its leg, and it grows a brand-new one. Bones, nerves, everything."
- **① IMAGE PROMPT (Runway image tool):**
```
Medium close-up of [axolotl look] underwater, one front leg gently glowing with soft magical
blue-white light as a brand-new leg regrows, gentle sparkles around the glow, friendly and
wholesome (absolutely not gory), bright turquoise water. [Series style block]
```
- **② MOTION (Runway image-to-video):** `the glowing leg sparkles and a new little leg smoothly forms; the glow softly pulses`
- **SFX:** magical shimmer / soft whoosh

---

### Scene 6 — SURPRISE, almost extinct (28–33s)
- **Caption:** `ALMOST GONE` → `ONE LAKE IN MEXICO`
- **Voiceover:** "But here's the weird part. In the wild, they're almost gone — nearly all of them live in one lake in Mexico."
- **① IMAGE PROMPT (Runway image tool):**
```
Wide establishing shot, high camera angle looking down, of a single tiny axolotl alone in a
large calm lake with traditional floating gardens and canals (Xochimilco style), warm
late-afternoon golden light, gentle reeds, a quiet lonely "rare survivor" mood. The lone
axolotl small in the lower-middle of the frame. [Series style block]
```
- **② MOTION (Runway image-to-video):** `slow zoom-out / pull-back revealing the lone axolotl in the big quiet lake`
- **SFX:** a soft, low dramatic bass hit, then quiet ambience

---

### Scene 7 — LOOP ENDING (33–35s)
- **Caption:** `WAIT…` → `DID IT JUST SMILE?`
- **Voiceover:** "Wait… did this one just smile at me?"
- **① IMAGE PROMPT (Runway image tool):**
```
Extreme macro close-up, eye-level, of [axolotl look], underwater in clear turquoise water,
almost IDENTICAL framing and lighting to Scene 1, gills gently floating, soft god-rays from
above — but its smile is a little wider. [Series style block]
```
- **② MOTION (Runway image-to-video):** `the axolotl's smile slowly widens and it blinks; gills wave — match the opening shot`
- **SFX:** cute twinkle + a small "huh?" sting

> **Loop tip:** Scene 7 is deliberately almost the same as Scene 1. When the video restarts it
> feels seamless — that's what earns replays. Make the framing and lighting match.

---

## G. Caption summary (to check CapCut's auto-captions)

```
IT CAN REGROW / ITS OWN BRAIN
MEET FINN
GILLS ON THE / OUTSIDE OF ITS HEAD
IT NEVER / GROWS UP
LOSE A LEG? / GROWS A NEW ONE
ALMOST GONE / ONE LAKE IN MEXICO
WAIT… / DID IT JUST SMILE?
```

---

## H. Platform titles/captions (for when you publish the test)

- **YouTube Shorts title:** `This animal can regrow its own brain 🧠 #shorts`
- **TikTok caption:** `It regrows legs, heart, even brain 🤯 #axolotl #animals #wildlife`
- **Instagram Reels caption:** `Meet the axolotl — the animal that never grows up 🩷 #axolotl #animalfacts #reels`
- **Snapchat caption:** `This little guy can regrow its brain 😳`

> If you publish, tick the **"AI-generated / altered content"** box where the platform asks.
> It's cartoon, so requirements are light, but it keeps you safe.
