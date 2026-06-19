# Fully Automated Short-Form Video Production Plan

Below is a practical blueprint for building this as a **repeatable AI video production system**, not just a one-off content experiment.

One important framing point: use "Steve Irwin-style energy" as a **genre reference**, not as a likeness/voice/personality clone. Build an original presenter with their own name, look, voice, catchphrases, and mannerisms.

---

## 0. Core recommendation

Start with a **semi-automated pipeline** where the system generates everything, but you approve the episode before publishing. Once quality is stable, move toward full automation.

The best target format is:

**Length:** 25–45 seconds
**Format:** 9:16 vertical
**Resolution:** 1080×1920
**FPS:** 30
**Audio:** voiceover + light music + animal/environment SFX
**Structure:** hook → discovery → 2–3 facts → surprise → loop ending

This fits most short-form platforms well and avoids edge cases. YouTube Shorts can now be up to 3 minutes for vertical/square uploads, TikTok's Content Posting API supports direct video posting and accepts longer videos depending on account capability, while Snapchat Spotlight's official Public Profile API flow has stricter Spotlight constraints and requires more setup.

---

## 1. Video production pipeline

Each video should be generated from a structured "episode spec," ideally JSON. Do not let the AI just "make a video." Force it to output components that downstream tools can validate.

### A. Episode idea layer

For each episode, generate:

- Animal name
- Scientific name
- Habitat
- Conservation status (optional)
- 3–5 verified facts
- One "surprising" fact
- One visual gag or memorable comparison
- Difficulty rating: easy, medium, advanced
- Target age/style: children, teens, general audience

**Example animals:**
- Axolotl
- Pangolin
- Mantis shrimp
- Capybara
- Shoebill stork
- Leaf-tailed gecko
- Goblin shark
- Narwhal
- Blue-ringed octopus

### B. Script layer

Each script should include:

**1. Hook, 0–3 sec**
- "This animal looks fake… but it's real."
- "Never touch this tiny blue octopus."
- "This bird sounds like a machine gun."
- "This is the animal that can punch faster than a bullet."

**2. Presenter intro, 3–6 sec**
- Character appears in the environment.
- Short catchphrase.
- Immediate animal reveal or tease.

**3. Fact sequence, 6–30 sec**
- 2–3 fast facts.
- Each fact should map to a visual beat.
- Avoid long textbook explanations.

**4. Surprise beat, 30–38 sec**
- Unexpected comparison.
- Scale gag.
- "But here's the weird part…"

**5. Loop ending, 38–45 sec**
- End should visually or verbally connect to the first frame.
- Example: the presenter hears a sound, turns around, and says "Wait… what was THAT?" Then the next video/start hook begins with the animal.

### C. Subtitle/caption layer

Generate both:
- **Exact voiceover subtitles**
- **Punchy on-screen captions**

Use short line breaks:
- 2–5 words per caption chunk
- Highlight keywords
- Avoid covering the animal's face
- Add emphasis words: "VENOMOUS," "FASTER," "TINY," "REAL"

Example:

Voiceover:

> "This tiny octopus is one of the most dangerous animals in the ocean."

On-screen caption:

> "TINY… BUT DEADLY"

### D. Scene-by-scene storyboard

Each scene should have:

- Scene number
- Start/end time
- Voiceover text
- Visual action
- Presenter action
- Animal action
- Background/environment
- Camera movement
- SFX
- Music intensity
- Caption text
- Generation prompt
- Negative prompt
- Asset dependencies

Example scene structure:

**Scene 1 — Hook**
- Time: 0.0–3.0 sec
- Visual: Jungle leaves shake. Presenter jumps into frame.
- Camera: Fast push-in.
- Caption: "THIS ANIMAL LOOKS FAKE"
- SFX: Leaf rustle + pop
- Purpose: Stop the scroll.

### E. Visual prompts

You need separate prompt types:

**1. Character prompt**
Used in every episode.

Example:

> Original cartoon wildlife presenter, young adult, expressive face, tan explorer shirt, green neck scarf, brown boots, round field hat, friendly chaotic energy, large readable eyes, clean 3D cartoon style, consistent proportions, family-friendly, vertical video composition.

**2. Character consistency block**
This should be reused exactly.

Include:
- Character name
- Outfit
- Hair/hat
- Body proportions
- Facial features
- Color palette
- Personality
- Do-not-change rules

Example:

> The presenter must always be the same character: same face shape, same outfit, same hat, same scarf, same boots, same voice personality. Do not change age, ethnicity cues, outfit colors, facial structure, or animation style.

**3. Animal design prompt**
Generated per episode.

Example:

