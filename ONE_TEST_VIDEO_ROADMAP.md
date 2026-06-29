# One Test Video Roadmap

Goal: make one finished 9:16 cartoon animal short before worrying about automation.

This roadmap is intentionally practical. The goal is not to build the full system yet. The goal is to prove that the format can work: same presenter, clear animal facts, fun cartoon scenes, good voice, readable captions, and a loopable ending.

Use [EPISODE-01-AXOLOTL.md](/Users/jorgenbergh/Documents/ai-cartoon-shorts-automation/EPISODE-01-AXOLOTL.md) as the first test episode unless you want to change animal. It already contains a ready-to-paste script, scene prompts, motion prompts, captions, and title ideas.

---

## 1. Recommended Stack For This First Test

### Best first-test stack

Use this stack if you are setting things up from scratch:

| Job | Recommended tool | Why this choice |
|---|---|---|
| Script and prompt planning | ChatGPT / Codex | You already have the episode pack here. No extra setup needed for the first test. |
| Character and scene images | Runway, or Gemini if you already use it | Runway is better as a future product stack because it has web tools and an API path. Gemini is fine for still images if you already have access. |
| Image-to-video animation | Runway | Strong current video tools, reference workflows, web UI, and API support later. |
| Voiceover | ElevenLabs Starter | Good voice quality, cheap entry plan, commercial license on paid plan, API path later. |
| Editing and captions | CapCut Desktop | Easiest for a non-technical first edit: timeline, auto captions, caption styling, music/SFX, export. |
| Final quality check | Your phone | Shorts/Reels/TikTok are phone-first, so the final review should happen on a phone screen. |

### Why I recommend this stack

For one test video, do not start with a complex cloud/API workflow. You will learn more by manually making one good video than by building automation before you know what "good" looks like.

Runway is the best first paid video tool to try because it can handle image/video generation in one creator-friendly interface and still has API support later. Its pricing page currently lists a Free plan with one-time credits, Standard at $15/month monthly or $12/month billed annually, and Pro at $35/month monthly or $28/month billed annually. Standard includes no watermarks and enough credits to make a short test if you are careful with regenerations.

ElevenLabs is worth paying for early because the presenter voice is part of the brand. Its Starter plan is currently $6/month and includes a commercial license. Do not start with ElevenLabs Pro unless you know you need higher volume or advanced audio quality.

CapCut is recommended because it is simple and built for this kind of short-form edit. It has auto captions, caption styling, video editing, and export in one place. Do not pay for CapCut Pro on day one unless a specific feature you need is locked.

### Tools I would not start with today

Do not start with Google Cloud / Vertex AI / Veo for this first manual test. Veo is strong and has a serious API path, but Google Cloud setup is more technical. It is better for a later automation phase.

Do not start with Adobe Premiere unless you already know it. It is powerful, but it slows down a first test.

Do not start with Midjourney unless you strongly prefer its look. It can make beautiful images, but the workflow is less direct for future automation.

Do not buy expensive plans yet. The first test is about learning the workflow and quality bar, not volume.

---

## 2. What You Need To Set Up

### A. Runway account

Purpose: create or animate the visual clips.

Simple setup:

1. Go to Runway's website.
2. Create an account with your email.
3. Start with the Free plan if you only want to test the interface.
4. Upgrade to Standard only when you are ready to export without watermarks and make enough generations for the full video.
5. Create a new project or folder called `Finn Axolotl Test`.
6. Upload/save your character reference image once you have it.
7. Use image-to-video for each scene, not pure text-to-video.

Important settings:

- Format: vertical `9:16`
- Target resolution: `1080x1920` if available
- Clip length: around `5 seconds`
- Motion: simple, clear, not chaotic
- Captions/text: do not generate text inside the AI video; add text later in CapCut

What to avoid:

- Do not ask the video model to invent Finn from scratch in every clip.
- Do not make long 20-30 second generated clips.
- Do not generate captions inside the video tool.
- Do not use complicated camera moves until the simple clips work.

### B. ElevenLabs account

Purpose: create the recurring presenter voice.

