# Quest-MFTS — Enhancement Phase 3: Three Proposed System Configurations

**Author:** Joseph Ribal Nasr | Independent Researcher  
**Classification:** Documented design and comparative feasibility framework, **not an installed or tested configuration**.  
**Repository:** https://github.com/Joenasriani/quest-mfts  
**Relationship:** Read alongside [ARCHITECTURE_PHASE_A_VISUAL.md](ARCHITECTURE_PHASE_A_VISUAL.md), [SCENARIO_PHASE_B_WALKTHROUGH.md](SCENARIO_PHASE_B_WALKTHROUGH.md), and [PHASE_2_TECHNICAL_PRIOR_ART.md](PHASE_2_TECHNICAL_PRIOR_ART.md).

## What the configurations compare

The tiers represent *additional requirements and potential interface complexity*, **not product offerings**, tested builds, measured performance improvements, or a guaranteed upgrade path. Some simulators require different runtimes or support fewer modalities. Hardware cost and compatibility are intentionally not quoted without a date-specific verified bill of materials.

| Property | A. Basic PCVR control | B. Multimodal candidate | C. Advanced experimental concept |
|---|---|---|---|
| Primary aim | Present a VR simulator with conventional physical controls | Explore voice and haptic augmentation of conventional controls | Investigate permitted gaze and/or MR interaction without treating them as automatic features |
| Headset | VR-capable Quest model with compatible PCVR route; exact models/versions TBD | Same compatible PCVR route as A | Quest Pro for *potential* native eye-gaze; Quest 3 only for passthrough without native eye gaze |
| Simulator | Exact application/aircraft version with verified VR support | Same, plus required command and event interfaces if available | Same, plus verified simulator adapter or separate native Quest MR app |
| Physical controls | PC HOTAS with simulator-supported bindings | HOTAS remains primary input | HOTAS remains primary input; alternative selection channel is optional |
| Voice | Not required | Candidate Windows speech/command profile | Optional, conditional on B interface verification |
| Haptic feedback | Standard game feedback only | Optional SDK/device/event bridge if simulator exposes relevant data | Optional, with event-mapping and safety checks |
| Eye gaze | Not required | Not required | **Conditional:** device eye sensor, consent, extension/runtime support, custom application mapping; no Quest-MFTS integration shown |
| Passthrough MR | Not required | Not required | Separate app/runtime capability; physical room visibility does not equal aircraft DAS |
| Failure behavior | Revert to simulator's documented controls | Voice/haptic features fail independently; native controls remain | Loss of gaze/MR must not disable physical control or suppress normal simulator cues |
| Verification currently available | Documented component capabilities only | Documented standalone tools/SDKs only | Proposed research interfaces, not validated |
| Main unknown | Runtime and device mappings | Voice command reliability, event access, cue timing | Runtime gaze, SDK permissions, simulator bridge, calibration, MR registration |
| Feasibility decision | Candidate for future controlled setup | Do not assert interoperability without per-interface logs | **Stop at design stage** until prerequisites and event/control data paths are proven |

## Configuration A: minimum defensible starting point

Choose one exact simulator version, a compatible Quest PCVR transport/runtime and one PC HOTAS model. Record application documentation, mapping screenshots, firmware, drivers, PC specifications, and all failure cases. A successful PCVR game session using ordinary peripherals would validate *that setup only*, not the multimodal Quest-MFTS research concept. **No such setup test is present in this repository.**

## Configuration B: added feedback and hands-free commands

VoiceAttack or another supported command tool could trigger documented simulator actions. An optional haptic device might respond to simulator signals if an accessible, versioned event source and application adapter exist. Standalone voice or haptics product availability is insufficient to establish integration. Failure cases must include misrecognized commands, unsupported bindings, disconnected devices, and missing simulator event signals.

## Configuration C: conditional eye-gaze and MR design

Quest Pro has native eye tracking, but it requires permission, runtime capability reporting, and a custom integration route before it could control a simulator selection. Quest 3 has **no native eye tracking**; an external tracker is *unverified*. Passthrough may expose nearby real-world surroundings within an appropriate Quest MR application; it does not provide simulated aircraft external-sensor or DAS imaging. Eye gaze and MR can be independent options, not automatically co-installed or simultaneously supported.

## Decision rules (not observed results)

1. Confirm headset, simulator, PCVR route, and controller compatibility **before** adding optional modalities.
2. For every extension, document an API/source of data, an adapter, a target binding, and fallback behavior.
3. If source signals or runtime permissions are absent, label the path **UNAVAILABLE/UNVERIFIED**, never “working.”
4. Do not infer reduced workload, superior training, increased realism, lower latency, or safety from feature count.
5. Compare potential configurations as design choices, not empirical performance rankings.

## Research significance and boundaries

The tiered comparison contributes a **reusable design-decision lens**: it distinguishes baseline immersion from optional multimodal augmentation and higher-risk experimental interaction. This presentation and comparison do **not** establish scientific novelty, usability gains, cost-effectiveness, or implementation success. Relevant antecedents include Auer et al., DOI [10.1145/3626481](https://doi.org/10.1145/3626481), and Hebbar et al., DOI [10.16910/jemr.15.3.11](https://doi.org/10.16910/jemr.15.3.11).

**Authoritative interface boundary:** [OpenXR runtime gaze property](https://registry.khronos.org/OpenXR/specs/1.1/man/html/XrSystemEyeGazeInteractionPropertiesEXT.html); [bHaptics SDK guide](https://docs.bhaptics.com/sdk/unity/guide).

**Evidence status:** DOCUMENTED DESIGN. No hardware configuration, simulator version, speech profile, gaze adapter, haptic pipeline or integrated system was tested to create this section. No Zenodo publication is authorized.