> Cartoon blue-ringed octopus, small body, bright blue ring patterns, expressive but biologically recognizable, cute but slightly dangerous, not scary, underwater reef setting, educational cartoon style.

**4. Background prompt**
Generated per episode.

Example:

> Shallow coral reef, clear blue water, colorful coral, soft sun rays from above, stylized 3D cartoon environment, high detail but not cluttered.

**5. Camera prompt**
Examples:
- Fast push-in
- Handheld explorer-cam feel
- Low angle animal reveal
- Orbit around animal
- Macro close-up
- Whip pan
- Crash zoom
- Slow reveal from behind leaves

**6. Negative prompt**
Use for quality control:

> No realistic human likeness, no celebrity likeness, no horror, no gore, no blurry text, no extra limbs, no deformed animal anatomy, no inconsistent outfit, no unreadable captions, no watermark, no brand logos.

### F. Audio layer

Each episode needs:

**Voiceover**
- Same voice every episode
- Energetic but not annoying
- Fast but understandable
- Strong emphasis on hook words

**Music**
- Light adventure music
- Low volume under speech
- Slight rise during reveal
- Loopable ending

**SFX**
- Leaves rustling
- Animal call
- Splash
- Footsteps
- Pop/whoosh transitions
- Comedic boing or blink
- Camera zoom whoosh

### G. Editing instructions

For every video, generate an edit decision list:

- Cut every 1–3 seconds
- Motion in every shot
- Captions appear within first 0.5 sec
- No dead air
- Voice starts immediately
- Add 1–2 pattern interrupts
- Add zooms on fact reveals
- Add freeze-frame for surprising fact
- End on a loopable question/action

### H. Looping ending

Good loop endings:
- End frame resembles first frame.
- Example: bushes shake at the end, first frame opens with bushes shaking.
- Final line tees up the hook.
- Example: "Wait… is that thing glowing?" → first line: "This glowing animal is real."
- Presenter runs toward next animal.
- New video starts as if continuing the chase.

---

## 2. Tech stack

The stack should separate asset generation, video assembly, QA, and publishing.

### Recommended default stack

| Layer | Recommended tool | Why |
|---|---|---|
| Main orchestration | Python + Temporal or n8n | Reliable automation |
| LLM/script generation | OpenAI API / Anthropic / Gemini | Structured JSON + scripts |
| Image generation | OpenAI GPT Image / Midjourney / Leonardo / Ideogram | Character/environment assets |
| Video generation | Runway API / Kling / Luma / Pika | Animated clips |
| Voice | ElevenLabs | Consistent TTS voice |
| Captions | Whisper / AssemblyAI / forced alignment | Word-level timing |
| Rendering | Remotion + FFmpeg | Template-based video assembly |
| Cloud storage | S3 / Cloudflare R2 / Google Cloud Storage | Asset storage |
| Database | PostgreSQL | Episode metadata, statuses |
| Queue | Redis / BullMQ / Celery | Job processing |
| Review UI | Simple Next.js dashboard | Approve/reject/regenerate |
| Publishing | Platform APIs + Ayrshare/Zernio fallback | Upload automation |
| Logging | Sentry + structured logs | Debug failures |
| Analytics | Platform APIs + own database | Retention learning loop |

### Script generation

Good options:
- OpenAI API
- Anthropic Claude API
- Google Gemini API
- Local LLM later if cost becomes high

Use for:
- Animal selection
- Fact summarization
- Script generation
- Storyboard generation
- Prompt generation
- Metadata generation
- Platform captions/descriptions/hashtags

Pros:
- Easy to automate
- Good JSON output
- Fast iteration

Cons:
- Can hallucinate animal facts
- Needs factual verification
- Needs strict schema validation

**Difficulty:** Easy

### Voice generation

Best option: ElevenLabs

Use it for:
- Consistent presenter voice
- Episode voiceover
- Optional animal reactions
- Multiple languages later

ElevenLabs' TTS API is designed to turn text into lifelike spoken audio with controllable intonation and emotional delivery, and their docs describe support across multiple languages and voice styles.

Pros:
- Very good voice quality
- Easy API
- Voice consistency
- Good emotional delivery

Cons:
- Can become expensive at scale
- You must avoid cloning real people without rights
- Need pronunciation dictionary for animal names

**Difficulty:** Easy

### Subtitle generation

Options:
- Whisper / faster-whisper
- AssemblyAI
- Deepgram
- ElevenLabs forced alignment (if available in your plan)
- Custom forced alignment from TTS timestamps

Whisper is an open-source speech recognition model that supports multilingual speech recognition, translation, and language identification.

Best approach:
1. Generate voiceover.
2. Run speech-to-text with timestamps.
3. Convert to word-level captions.
4. Style captions in Remotion.
5. Burn captions into the final video.

Pros:
- Captions greatly improve retention
- Can automate completely
- Word-level highlighting is possible

Cons:
- Timestamp drift can occur
- Animal names may be misrecognized
- Needs manual style tuning

**Difficulty:** Medium

### Character design and consistency

Options:
- OpenAI GPT Image for character sheets and scene stills
- Midjourney for initial concept art
- Leonardo / Scenario / Krea for character style workflows
- Custom LoRA later
- 3D character rig later

OpenAI's image generation API can generate images from text and edit existing images using prompts; it supports configurable quality, size, format, and related image-generation controls.

Best early approach:
- Generate 8–12 reference poses
- Use those as reference assets
- Keep the same outfit and visual rules
- Use image-to-video from reference frames

Best scalable approach:
- Build or commission a simple 3D rig
- Use AI-generated backgrounds and animals
- Composite the same rigged character into all episodes

Pros:
- Strong brand identity
- Viewers recognize the character
- Reusable assets reduce generation cost

Cons:
- AI image/video tools often drift
- Hands, face, outfit, and proportions may change
- Character consistency is the hardest visual problem

**Difficulty:** Hard

### Image generation

Use for:
- Background plates
- Animal stills
- Character poses
- Props
- Thumbnail frames
- End cards

Options:
- OpenAI GPT Image
- Midjourney
- Ideogram
- Leonardo
- Stable Diffusion / Flux with LoRA

Best approach:
- Generate stills first.
- Approve stills.
- Animate the best stills.
- Do not rely only on text-to-video for character consistency.

**Difficulty:** Medium

### Animation/video generation

Options:
- Runway API
- Kling
- Luma Dream Machine
- Pika
- PixVerse
- HeyGen/D-ID (only if using talking avatars — probably not ideal for this concept)

Runway's API is built for integrating generative models into apps and products, and its docs describe API-based video/image generation and video editing workflows.

Use for:
- 3–5 sec animated scene clips
- Animal movement
- Background motion
- Presenter reaction shots
- Camera moves

Pros:
- Fast visual production
- Good for short clips
- Great for stylized worlds

Cons:
- Expensive at scale
- Clip-to-clip consistency is unstable
- Exact timing can be hard
- Regeneration may be necessary

**Difficulty:** Medium/Hard

### Scene composition and rendering

Best options:
- Remotion
- FFmpeg
- Shotstack
- MoviePy (for simple MVPs only)

Remotion is a good fit because it lets you design reusable video templates and expose props for text, images, timing, and layouts, then render videos programmatically.

FFmpeg is the low-level workhorse for converting, filtering, transcoding, and combining media assets.

Shotstack is a cloud video editing API that uses JSON schemas to compose tracks, clips, overlays, transitions, and text before rendering.

Recommended:
- MVP: Remotion + FFmpeg
- No-code/low-code MVP: Shotstack
- Scale: Remotion render workers on cloud instances

**Difficulty:**
- Remotion: Medium
- FFmpeg: Medium/Hard
- Shotstack: Easy/Medium

### Music and sound effects

Options:
- ElevenLabs sound effects/music features
- Stable Audio
- Epidemic Sound / Artlist / Soundstripe with license
- YouTube Audio Library for YouTube-specific usage
- Freesound (only with careful license filtering)

Best approach:
- Create a small licensed audio library.
- Reuse 10–20 music beds.
- Generate or source short SFX.
- Keep music very low under narration.

Avoid:
- Popular songs
- Platform-native trending audio in fully automated workflows unless the API supports it and rights are clear
- Content ID risk for YouTube

YouTube specifically warns that Shorts over one minute with an active Content ID claim can be blocked globally, so avoid copyrighted music in your longer Shorts workflow.

### Quality control

Automate checks for:

**Technical:**
- Duration
- Resolution
- Aspect ratio
- Audio loudness
- Captions inside safe zone
- File size
- Codec
- No black frames
- No missing audio
- No frozen clips

**Content:**
- Animal fact verification
- No harmful misinformation
- No copyrighted character/person likeness
- No unreadable captions
- No scary/gory visuals if targeting young audiences
- No platform policy issues

**Brand:**
- Character consistency score
- Voice consistency
- Catchphrase usage
- Color/style consistency
- Episode pacing

### Automated publishing

#### YouTube Shorts

Use:
- YouTube Data API
- OAuth
- Metadata: title, description, tags, privacy status
- Upload vertical/square video

Google's YouTube upload guide describes uploading videos with the YouTube Data API using OAuth, setting metadata such as title/description/keywords/category/privacy, and retrying uploads with exponential backoff.

**Automation difficulty:** Easy

#### TikTok

Use:
- TikTok Content Posting API
- Creator info query
- Initialize upload/post
- Transfer video to TikTok servers

TikTok's Direct Post docs describe querying creator information, initializing a post request, and exporting the video to TikTok servers; its media guide lists video restrictions including supported formats, codecs, frame rate, resolution, duration, and size limits.

**Automation difficulty:** Medium — mainly because of app review, OAuth, scopes, and creator account constraints.

#### Instagram Reels

Use:
- Instagram Graph API Content Publishing
- Business/Creator account
- Media container creation
- Status polling
- Publish call

Meta's Instagram content publishing docs describe publishing images, videos, Reels, and carousels through the Instagram Platform.

**Automation difficulty:** Medium/Hard — mostly because of Meta app setup, permissions, and account requirements.

#### Snapchat Spotlight

Use:
- Snap Public Profile API
- Public Profile
- Business account
- OAuth app
- Allowlisting
- Media encryption/chunk upload
- Spotlight post endpoint

Snap's docs describe the Public Profile API as supporting Creator Discovery and Content Management, including posting content on behalf of brands/creators; the Public Profile API is currently allowlist-only, and the Spotlight upload flow requires media creation/upload before using the Spotlight posting API.

**Automation difficulty:** Hard

Practical shortcut:
- Use a third-party social posting API such as Ayrshare, Zernio, or similar for Snapchat, especially early.
- Long term, use direct APIs where possible to reduce vendor lock-in.

### Workflow orchestration

#### MVP

Use:
- Python scripts
- SQLite/Postgres
- Cron
- Local folders

#### Semi-automated

Use:
- n8n for visual workflow automation
- Python workers for media generation
- PostgreSQL
- S3/R2 storage

n8n's docs describe it as a workflow automation tool with AI/business process automation features, and self-hosted n8n can run as Community Edition without a license key, though n8n recommends self-hosting mainly for technically experienced users because of security and downtime risks.

#### Production

Use:
- Temporal or Airflow
- Queue workers
- Retry policies
- Cloud rendering
- Central observability

Temporal is designed for durable workflows that can resume after crashes, network failures, or outages, which is very useful for long-running media-generation pipelines with expensive external API calls.

Airflow is strong for batch-oriented workflows that need scheduling, monitoring, logs, retries, and Python-defined DAGs.

---

## 3. System architecture

### High-level architecture

**Input data:**
- Animal/topic queue
- Character bible
- Visual style bible
- Prompt templates
- Audio style settings
- Platform account settings
- Publishing schedule

**Generation steps:**
1. Select animal.
2. Fetch/verify facts.
3. Generate episode script.
4. Generate storyboard.
5. Generate visual prompts.
6. Generate voiceover.
7. Generate or retrieve character/animal/background assets.
8. Animate scenes.
9. Generate captions.
10. Render final video.
11. Run QA checks.
12. Send to review dashboard.
13. Publish/schedule.
14. Collect analytics.
15. Feed analytics into future scripts.

### Suggested file structure

```
/episodes
  /ep-001-axolotl
    episode.json
    script.md
    storyboard.json
    /assets
      /character
      /animal
      /backgrounds
      /sfx
    /clips
    /render
    final.mp4
    qa_report.json
    publish_log.json
```

### Database tables

Minimum viable database:
- `episodes` — id, animal, status, created_at, published_at
- `scenes` — id, episode_id, scene_number, prompt, asset_path, status
- `assets` — id, episode_id, type, path, generation_model, cost
- `publishes` — id, episode_id, platform, post_id, status, timestamp
- `analytics` — id, episode_id, platform, views, completion_rate, replays

### Automation logic

Use a state machine:

```
QUEUED → SCRIPTING → STORYBOARDING → GENERATING_ASSETS
→ ANIMATING → CAPTIONING → RENDERING → QA → REVIEW
→ APPROVED → PUBLISHING → PUBLISHED → ANALYTICS
```

Every step should be idempotent. If scene 3 fails, rerun scene 3 only, not the whole episode.

### Human approval points

Early stage:
- Approve script
- Approve character/animal look
- Approve final video
- Approve platform captions

Later:
- Auto-approve if QA score > threshold
- Manual review only for low-confidence episodes

I would not start with full auto-publishing. First build a review dashboard with:
- Video preview
- Script preview
- Captions
- Fact sources
- Regenerate buttons
- Publish buttons
- QA report

### Error handling

Handle:
- API rate limits
- Failed generations
- Policy refusals
- Low-quality assets
- Bad captions
- Render failures
- Upload failures
- Expired OAuth tokens
- Platform-specific rejection
- Duplicate topic selection

Use:
- Exponential backoff
- Retry limits
- Dead-letter queue
- Partial regeneration
- Alerting on repeated failure
- Cost limit per episode

### Logging

Log every major step:
- Step name
- Episode ID
- Timestamp
- Duration
- Cost
- Model/tool used
- Success/failure
- Error message if failed
- Output path

### Scheduling

Recommended schedule:
- Generate 10 episodes in batch.
- Review once per week.
- Publish 1–3 per day per account.
- Stagger platform uploads by 15–60 minutes.
- Track which post time performs best per platform.

---

## 4. Retention optimization

### Strong opening hooks

The first second must show:
- Movement
- Large caption
- Animal tease
- Presenter reaction
- Sound hit

Bad:

> "Today we are going to learn about the axolotl."

Good:

> "This animal can regrow its body parts."

Better:

> "This little guy can regrow his BRAIN."

### Fast pacing

Use:
- 1–3 sec shots
- No long intros
- No logo intro
- No "welcome back"
- No pause before speaking
- Immediate captions

### Pattern interrupts

Every 5–8 seconds:
- Crash zoom
- Freeze-frame
- Animal reaction
- Map pop-up
- Comedic sound
- Presenter nearly gets surprised
- Quick comparison graphic

### Captions/subtitles

Best style:
- Large
- High contrast
- Center-lower safe zone
- 2–5 words at a time
- Highlight key terms
- Animate captions slightly

Example:

> "IT PUNCHES"
> "FASTER THAN"
> "A BULLET"

### Visual movement

Even static scenes need motion:
- Slow zoom
- Parallax background
- Floating particles
- Character idle motion
- Camera shake
- Moving caption emphasis
- Animal blink/twitch/swim

### Curiosity gaps

Use open loops:
- "But the weirdest part?"
- "That's not even its strongest ability."
- "And this is why you should never touch it."
- "Watch what happens when it gets scared."

### Sound design

Use:
- SFX for every reveal
- Light ambience
- Music riser before surprise
- Bass hit on scary/surprising facts
- Gentle animal sound
- Whoosh on transitions

Keep voice dominant. Music should support, not compete.

### Looping endings

Examples:
- Presenter says: "Wait… did it just move?" → video restarts with movement.
- Animal disappears at the end → first frame shows animal being found.
- Presenter runs offscreen → first frame has him running into frame.

### Short episode structure

Best default:
- Hook: 0–3 sec
- Presenter intro: 3–6 sec
- Facts: 6–30 sec
- Surprise: 30–38 sec
- Loop ending: 38–45 sec

### Callbacks

Recurring elements:
- Catchphrase
- Presenter nearly misidentifies animal
- Tiny field notebook
- "Danger meter"
- "Weirdness meter"
- Animal "rating"
- Running joke with one recurring sidekick

### Platform-specific tactics

**YouTube Shorts:**
- Strong loop matters.
- Title can be curiosity-based.
- Avoid copyrighted music if over one minute because Content ID issues can block longer Shorts.

**TikTok:**
- First-second visual clarity matters.
- Use native-feeling captions.
- Trend formats can help, but avoid depending on copyrighted/trending audio in automation.

**Instagram Reels:**
- Clean visuals matter.
- Captions should look polished.
- Use save-worthy facts: "3 animals you didn't know were real."

**Snapchat Spotlight:**
- Keep it fast and visual.
- Make it understandable without reading the description.
- Stay inside 6–60 seconds for official Spotlight API constraints.

---

## 5. Consistency and quality

### Character consistency system

Create a character bible document that covers:
- Character name
- Physical description
- Outfit details and color palette
- Facial structure rules
- Voice personality
- Catchphrases
- Do-not-change rules
- Reference image sheet

Attach this bible to every generation prompt.

### Voice consistency

Use:
- Same TTS voice ID
- Same speaking speed
- Same pitch/emotion settings
- Same pronunciation dictionary
- Same intro/outro cadence

Create a voice direction prompt:

> Energetic cartoon wildlife presenter. Excited, warm, fast-paced, clear pronunciation, child-friendly, expressive, slightly comedic, never sarcastic, never scary.

### Visual consistency

Use a style bible:
- Color palette (hex values)
- Lighting rules
- Shadow style
- Line weight
- Background complexity level
- Caption font and size
- Transition style
- Cartoon rendering style

Include this in every image/video generation prompt.

### Asset reuse

Reuse:
- Presenter character sheet
- 10 facial expressions
- 10 body poses
- Logo/title card
- Caption template
- SFX pack
- Music beds
- Transition effects
- Environment templates

### Quality scoring

Give every episode a score:
- Fact accuracy: 0–100
- Character consistency: 0–100
- Caption quality: 0–100
- Pacing score: 0–100
- Audio quality: 0–100
- Technical QA: pass/fail

Only auto-publish if:
- Overall score > 85
- No policy/compliance flags
- Fact confidence > 90
- Character consistency > 80
- Captions pass safe-zone check

### AI-content disclosure

Because this is AI-generated, build disclosure into the publishing metadata where required. YouTube requires disclosure for AI-generated or meaningfully altered content that appears realistic, and TikTok requires labeling realistic AI-generated images, audio, and video. Meta also uses "AI info" labels when users disclose AI-generated content or when Meta detects industry AI indicators.

Since your series is clearly cartoon-style, disclosure requirements may be lighter than for photorealistic/deepfake content, but I would still keep an internal flag and comply with each platform's upload settings.

---

## 6. Practical roadmap

### Phase 1 — MVP

Goal: produce 5–10 good videos manually assisted by automation.

Build:
- Character bible
- Style bible
- Script/storyboard JSON generator
- Manual image/video generation
- ElevenLabs voiceover
- Captions
- Remotion template
- Manual publishing

Avoid overcomplicating:
- Full auto-publishing
- Multi-account scaling
- Custom character model
- Complex analytics loop
- Fully autonomous topic generation

Biggest risks:
- Character drift
- Bad animal facts
- Low-quality animation
- Videos feeling like AI slop
- Too much time spent on tooling before proving the format

Success metric:
- Can you make 10 videos with the same character and acceptable quality?

### Phase 2 — Improved semi-automated version

Goal: one-click generation with human approval.

Build:
- Python backend
- PostgreSQL episode database
- Asset storage
- Script generator
- Voice generator
- Caption generator
- Remotion renderer
- QA report
- Review dashboard

Human approves:
- Script
- Final render
- Publish

Avoid:
- Fully autonomous publishing
- Too many visual styles
- Too many episode formats

Biggest risks:
- Video generation cost
- Regeneration loops
- Render pipeline bugs
- Captions not matching speech

Success metric:
- Produce 3–5 videos per day with review.

### Phase 3 — Fully automated version

Goal: daily auto-generation and scheduled publishing.

Build:
- Automated animal queue
- Fact verification workflow
- Prompt generation
- Scene generation
- Auto-QA
- Auto-render
- Auto-schedule
- Platform-specific captions/hashtags
- Analytics ingestion

Use:
- Temporal/Airflow for orchestration
- Cloud render workers
- Retry logic
- Alerting
- Cost limits

Avoid:
- Removing all human review too early
- Auto-posting low-confidence episodes
- Relying on one video generation provider

Biggest risks:
- Platform API failures
- Content quality degradation
- Repetitive scripts
- Account trust issues from posting too much
- Policy mistakes

Success metric:
- 80%+ of generated videos pass QA without manual edits.

### Phase 4 — Scalable multi-account version

Goal: multiple channels, languages, niches, and formats.

Build:
- Multi-account dashboard
- Brand presets
- Character variants
- Language localization
- Per-platform analytics
- A/B testing
- Auto topic rotation
- Content calendar
- Publishing throttles
- Cost-per-video tracking

Avoid:
- Spamming duplicate videos across accounts
- Posting identical captions everywhere
- Scaling before retention data proves the concept

Biggest risks:
- Platform spam detection
- Repetitive content
- Weak brand differentiation
- Rights/licensing issues
- Operational complexity

Success metric:
- Stable production of 50–200 videos/month with measurable retention and low failure rate.

---

## 7. Recommended production workflow

Use this order for every episode:

1. Select animal from queue
2. Verify facts (LLM + source check)
3. Generate episode JSON spec
4. Generate script
5. Human approves script (early phase)
6. Generate voiceover
7. Generate captions from voiceover
8. Generate character/animal/background prompts
9. Generate still images
10. Human approves key stills (early phase)
11. Animate stills into clips
12. Render final video with Remotion + FFmpeg
13. Run QA checks
14. Human approves final video (early phase)
15. Generate platform-specific titles/captions/hashtags
16. Schedule and publish
17. Save post IDs and collect analytics

The key is to make each episode data-driven. The final video should be a render of structured metadata, not a chaotic pile of generated assets.

---

## 8. Ranked tech stack

### Best practical stack to start

1. **Python** — Main backend and automation glue. Best for APIs, file processing, queues, QA, and data handling.

2. **OpenAI API / Claude API** — Script, storyboard, prompt, metadata, and QA generation.

3. **ElevenLabs** — Presenter voice consistency.

4. **OpenAI GPT Image / Midjourney** — Character sheets, backgrounds, animals, thumbnails.