Simple setup:

1. Go to ElevenLabs.
2. Create an account.
3. Choose the Starter plan if you want to use the output commercially.
4. Go to text-to-speech.
5. Pick an energetic, young, friendly male voice.
6. Paste only the script lines from [EPISODE-01-AXOLOTL.md](/Users/jorgenbergh/Documents/ai-cartoon-shorts-automation/EPISODE-01-AXOLOTL.md).
7. Generate the voiceover.
8. Download the result as an audio file, ideally `.mp3` or `.wav`.
9. Save it as `voiceover_axolotl_v1.mp3`.

Voice direction:

- Energetic but not shouting
- Fast but understandable
- Warm, curious, and playful
- Not a celebrity impression
- Same voice should be reusable in later episodes

If the word "axolotl" is pronounced badly, change the script spelling to:

```text
ax-oh-LOT-ull
```

What to avoid:

- Do not clone a real celebrity voice.
- Do not spend time perfecting a custom voice before the first video works.
- Do not make the script longer than about 35-40 seconds.

### C. CapCut Desktop account/app

Purpose: assemble the final video.

Simple setup:

1. Download CapCut Desktop.
2. Create or log in to an account.
3. Start a new project.
4. Set the canvas/aspect ratio to `9:16`.
5. Import the 7 video clips from Runway.
6. Import the ElevenLabs voiceover.
7. Place the voiceover on the timeline first.
8. Place each video clip above the matching voiceover line.
9. Trim clips so the picture changes exactly when the voice changes.
10. Use Auto Captions.
11. Fix any wrong words manually.
12. Style captions with large white text, black outline, and occasional keyword color.
13. Add soft background music very low under the voice.
14. Add 1 small sound effect per scene.
15. Export as vertical `1080p`.

Caption style:

- 2-5 words per caption chunk
- Big enough to read on a phone
- White text with dark outline
- Keep captions in the lower third
- Do not cover Finn's face or the animal's face
- Highlight only the most important words

What to avoid:

- Do not use tiny captions.
- Do not cover the animal.
- Do not make music louder than the voice.
- Do not add too many effects.

---

## 3. The Work Sequence For Today

### Step 1: Lock the format

Use this target:

```text
Length: 33-40 seconds
Aspect ratio: 9:16 vertical
Resolution: 1080x1920
Scenes: 7 short clips
Clip length: about 3-6 seconds each
Style: clean 3D cartoon, colorful, friendly, educational
Main character: Finn, original cartoon wildlife explorer
Episode animal: axolotl
```

Do not change these settings during the first test. Changing format mid-process creates confusion.

### Step 2: Create Finn once

Use Section A in [EPISODE-01-AXOLOTL.md](/Users/jorgenbergh/Documents/ai-cartoon-shorts-automation/EPISODE-01-AXOLOTL.md).

You need one good reference sheet of Finn before making scenes.

Pass/fail standard:

- Pass: Finn looks like an original cartoon presenter, not a real person.
- Pass: outfit is clear: khaki shirt, green bandana, brown field hat, boots.
- Pass: face is friendly and readable.
- Fail: he looks too realistic, too generic, or changes outfit between poses.
- Fail: the image includes text or logos.

Save the best image as:

```text
test-video-01-axolotl/character/finn_reference_sheet_v1.png
```

### Step 3: Generate the voiceover

Generate the ElevenLabs voiceover before animating all scenes. This tells you the real video length.

Use the script in Section C of [EPISODE-01-AXOLOTL.md](/Users/jorgenbergh/Documents/ai-cartoon-shorts-automation/EPISODE-01-AXOLOTL.md).

Pass/fail standard:

- Pass: total length is about 33-40 seconds.
- Pass: the first sentence starts immediately.
- Pass: it sounds excited but clear.
- Fail: too slow, flat, robotic, or mispronounces "axolotl."

Save as:

```text
test-video-01-axolotl/audio/voiceover_axolotl_v1.mp3
```

### Step 4: Generate the 7 still images

