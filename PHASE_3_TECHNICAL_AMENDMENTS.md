# Quest-MFTS — Phase 3 Technical Amendment Register
Date: 2026-10-21
Branch: main
Research classification: conceptual XR architecture / feasibility proposal
Overall status: NOT READY FOR PUBLICATION; no validated integrated system.

## Changes on main
Commit 291c6025c564fcf16a15072e5f8f3defb2b9f133:
1. Added a compact compatibility and evidence matrix to the primary public technical document, covering headset gaze, OpenXR, external tracking, HOTAS, speech, haptics, passthrough, simulator versions, and overall integration.
2. Included a proposed and explicitly unexecuted evaluation protocol, requiring actual versioned hardware/software configurations, logs, errors and measurements before results may be claimed.
3. Incorporated bibliographic references to relevant cockpit interaction and VR flight simulation antecedents, as well as authoritative developer references for gaze, toolkit discontinuation, and haptics.
4. Removed universal SteamVR setup language in favor of conditional runtime requirements.
5. Clarified feature-specific SDK selection and the distinction between the OpenXR standard and actual extension/runtime support.
6. Removed a redundant outdated discussion reference to the discontinued OpenXR Toolkit.

## Source-to-design rationale
- Native Quest Pro eye tracking is a hardware capability, not a Quest-MFTS demo.
- Quest 3 does not feature native eye tracking; external integrations are unverified.
- OpenXR `XR_EXT_eye_gaze_interaction` requires runtime support, including `supportsEyeGazeInteraction` (see Khronos spec).
- Voice macros, Windows HOTAS drivers and haptic SDK support do not demonstrate interoperability among tools.
- Passthrough shows local physical surroundings; it does not substitute for synthetic sensor representations of the simulated aircraft's exterior.
- Simulator-specific support must be verified by simulator, module and version.
- Prior art prevents a broad scientific novelty assertion without narrower proof.

## Evidence and source register
- https://registry.khronos.org/OpenXR/specs/1.1/man/html/XrSystemEyeGazeInteractionPropertiesEXT.html
- https://github.com/mbucchia/OpenXR-Toolkit/releases
- https://developers.meta.com/vr/essentials/horizon-os-immersive-features/
- https://docs.bhaptics.com/sdk/unity/guide
- https://doi.org/10.1145/3626481
- https://doi.org/10.16910/jemr.15.3.11
- https://github.com/Joenasriani/quest-mfts/blob/main/PHASE_2_TECHNICAL_PRIOR_ART.md

## Restrictions and remaining work
- The HTML-compatible matrix is a technical specification, not a compatibility test.
- No Quest/Windows/flight simulator execution, benchmark, accessibility or responsive-browser test is claimed.
- Some existing sourcing instructions in the historical technical document are examples, not tested assembly steps. Do not interpret these as a validated build guide.
- Missing: a full documented interface specification, detailed reproducibility protocol with pinning of exact versions, full bibliography metadata re-verification, diagrams appropriate to a scholarly manuscript, rights and license sign-off.
- Phase 4 must use only documented and attributed design claims, and explicitly distinguish third-party technologies from original contributions.
- A technical design report can be prepared without a built prototype; any implementation-success or performance claim requires actual evidence.
