# Streaming Troubleshooting Playbook

A practical, vendor-neutral playbook for investigating common live-streaming playback issues. This portfolio project demonstrates a structured support-engineering workflow: reproduce the symptom, collect evidence, isolate the failing stage, validate a hypothesis, and document the outcome.

> **Portfolio note:** This repository is an independently written, educational example. It uses synthetic scenarios and generic terminology. It does not contain customer data, company-internal dashboards, credentials, proprietary log queries, or confidential case notes.

## What this project covers

- Black screen, frozen video, and audio-only playback
- Audio/video synchronization problems
- Codec and device compatibility
- Evidence collection and root-cause isolation
- Post-fix validation and escalation notes

## Troubleshooting approach

1. **Clarify impact:** Is the issue affecting every viewer, some viewers, or one device?
2. **Reproduce:** Record the exact time, timezone, stream/session identifier (redacted in public examples), player, browser, OS, and steps.
3. **Map the media path:** Source/encoder → ingest → processing/packaging → delivery/network → player/device.
4. **Collect evidence:** Browser console/network logs, playback statistics, sanitized logs, and a short screen recording when appropriate.
5. **Test one hypothesis at a time:** Change one variable per test and note the result.
6. **Validate:** Re-test on more than one device and after a refresh/reconnect where relevant.
7. **Communicate:** Share confirmed facts, what has been ruled out, next action, owner, and timestamp.

## Repository map

- [`docs/black-screen.md`](docs/black-screen.md) — black screen, frozen video, audio-only playback
- [`docs/audio-video-sync.md`](docs/audio-video-sync.md) — measuring and isolating sync issues
- [`docs/codec-compatibility.md`](docs/codec-compatibility.md) — codec/profile/device checks
- [`examples/sample-incidents.md`](examples/sample-incidents.md) — fictional, anonymized practice cases
- [`templates/incident-template.md`](templates/incident-template.md) — reusable investigation template

## General tools used in the examples

- Browser Developer Tools: Console and Network panels
- Browser media diagnostics where available
- WebRTC diagnostics such as `chrome://webrtc-internals` for WebRTC sessions
- `ffmpeg`/`ffprobe` for inspecting media files you are authorized to analyze
- Sanitized application or server logs, when access is authorized

Tool availability and exact steps depend on the streaming stack. Never publish access tokens, stream keys, customer identifiers, private URLs, IP addresses, or unredacted logs.

## Example outcome

A useful investigation does not guess the cause from the symptom alone. It compares evidence across the source, ingest, delivery, and playback stages, then records which test supports or rules out each hypothesis.

## Disclaimer

This is a learning and portfolio project, not an official runbook for any vendor. Procedures and codec support vary by product, protocol, browser, and version. Verify current documentation before applying changes to a real system.