Use the 7 image prompts from Section F in [EPISODE-01-AXOLOTL.md](/Users/jorgenbergh/Documents/ai-cartoon-shorts-automation/EPISODE-01-AXOLOTL.md).

For each still image:

1. Paste the scene prompt.
2. Add the reusable axolotl look block.
3. Add the reusable series style block.
4. Keep the image vertical.
5. Reject any image with text, logos, extra limbs, wrong outfit, or strange anatomy.

Save images like this:

```text
test-video-01-axolotl/images/scene_01_hook.png
test-video-01-axolotl/images/scene_02_finn_intro.png
test-video-01-axolotl/images/scene_03_gills.png
test-video-01-axolotl/images/scene_04_never_grows_up.png
test-video-01-axolotl/images/scene_05_regrowth.png
test-video-01-axolotl/images/scene_06_one_lake.png
test-video-01-axolotl/images/scene_07_loop_smile.png
```

Pass/fail standard:

- Pass: all images feel like the same cartoon world.
- Pass: the axolotl is cute, recognizable, and consistent.
- Pass: Scene 7 looks very similar to Scene 1 for the loop.
- Fail: different art styles across scenes.
- Fail: captions/text baked into images.
- Fail: Finn's face or outfit changes badly.

### Step 5: Animate each still image

This is where your still pictures become moving video clips.

You will do the same basic process 7 times:

```text
Open Runway
Choose image-to-video
Upload one scene image
Paste the matching motion prompt
Generate a short clip
Download the clip
Rename it correctly
Repeat for the next scene
```

Important idea: do not ask Runway to create a totally new video from text. You already made the
picture. Now Runway's job is only to add movement to that picture.

#### Before you start

Make sure these files exist:

```text
test-video-01-axolotl/images/scene_01_hook.png
test-video-01-axolotl/images/scene_02_finn_intro.png
test-video-01-axolotl/images/scene_03_gills.png
test-video-01-axolotl/images/scene_04_never_grows_up.png
test-video-01-axolotl/images/scene_05_regrowth.png
test-video-01-axolotl/images/scene_06_one_lake.png
test-video-01-axolotl/images/scene_07_loop_smile.png
```

Also create this folder if it does not exist yet:

```text
test-video-01-axolotl/video/
```

#### Runway setup for each clip

In Runway:

1. Open your project.
2. Choose the video generation tool.
3. Choose **image-to-video** or the option that lets you start from an uploaded image.
4. Upload the correct scene image.
5. Set the format to vertical `9:16` if Runway asks.
6. Set the clip length to around `5 seconds` if you get a choice.
7. Paste the motion prompt for that scene.
8. Generate the clip.
9. Watch the clip once before downloading.
10. Download it only if it passes the checks below.

If Runway offers different model or quality settings, choose the normal/high-quality creative
video option. Do not choose the fastest/cheapest mode if it visibly damages the character or
animal.

#### Motion prompts to paste

Use these exact prompts, one at a time.

Scene 1:

```text
slow push-in on the axolotl's face; gills wave gently; it blinks once
```

Scene 2:

```text
Keep Finn as the clear main subject in the center-left foreground. Medium shot focused on Finn's face and upper body; Finn leans slightly toward the camera, smiles, and points down toward the water. Very subtle camera push-in on Finn. Background leaves rustle gently, but do not shift focus away from Finn.
```

Scene 3:

```text
gentle side-orbit around the axolotl; the feathery gills sway in the current
```

Scene 4:

```text
the little axolotl wiggles and swims happily across the frame
```

Scene 5:

```text
the glowing leg sparkles and a new little leg smoothly forms; the glow softly pulses
```

Scene 6:

```text
slow zoom-out / pull-back revealing the lone axolotl in the big quiet lake
```

Scene 7:

```text
the axolotl's smile slowly widens and it blinks; gills wave; match the opening shot
```

#### What a good clip looks like

Good motion is usually subtle. For this first test, a small camera push, blink, gill movement,
water movement, or gentle character gesture is enough.

Do not chase dramatic movement yet. Big movement is where AI video often breaks the character.

Keep the clip if:

