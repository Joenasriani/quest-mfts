# Quest-MFTS — Enhancement Phase 2: Evidence-Labeled Simulation Scenario

**Status:** DOCUMENTED DESIGN; hypothetical walkthrough, not an executed experiment or working Quest-MFTS integration.  
**Author:** Joseph Ribal Nasr, Independent Researcher  
**Scope:** Illustration for the existing conceptual XR technical report, not a new prototype or added research result.

## Scenario objective and boundary

A civilian flight-simulation training exercise is used to explain how selected interfaces *might* cooperate. The scenario deliberately avoids pretending that a particular simulator exposes all the necessary events or that an F-35 module, external gaze adapter or haptic event bridge already exists.

**Candidate conditions:** A selected PC simulator with verified VR presentation and controller binding; a PC HOTAS; optional voice command software; optional supported headset gaze (for example Quest Pro, subject to user consent and runtime/SDK support); optional haptic vest with an independently implemented event bridge. The exact simulator version, headset firmware, event API, speech profile and device mappings are **not supplied or verified** by the repository.

## Step-by-step proposed interaction

| Stage | Intended action | Interface / dependency | Evidence status | Fallback or failure condition |
|---|---|---|---|---|
| 0. Preflight | Check headset connection, simulator bindings and permissions | Headset runtime; PC HOTAS; optional gaze, voice and haptic interfaces | Components may exist separately; integrated preflight **not implemented** | Disable unavailable optional paths; continue with simulator's documented controls |
| 1. Cockpit preparation | Select one simulator-supported checklist command using a spoken phrase | PC voice utility and a command profile for the exact simulator | **Proposed**, no Quest-MFTS profile tested | Use mapped physical/keyboard command; do not claim automatic recognition |
| 2. Flight control | Adjust throttle and direction using HOTAS | Windows device recognition plus game-specific control mapping | Commercial components available; Quest-MFTS mapping **unverified** | Use simulator's supported input or stop exercise |
| 3. Information selection | Select a non-safety-critical virtual instrument with gaze where support is confirmed | Quest Pro gaze permissions; runtime extension; custom app/simulator adapter | **Proposed**; no completed gaze-to-simulator bridge | Use head pointer, mouse or HOTAS binding; never relabel head direction as gaze |
| 4. Simulated alert | A deliberately generated simulator event is read by an adapter and mapped to an optional vibration | Exposed simulator event, event bridge, bHaptics SDK/device | **Proposed**; no event-to-vest pipeline verified | Use normal in-simulator visual/audio alert; do not mask essential cues |
| 5. Failure recovery | Voice/gaze/haptic adapter becomes unavailable during an exercise | Capability/health checks and fallback logic | **Proposed extension**; no recovery algorithm implemented in Quest-MFTS | Revert to simulator-native controls, signal loss visibly, or safely halt exercise |
| 6. Review | Examine command attempts, available interfaces, missed events and timing | Versioned logs, timestamps, operator observations | **Future validation requirement**, no measurements available | Mark unobserved values as missing; do not assign invented numbers |

## Intended user experience, clearly hypothetical

An operator begins a civilian training session with headset and HOTAS connected. The operator *could* issue a selected spoken checklist command, provided a validated input mapping exists. During flight, the HOTAS remains the primary physical control. Where permitted headset gaze data and an application adapter are available, the operator *might* highlight a virtual instrument; this is not a native Quest-MFTS feature. A simulator-defined training alert *could* be mirrored as a haptic cue, but only if an event source, adapter and compatible feedback SDK are integrated. On failure, conventional simulator input and existing visual/audio alerts should remain available.

**No steps above were executed, timed, observed with participants, or validated on a headset.** They are test cases for potential future engineering work.

## Why this scenario belongs in the report

It shows a causal dependency chain rather than listing products: a simulator command must have a source, mapping, state transition and feedback path. It also makes the primary risk explicit: standalone availability of parts does not establish their interoperable operation. Fallback behavior is a proposed design requirement, not a claim of original or successfully tested graceful degradation.

## Evidence and references
- Project technical document: [index.html](index.html)
- Project visual system architecture: [ARCHITECTURE_PHASE_A_VISUAL.md](ARCHITECTURE_PHASE_A_VISUAL.md)
- Prior-art and technical source register: [PHASE_2_TECHNICAL_PRIOR_ART.md](PHASE_2_TECHNICAL_PRIOR_ART.md)
- Khronos conditional gaze capability: https://registry.khronos.org/OpenXR/specs/1.1/man/html/XrSystemEyeGazeInteractionPropertiesEXT.html
- bHaptics official SDK documentation: https://docs.bhaptics.com/sdk/

**Publication limitation:** This example does not support claims of operability, compatibility, military-system equivalence, usability benefit, reliable fallback, or performance. Rights and publication approval remain separate.
