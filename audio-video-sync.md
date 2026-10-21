# Troubleshooting: Audio/Video Synchronization

## Common patterns

- **Fixed offset:** audio and video are consistently early/late by roughly the same amount.
- **Drift:** the offset grows over time.
- **Intermittent sync issue:** it appears after reconnects, packet loss, or source changes.
- **Device-specific offset:** one device/output differs while another remains synchronized.

## Step-by-step workflow

### 1. Establish a repeatable test
Use a permitted test source with a clear visual marker and matching sound (for example, a flash and beep). If using a real customer stream, obtain approval and avoid recording private content.

### 2. Compare devices
Play the same stream on two devices at approximately the same time. Prefer built-in speakers for the baseline test; Bluetooth and external audio devices can introduce additional output delay.

### 3. Measure the offset
Record the screen with audio, identify the visual marker and sound onset, and estimate the time difference. Use the same measurement method for both devices. Document measurement uncertainty.

A practical sign convention for this playbook:
- **Positive offset:** the audio event occurs before the corresponding video event.
- **Negative offset:** the video event occurs before the audio event.

### 4. Check whether it is fixed or drifting
Measure near the beginning and again after several minutes:
- Similar offset at both points suggests a mostly fixed delay.
- A growing offset suggests timing, clock, frame-rate, sample-rate, or timestamp issues may be involved.

### 5. Isolate the stage
- If a local/source recording is already out of sync, inspect source/encoder settings.
- If all devices show a similar offset, investigate upstream timing and processing.
- If only one device/output differs, inspect player buffering, device output, Bluetooth, and OS/browser behavior.
- If it begins after reconnects or packet loss, correlate the change with sanitized connection and timing evidence.

### 6. Validate after a change
Repeat the same test, on at least two devices if possible. Check both the initial offset and whether it drifts. Record the exact change and the before/after measurements.

## Report format

- Expected behavior:
- Actual behavior:
- Initial measured offset:
- Offset after test interval:
- Devices and outputs tested:
- Source/local recording result:
- Reconnect/refresh result:
- Evidence reviewed:
- Confirmed cause or remaining hypotheses:
- Validation result:
