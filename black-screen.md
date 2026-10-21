# Troubleshooting: Black Screen or Frozen Video

## Symptoms to distinguish

- **Black screen with no audio:** playback may not have started, the session may be unavailable, or the player may be blocked.
- **Black screen with audio:** video track, codec/profile, or decoder may be involved.
- **Video starts late:** the player may be waiting for a keyframe or initial media data.
- **Video freezes after starting:** source interruption, reconnect, buffering, or decoder issues may be involved.
- **Only one device/browser fails:** compare browser, OS, device capabilities, and player integration.

These are hypotheses, not conclusions. Confirm with evidence before assigning a root cause.

## Investigation workflow

### 1. Define the scope
Record the approximate start time and timezone, duration, affected viewers, player/browser version, OS/device, ingest protocol if known, and whether audio continues.

### 2. Reproduce in a controlled way
- Test the same stream on a second supported browser or device.
- If available, compare the customer application with a known-good reference player.
- Use a test stream only when authorized and safe.
- Record the exact steps and whether a refresh changes the symptom.

### 3. Check the source
- Confirm the source preview or local recording contains moving video.
- Verify that the encoder is publishing a video track and that bitrate/frame rate are not unexpectedly zero.
- Check whether the issue begins immediately or after a source change/reconnect.

### 4. Check ingest and processing
- Review authorized, sanitized status/log evidence around the incident time.
- Look for failed ingest, missing video, processing errors, or repeated reconnects.
- Confirm whether the service reports active media, not just an active session.

### 5. Check delivery and playback
- In Developer Tools, inspect Console errors and Network failures.
- For WebRTC, inspect connection state and whether inbound audio/video statistics are increasing.
- For segmented playback, inspect playlist/manifest and media-request status where available.
- Compare the failing device with a working device.

### 6. Form a conclusion
State the stage supported by evidence (source, ingest/processing, delivery, or player/device). If evidence is incomplete, list the leading hypotheses and the next test instead of claiming a confirmed root cause.

## Evidence checklist

- [ ] Exact timestamp and timezone
- [ ] Scope: all viewers, some viewers, or one device
- [ ] Browser/OS/device and player version
- [ ] Screenshot or short recording, if safe to share
- [ ] Sanitized console/network evidence
- [ ] Playback or connection statistics
- [ ] Result from a second device/reference player
- [ ] Tests performed and results

## Example diagnostic note

**Observation:** Audio continues, but video remains black in one browser.  
**Test:** The same stream displays video in a second supported browser.  
**Interpretation:** A source-wide failure is less likely; investigate device/browser decoding or player integration next.  
**Status:** Not confirmed until codec/profile and player diagnostics are reviewed.
