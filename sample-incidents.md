# Sample Incidents (Fictional)

These examples are synthetic and are included to demonstrate a troubleshooting method.

## Case 1 — Black video in one browser

**Reported symptom:** A viewer hears audio but sees a black screen in Browser A.

**Checks performed**
1. Confirmed the stream was active during the reported time.
2. Compared playback in Browser A and Browser B on the same device.
3. Reviewed sanitized Console and Network evidence.
4. Checked whether inbound video statistics were increasing.

**Evidence:** Browser B displayed video; Browser A showed a decoder-related error.  
**Conclusion:** Evidence points toward a browser/device decoding or compatibility path; source-wide failure is less likely.  
**Next step:** Verify codec/profile support for Browser A and retest with an authorized known-good media source.  
**Validation:** Re-test after the approved change and record the outcome.

## Case 2 — Audio is ahead of video

**Reported symptom:** Audio is consistently ahead of the visual marker on two devices.

**Checks performed**
1. Captured the same sync test on both devices.
2. Estimated the offset at the beginning and after several minutes.
3. Compared with an authorized local/source recording.
4. Checked whether the offset changed after a player refresh.

**Evidence:** Similar fixed offset on both devices; source recording shows the same behavior.  
**Conclusion:** Source/encoder timing is a stronger hypothesis than a single-device playback problem.  
**Next step:** Review source timing and encoder configuration with the responsible team.  
**Validation:** Repeat the same measurement after the approved change.

## Case 3 — Playback fails after a media configuration change

**Reported symptom:** A stream plays on a laptop but fails on an older mobile device.

**Checks performed**
1. Collected media metadata using an approved diagnostic workflow.
2. Compared device and browser support with current official documentation.
3. Tested a known-good baseline stream.
4. Changed one variable at a time.

**Evidence:** The baseline stream works on both devices; the original media configuration fails only on the older device.  
**Conclusion:** A media/device compatibility difference is likely.  
**Next step:** Confirm the exact unsupported setting and agree on a compatible configuration.  
**Validation:** Verify playback on both devices and document the final settings.