5. **Runway API / Kling** — Short animated clips.

6. **Remotion** — Programmatic video templates and rendering.

7. **FFmpeg** — Transcoding, normalization, final platform exports.

8. **PostgreSQL** — Episode state, metadata, assets, analytics.

9. **S3 / Cloudflare R2** — Store generated assets and rendered videos.

10. **n8n** — Good for MVP/semi-automated workflow orchestration.

11. **Temporal** — Best for robust production orchestration.

12. **Platform APIs** — YouTube Data API, TikTok Content Posting API, Instagram Graph API, Snap Public Profile API.

13. **Ayrshare** — Useful shortcut for multi-platform posting, especially Snapchat.

---

## 9. Checklist for each video

### Concept checklist

- [ ] Animal selected
- [ ] Animal not recently used
- [ ] 3–5 facts verified
- [ ] One surprising fact chosen
- [ ] Clear audience level
- [ ] No unsafe/misleading claim

### Script checklist

- [ ] Hook starts immediately
- [ ] First caption appears within 0.5 sec
- [ ] Voiceover under 45 sec
- [ ] 2–3 facts maximum
- [ ] One pattern interrupt
- [ ] Strong final loop
- [ ] No copyrighted/personality imitation

### Visual checklist

- [ ] Presenter matches character bible
- [ ] Same outfit
- [ ] Same cartoon style
- [ ] Animal recognizable
- [ ] Background matches habitat
- [ ] Motion in every scene
- [ ] No visual artifacts
- [ ] No unreadable text

### Audio checklist

- [ ] Same voice ID
- [ ] Clear pronunciation
- [ ] Music below voice
- [ ] SFX timed to reveals
- [ ] No copyrighted music risk
- [ ] Loudness normalized

### Caption checklist

- [ ] Correct words
- [ ] Word timing aligned
- [ ] Large readable font
- [ ] Safe-zone compliant
- [ ] Keywords emphasized
- [ ] No caption covers animal face

### Render checklist

- [ ] 1080×1920
- [ ] 9:16
- [ ] MP4
- [ ] H.264
- [ ] AAC audio
- [ ] 30 fps
- [ ] Duration correct
- [ ] File size acceptable
- [ ] No black frames
- [ ] No missing audio

### Publishing checklist

- [ ] Platform-specific title
- [ ] Platform-specific caption
- [ ] Hashtags
- [ ] AI disclosure if required
- [ ] Scheduled time
- [ ] Upload success confirmed
- [ ] Platform post ID saved
- [ ] Analytics collection scheduled

---

## 10. Example JSON/template structure

```json
{
  "episode_id": "ep-007",
  "animal": {
    "name": "Blue-ringed octopus",
    "scientific_name": "Hapalochlaena lunulata",
    "habitat": "Shallow coral reefs, Indo-Pacific",
    "conservation_status": "Least Concern",
    "facts": [
      "Small enough to fit in a human hand.",
      "Contains enough venom to kill 26 adult humans.",
      "Has no antivenom.",
      "Rings turn bright blue when threatened.",
      "Can change color to camouflage in under a second."
    ],
    "surprise_fact": "No antivenom exists for its bite.",
    "visual_gag": "Presenter holds out hand, then quickly pulls it back.",
    "difficulty": "easy",
    "audience": "general"
  },
  "script": {
    "hook": "This tiny octopus can kill 26 people. And there's no antidote.",
    "presenter_intro": "I'm Finn. And I found one.",
    "facts": [
      "It's smaller than your hand.",
      "Its venom shuts down your nervous system in minutes.",
      "Those glowing blue rings? That's its warning."
    ],
    "surprise_beat": "But here's the terrifying part — it only bites if you pick it up. So just... don't.",
    "loop_ending": "Wait. Did that one just turn blue?",
    "voiceover_file": "ep-007-vo.mp3",
    "duration_sec": 42
  },
  "scenes": [
    {
      "scene_number": 1,
      "start_sec": 0.0,
      "end_sec": 3.0,
      "voiceover": "This tiny octopus can kill 26 people.",
      "caption": "TINY. DEADLY. NO CURE.",
      "visual": "Close-up: blue rings flash on small octopus. Presenter's hand visible.",
      "camera": "Fast push-in macro",
      "sfx": ["ocean_ambient", "ring_flash_whoosh"],
      "music_intensity": "low",
      "generation_prompt": "Cartoon blue-ringed octopus close-up, bright glowing blue rings, clear shallow water, dramatic lighting, stylized 3D cartoon, vertical composition",
      "negative_prompt": "realistic, scary, gore, blurry, watermark"
    }
  ],
  "character": {
    "name": "Finn",
    "voice_id": "elevenlabs_voice_id_here",
    "outfit": "tan explorer shirt, green neck scarf, round field hat, brown boots",
    "consistency_block": "Same face shape, same outfit, same hat, same scarf, same boots every episode. Do not change age, outfit colors, facial structure, or animation style.",
    "catchphrase": "I found one."
  },
  "assets": {
    "character_sheet": "assets/finn/character_sheet_v3.png",
    "animal_reference": "assets/ep-007/octopus_ref.png",
    "background": "assets/ep-007/coral_reef_bg.png",
    "music_bed": "assets/audio/adventure_loop_02.mp3"
  },
  "qa": {
    "fact_confidence": 97,
    "character_consistency_score": 91,
    "caption_safe_zone": true,
    "duration_valid": true,
    "resolution_valid": true,
    "overall_score": 93,
    "auto_approve": true
  },
  "publishing": {
    "youtube": {
      "title": "This octopus has NO antivenom #shorts",
      "description": "Meet the blue-ringed octopus — one of the deadliest animals on Earth. #wildlife #animals #shorts",
      "tags": ["shorts", "wildlife", "octopus", "animals", "facts"],
      "scheduled_at": "2024-02-15T14:00:00Z"
    },
    "tiktok": {
      "caption": "No antivenom. No mercy. 🐙 #animals #wildlifefacts #tiktok",
      "scheduled_at": "2024-02-15T14:30:00Z"
    },
    "instagram": {
      "caption": "The smallest octopus. The biggest problem. 🐙\n\n#reels #wildlife #octopus #animalsoftiktok",
      "scheduled_at": "2024-02-15T15:00:00Z"
    },
    "snapchat": {
      "caption": "This tiny octopus has NO antidote 😳",
      "scheduled_at": "2024-02-15T15:30:00Z"
    }
  }
}
```

