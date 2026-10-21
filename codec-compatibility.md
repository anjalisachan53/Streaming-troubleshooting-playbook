# Troubleshooting: Codec and Playback Compatibility

## Symptoms that can indicate a codec/decoder issue

- Black screen while audio plays
- Playback works on one device but not another
- Artifacts, green/grey blocks, or repeated/frozen frames
- Playback fails after a stream configuration change
- Audio is missing or unsupported

A symptom alone does not prove a codec issue. Network, source, DRM, player integration, and device support can produce similar symptoms.

## Investigation workflow

### 1. Collect the playback context
Record the ingest protocol if known, media container, video/audio codec, profile/level, bit depth, chroma format, frame rate, player version, browser, OS, and device model. Do not include credentials or private stream URLs in a public report.

### 2. Inspect the media
For a file you are authorized to analyze, `ffprobe` can display stream metadata:

```bash
ffprobe -hide_banner -show_streams -show_format sample.mp4
```

Review the output for codec names, profile, pixel format, frame rate, sample rate, and channel layout. Redact filenames or metadata that identify a customer.

### 3. Compare supported combinations
Check current official documentation for the exact protocol, product version, browser, OS, and device. Do not assume that support for a codec in one protocol means it is supported in every protocol or browser.

### 4. Test a known-good baseline
Where appropriate, use a short test stream with a commonly supported configuration, such as H.264 video, 8-bit 4:2:0 pixel format, and AAC audio for a compatible file/container workflow. This is a diagnostic baseline, not a universal requirement.

Change one setting at a time and compare results. Keep a record of the original settings and the test outcome.

### 5. Compare devices and players
- If a known-good stream works but the original does not, compare the media metadata and source settings.
- If the same stream works in one player but not another, inspect player/browser compatibility and integration.
- If the issue affects every player, inspect the source and processing path before concluding the player is responsible.

## Safe conclusion template

**Evidence:** [metadata, error, device comparison]  
**Likely stage:** [source/encoder, processing, delivery, player/device]  
**Confidence:** [confirmed / likely / inconclusive]  
**Next action:** [specific test or escalation]