- The axolotl or Finn still looks like the original image.
- The motion is easy to understand.
- The camera movement is smooth.
- The face does not warp.
- The body does not grow extra parts.
- The clip still looks like a cartoon, not a realistic animal/human.
- The clip has no text, watermark, or random logo.

Regenerate the clip if:

- Finn's face changes badly.
- The axolotl melts, grows extra legs, or loses its gills.
- The camera spins or moves too fast.
- The clip adds random text.
- The image becomes blurry.
- The animation distracts from the fact being explained.

#### How many times should you regenerate?

For the first test, use this rule:

```text
Try each scene up to 3 times.
If one version is usable, keep it and move on.
Only spend more attempts on Scene 1, Scene 2, or Scene 7.
```

Why: Scene 1 stops the scroll, Scene 2 introduces Finn, and Scene 7 creates the loop. Those are
worth extra effort. The middle fact scenes only need to be clear and consistent.

#### Download and rename each clip

When a clip is good enough, download it and rename it immediately.

Use these exact filenames:

```text
test-video-01-axolotl/video/scene_01_hook.mp4
test-video-01-axolotl/video/scene_02_finn_intro.mp4
test-video-01-axolotl/video/scene_03_gills.mp4
test-video-01-axolotl/video/scene_04_never_grows_up.mp4
test-video-01-axolotl/video/scene_05_regrowth.mp4
test-video-01-axolotl/video/scene_06_one_lake.mp4
test-video-01-axolotl/video/scene_07_loop_smile.mp4
```

Do not leave files with names like `runwayml_video_23748.mp4`. You will get confused in CapCut.

#### Simple scene-by-scene notes

Scene 1 is the hook. The axolotl face should be clear immediately. Avoid a slow reveal.

Scene 2 is the only Finn scene. It matters that Finn looks correct. If the hand or pointing
gesture is imperfect but his face and outfit are good, keep it.

Scene 3 is about the gills. The gills should move gently and stay visible.

Scene 4 is about staying baby-like. Cute swimming motion is enough.

Scene 5 is about regrowth. It must be magical and clean, not gross. If it looks gory, reject it.

Scene 6 is about rarity. Slow zoom-out is better than lots of movement.

Scene 7 should look close to Scene 1. This helps the video loop when it restarts.

Pass/fail standard:

- Pass: the clip has gentle motion.
- Pass: character/animal stays recognizable.
- Pass: no weird extra limbs or face warping.
- Pass: no random text or watermark.
- Fail: wild camera movement.
- Fail: animal body melts or changes.
- Fail: clip feels unrelated to the still image.
- Fail: clip is too blurry to use on a phone.

### Step 6: Assemble in CapCut

Timeline order:

```text
Voiceover first
Scene 1 video
Scene 2 video
Scene 3 video
Scene 4 video
Scene 5 video
Scene 6 video
Scene 7 video
Auto captions
Music
Sound effects
```

Editing rules:

- Start with picture and voice immediately.
- Cut whenever the voice moves to a new idea.
- Keep captions readable.
- Keep music low.
- Add small SFX only where useful.
- End Scene 7 so it visually loops back into Scene 1.

Export settings:

```text
Format: MP4
Aspect ratio: 9:16
Resolution: 1080p
Frame rate: 30 fps
Filename: axolotl_test_v1.mp4
```

### Step 7: Watch it like a viewer

Send the exported video to your phone and watch it three times:

1. First watch: does the first second stop you?
2. Second watch: can you read every caption?
3. Third watch: does the ending loop smoothly into the beginning?

Do not judge it on a big desktop monitor only. This format lives on a phone.

---

## 4. Pass/Fail Checklist

The test video is a success if:

- It is 33-40 seconds long.
- It is vertical 9:16.
- The voice starts immediately.
- The first 2 seconds are visually interesting.
- Finn looks like the same character wherever he appears.
- The axolotl looks consistent across scenes.
- Captions are readable on a phone.
- The facts are understandable without pausing.
- Music does not fight the voice.
- There are no watermarks.
- There is no accidental text/logos inside generated images.
- The ending visually connects back to the beginning.