---

## 11. Most important automation challenges to solve first

### 1. Character consistency

This is the hardest problem. Solve it before scaling. A recurring character only works if viewers recognize them instantly.

Best solution path:
1. Character bible
2. Character sheet
3. Reusable poses
4. Image references
5. Eventually custom LoRA or 3D rig

### 2. Repeatable video template

Do not make every episode structurally unique. Use 2–3 repeatable formats:
- "Dangerous but tiny"
- "Looks fake but real"
- "Animal superpower"
- "Weirdest defense mechanism"
- "Cute animal, shocking fact"

### 3. Fact verification

Animal content must be accurate. Build a fact-checking step before script generation is approved.

### 4. Caption quality

Bad captions make the video feel low quality instantly. Invest early in caption timing, safe zones, and styling.

### 5. Cost control

AI video generation can get expensive. Track:
- Cost per episode
- Cost per approved episode
- Cost per published episode
- Cost per 1,000 views
- Regeneration rate

### 6. Publishing reliability

Publishing APIs fail for boring reasons: expired OAuth tokens, app review issues, file constraints, rate limits, or metadata validation. Build retries, platform-specific validation, and manual fallback.

### 7. Avoiding "AI slop"

The content needs a recognizable format, recurring character, good pacing, accurate facts, and strong editing. Automation should make the system repeatable, not generic.

---

## Sources

- YouTube Shorts length and Content ID notes: https://support.google.com/youtube/answer/15424877?hl=en
- YouTube Data API video upload guide: https://developers.google.com/youtube/v3/guides/uploading_a_video
- TikTok Content Posting API Direct Post: https://developers.tiktok.com/doc/content-posting-api-reference-direct-post
- Instagram Platform Content Publishing: https://developers.facebook.com/docs/instagram-platform/content-publishing/
- Snap Public Profile API Introduction: https://developers.snap.com/api/marketing-api/Public-Profile-API/Introduction
- Snap Public Profile API Profile Asset Management: https://developers.snap.com/marketing-api/Public-Profile-API/ProfileAssetManagement
- ElevenLabs Text to Speech docs: https://elevenlabs.io/docs/overview/capabilities/text-to-speech
- OpenAI Whisper repository: https://github.com/openai/whisper
- OpenAI Image Generation API guide: https://developers.openai.com/api/docs/guides/image-generation
- Runway API docs: https://docs.dev.runwayml.com/
- Remotion docs: https://www.remotion.dev/
- FFmpeg docs: https://ffmpeg.org/ffmpeg.html
- Shotstack API docs: https://shotstack.io/docs/api/
- n8n docs: https://docs.n8n.io/
- Temporal docs: https://docs.temporal.io/
- Airflow docs: https://airflow.apache.org/docs/apache-airflow/stable/index.html
- YouTube AI disclosure info: https://support.google.com/youtube/answer/14328491?hl=en
