---
name: no-slop-video
description: >
  Edit, direct, and review short-form and long-form videos with AI so they tell
  a compelling story, preserve speaker authenticity, and avoid AI slop. Use
  whenever cutting raw video footage, building shorts or social clips, creating
  video thumbnails, adding captions/subtitles, grading color, selecting B-roll
  or screen captures, or running multi-agent video editing and review workflows.
  Enforces an 8-second hook, hard clean endings, real footage over invented
  visuals, color-locked emphasis zooms, PII exclusion, glance-test thumbnails,
  specialist production subagents, and blind digital-twin + Matthew Luhn
  reviews.
license: MIT
metadata:
  author: Ricky Robinett
  version: "1.0.0"
  source: https://ricky.robinett.ai/noslopvideo
---

# Please, no more AI slop video

## Narrative

### The best story wins

The most important thing when building a video for me is the story. When building a short video, please build it using a compelling narrative arc. If you are unsure of the story of the video, please come back and ask me questions to help shape it before building.

### Who is the story for?

A story requires someone to hear it. It should be clear when editing a video who the video is for. What do they care about? Do we need answers or decisions from them? Do we need to communicate an idea or ideas to them? If you aren’t clear on the audience and what we need to communicate, please ask clarifying questions before building the video.

### A beginning, middle, and end

A good story has a beginning, middle, and end. While not always true, for a short video the beginning is a hook that should capture someone in the first 8 seconds, the middle answers that hook, and the end should close hard and clean on the speaker’s final line with no graphics, URLs, or text CTAs—because truthfully most people stop watching when they determine the video is going to end. Land the core premise of the video in the first 8 seconds—don’t put background context, welcome or introductions, caveats, or side tangents before the audience knows where the story is going.

### Authenticity and personality

The video should capture what makes the speaker(s) uniquely them. If they’re funny, capture the humor. If they’re academic, pull together the most academic moments. People want to watch a human, not a robot, and we should lean into that. Show the best of the speaker(s): in a thumbnail make sure they’re smiling, excited, or expressive, with their eyes open and looking at the camera. No awkward poses in thumbnails.

### Accuracy

When showing screens, clips, etc., make sure to use the actual, literal websites or footage referenced in the video and match the exact action, feature, or transformation being described—not generic overview footage of the same site. Don’t invent (or make AI image) versions of the things referenced. When compressing technical terms into thumbnails or clips, make sure to maintain the accuracy of the statement. Don’t let brevity conceal the true statements or accidentally have compression reverse cause and effect.

## Design and Aesthetics

### Captions

For shorts, it’s a best practice to have captioning embedded directly in the video. Do this in a clear, simple, and straightforward way that allows the viewer to follow along even if they don’t have audio on. For long-form, ship the proper files for subtitles that we’ll need to upload to all the platforms.

### Variety

All visuals should reinforce the narrative and story, so don’t do any visuals for the sake of doing them. Try to add some visual variety throughout a video. Zoom in during an important moment. Do a color overlay if someone expresses a specific emotion in all of words, facial expression, vocal tone, and energy. This is a great way to layer in the speaker’s personality and authenticity we talk about above. Avoid AI slop graphics or overlays, or—beyond captions—overlays that just say what the speaker is already saying in the video. Keep emphasis zooms 100% color-locked to the base grade (no tint or exposure shifts during a zoom)—only shift color on deliberate, unmistakable emotion that matches the words and tone. Find and highlight the visual moments, with pacing and zooms.

### PII, or private information

When stitching together content, make sure to not show any PII or private information (e.g. API keys). While you can blur things out, our first choice should be to not show footage including PII or private information at all.

### Thumbnails

Please avoid any AI slop elements in the thumbnail (the little pill-type graphics everywhere, too much text on the thumbnail). Opt towards a full-bleed image pulled from the video itself (unless a thumbnail photo is provided), and if the image includes a person, triple-check that you’ve captured them in a flattering moment. Make sure it passes the glance test and is readable in under a second at tiny feed size. Strip out background clutter, extra props, and stray arrows. Max 3 focus areas with clear hierarchy—text, visual, and face + expression (single face usually wins). And click to answer: leave an open question they have to click to resolve. If making multiple edits or shorts, make a thumbnail catered to each edit option if the global thumbnail options would not apply. Ensure any thumbnail still is in focus, clear, and framed appropriately.

## Subagent team

### Production

The production subagent team working on this video should consist of (at minimum):

- Audio engineer
- Color grader
- Script experts focused on narrative, pace, and authenticity
- Thumbnail expert
- B-roll and screen capture expert
- Technical QA & Captions/Accuracy Checker
- If multiple camera angles are included, involve an expert on multicamera scene selection
- And anything else you deem necessary for solid output

### Reviews

Before sending to me, create digital twin subagents to review the content based on the audience(s) the video is for. Remember to account for varying skill levels across the audience when spinning up digital twins so we don’t accidentally overorient our content towards a specific skill level (unless we’re intentionally trying to do so). Also, have it reviewed by a digital twin of Matthew Luhn for the Pixar Story Spine. Don’t ask me to review until those audiences give the video a thumbs up. Keep reviewers blind to the editors’ changelog so that they don’t accidentally overfit towards the changelog.

When content is ready for me to review, open the folder that it’s in so I don’t have to hunt around for it on my machine.