The test video needs another edit if:

- The first 3 seconds feel slow.
- The voiceover is longer than 45 seconds.
- Captions are too small.
- The art style changes scene to scene.
- AI motion looks broken.
- The viewer cannot tell what animal it is.
- The final export looks blurry.

---

## 5. Budget Guidance

Reasonable first-month budget:

```text
Runway Standard: about $15 if paid monthly
ElevenLabs Starter: about $6
CapCut: $0 to start
Total: about $21 before taxes, if monthly prices are available in your region
```

Possible extra cost:

- More Runway credits if you regenerate many clips.
- ElevenLabs Creator if you later need more voice minutes or professional voice cloning.
- CapCut Pro only if you hit a specific locked feature that clearly matters.

Do not buy:

- Runway Max on day one.
- ElevenLabs Pro on day one.
- Adobe subscription on day one.
- A stock music subscription on day one.
- Google Cloud credits for the first manual test.

---

## 6. Biggest Creative Risks

### Risk 1: Character inconsistency

Fix: make Finn's reference sheet first and keep using it. Do not let every scene reinvent him.

### Risk 2: Bad AI motion

Fix: animate still images instead of starting from text. Keep motion prompts simple.

### Risk 3: Weak pacing

Fix: use 7 short scenes and keep the voiceover under 40 seconds.

### Risk 4: Captions that look amateur

Fix: use short caption chunks, strong contrast, and phone-size review.

### Risk 5: Spending too much before learning

Fix: buy only the minimum paid plans needed to remove watermarks and get commercial voice use.

---

## 7. What Not To Automate Yet

Do not automate these until one manual video is good:

- Animal/topic selection
- Script generation
- Prompt generation
- Video rendering
- Publishing
- Analytics collection
- Multi-platform formatting
- API orchestration

First prove the format manually. Then automate the parts that are repetitive.

---

## 8. Exact Deliverable For Today

By the end of the first test, you should have:

```text
axolotl_test_v1.mp4
```

And this source folder:

```text
test-video-01-axolotl/
  character/
    finn_reference_sheet_v1.png
  audio/
    voiceover_axolotl_v1.mp3
  images/
    scene_01_hook.png
    scene_02_finn_intro.png
    scene_03_gills.png
    scene_04_never_grows_up.png
    scene_05_regrowth.png
    scene_06_one_lake.png
    scene_07_loop_smile.png
  video/
    scene_01_hook.mp4
    scene_02_finn_intro.mp4
    scene_03_gills.mp4
    scene_04_never_grows_up.mp4
    scene_05_regrowth.mp4
    scene_06_one_lake.mp4
    scene_07_loop_smile.mp4
  final/
    axolotl_test_v1.mp4
```

---

## 9. Ranked Provider Stack

### Start now

1. Runway - best balance of quality, usability, and future automation path.
2. ElevenLabs - best early choice for a consistent recurring presenter voice.
3. CapCut Desktop - easiest manual assembly and captions.
4. ChatGPT / Codex - script, prompts, episode packs, review checklist.

### Consider later

1. Google Veo on Vertex AI - strong API video option later, but too technical for today's first manual test.
2. Remotion + FFmpeg - excellent automated rendering later, unnecessary for the first manual edit.
3. n8n / Temporal / custom Python orchestration - useful after you know the exact manual process.
4. PostgreSQL / cloud storage - useful once there are many episodes.

---

## 10. Sources Checked For Tool Recommendations

- Runway pricing and product/API availability: https://runwayml.com/pricing and https://docs.dev.runwayml.com/api/
- ElevenLabs pricing and text-to-speech API: https://elevenlabs.io/pricing and https://elevenlabs.io/docs/api-reference/text-to-speech/convert
- CapCut auto captions workflow: https://www.capcut.com/tools/auto-caption-generator
- Google Veo pricing comparison for later API use: https://cloud.google.com/vertex-ai/generative-ai/pricing
- OpenAI API documentation overview for script/image/audio/video model categories: https://platform.openai.com/docs/models
