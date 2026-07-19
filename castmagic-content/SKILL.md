---
name: castmagic-content
description: "Transform audio and video content using Castmagic — generate show notes, social posts, blog drafts, and repurposed content from raw media files."
tags: [castmagic, content-marketing, podcasting, audio-to-text, repurposing, show-notes]
category: creative
created: 2026-07-19
---

# Castmagic Content Pipeline

Transform audio/video content into a full content ecosystem using Castmagic. This skill covers uploading media, generating show notes, extracting social content, and repurposing into blog posts and newsletters.

## Trigger Conditions

Use this skill when the user asks to:
- Generate show notes from a podcast or video recording
- Create social media posts from audio content
- Repurpose a transcript into blog posts or newsletters
- Set up a content pipeline for regular episodes
- Extract quotes or key moments from audio

## API Access

Castmagic provides a REST API. Store your API key in Bitwarden:

```bash
# Retrieve Castmagic API key
bw get notes "Castmagic API Key"
```

Base URL: `https://api.castmagic.io/v1`

## Common Operations

### Upload Media for Processing

```bash
curl -X POST "https://api.castmagic.io/v1/media/upload" \
  -H "Authorization: Bearer *** \
  -F "file=@/path/to/episode.mp3" \
  -F "title=Episode Title" \
  -F "language=en"
```

### Generate Show Notes

```bash
curl -X POST "https://api.castmagic.io/v1/media/{media_id}/generate" \
  -H "Authorization: Bearer *** \
  -H "Content-Type: application/json" \
  -d '{
    "output_types": ["show_notes", "timestamps", "key_takeaways"],
    "tone": "professional"
  }'
```

### Extract Social Content

```bash
curl -X POST "https://api.castmagic.io/v1/media/{media_id}/social" \
  -H "Authorization: Bearer *** \
  -H "Content-Type: application/json" \
  -d '{
    "platforms": ["twitter", "linkedin", "instagram"],
    "quote_count": 3,
    "thread_length": 5
  }'
```

### Repurpose to Blog Post

```bash
curl -X POST "https://api.castmagic.io/v1/media/{media_id}/repurpose" \
  -H "Authorization: Bearer *** \
  -H "Content-Type: application/json" \
  -d '{
    "format": "blog_post",
    "word_count": 1000,
    "include_seo": true
  }'
```

## Workflow Pattern

### Full Content Pipeline (1 episode → multiple assets)

1. **Upload** — Upload raw audio/video file
2. **Transcribe** — Wait for transcription to complete
3. **Generate** — Request show notes, timestamps, key takeaways
4. **Social Extract** — Extract quotes and social threads from transcript
5. **Repurpose** — Generate blog draft and newsletter version
6. **Review & Publish** — Review all outputs, edit as needed, publish

## Environment Setup

```bash
export CASTMAGIC_API_KEY="your...ort CASTMAGIC_WEBHOOK_URL="https://your-server.com/webhooks/castmagic"
```

## Pitfalls

- **Audio quality matters.** Poor recordings produce poor transcripts. Pre-process with Descript if needed.
- **Speaker identification.** Castmagic can identify speakers, but you may need to name them in settings first.
- **Processing time.** Longer episodes (>60 min) take several minutes. Use webhooks for async notification.
- **Brand voice.** Set up brand voice profiles in Castmagic before generating content for consistent tone.
- **File formats.** Supported: MP3, WAV, MP4, MOV, M4A. Avoid unusual codecs.

## Verification

```bash
# Check media processing status
curl -s "https://api.castmagic.io/v1/media/{media_id}" \
  -H "Authorization: Bearer *** | jq '.status'
# Should return "completed", "processing", or "failed"
```