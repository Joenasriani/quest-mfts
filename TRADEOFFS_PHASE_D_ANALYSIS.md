# Quest-MFTS — Enhancement Phase 4: Engineering Trade-off Analysis

**Author:** Joseph Ribal Nasr, Independent Researcher  
**Classification:** comparative technical design analysis, not experimental results  
**Evidence:** source-level Quest-MFTS proposal, commercially documented component features and published antecedents; no hardware integration tests.

## Decision framework

Selection is conditional on an identified simulator, headset, runtime and use case. More input modalities do not intrinsically produce better performance, usability, reliability or safety. The comparison below describes *potential* benefits, costs and failure mechanisms, not measured effects.

| Design choice | Potential design rationale | Integration burden and failure modes | Reject or defer when | Evidence class |
|---|---|---|---|---|
| Physical HOTAS instead of virtual-only cockpit controls | Tactile axes and repeatable physical reference may suit continuous flight controls | Driver bindings, physical placement, input conflicts, controller-to-virtual alignment | No supported simulator mapping or ergonomic fit; essential controls inaccessible | DOCUMENTED DESIGN; component capability established, Quest-MFTS mapping unverified |
| Speech macros for secondary tasks | May reduce manual navigation for selected discrete commands | False activation, speech recognition errors, noise, command-profile maintenance | Consequential commands cannot be confirmed or recognition reliability is unknown | TECHNICALLY PLAUSIBLE BUT UNTESTED |
| Eye-gaze selection rather than head-directed pointer | Could decouple attention/selection from headset orientation on hardware exposing gaze | Consent, tracking availability, runtime extensions, calibration, accidental selection, custom simulator binding | No supported eye tracker, user consent or verified application path | TECHNICALLY PLAUSIBLE BUT UNTESTED; Quest Pro capability independent |
| Haptic cues supplementing audio/visual alerts | Could provide an additional nonvisual feedback channel | Source-event access, SDK integration, ambiguous cue encoding, latency, desynchronization | Simulator lacks an event interface or haptic cues obscure critical warnings | TECHNICALLY PLAUSIBLE BUT UNTESTED |
| Passthrough MR rather than immersive VR-only view | Could reveal real physical controls or surroundings in a custom MR application | Passthrough permissions, scene registration, display composition, lighting and depth/occlusion limitations | Simulator is PCVR-only with no integration path or stable registration | TECHNICALLY PLAUSIBLE BUT UNTESTED |
| Multiple optional modalities rather than single default control | Could offer alternative input paths for specific users and failures | State synchronization, priority conflicts, fallback logic, test-matrix growth | No evidence of deterministic arbitration or safe fallback | DOCUMENTED DESIGN; no recovery algorithm implemented |
| Single tightly controlled baseline rather than feature-rich setup | Fewer unknown dependencies, clearer version-pin and troubleshooting | Reduced feature breadth | Research question specifically requires multimodality | RECOMMENDED METHODOLOGY; not a measured result |

## Trade-off reasoning

**Control criticality.** Continuous directional control and safety-significant commands should not depend on unverified voice, gaze or haptic paths. Preserve the simulator's documented primary controls.

**Capability uncertainty.** Quest Pro's native gaze sensors, OpenXR gaze extensions and simulator bindings are separate prerequisites. Quest 3 lacks native eye-gaze hardware. The ability to render passthrough does not establish external simulated aircraft sensing.

**Feedback interpretation.** bHaptics SDK existence does not verify an alert-to-vest event adapter. Haptic augmentation must not suppress the simulator's existing audio/visual alerts.

**System complexity.** Each optional modality introduces version-dependent adapters and additional test cases. The most feature-rich concept is not automatically the preferred engineering choice.

**Evidence requirements.** A later comparison could record command success, false activations, event-to-feedback delay, fallback recovery, frame timing and operator workload, but this document reports **no experimental results**.

## When each configuration is appropriate to investigate

- **Basic PCVR (A):** initial feasibility checks with an exact simulator, Quest PCVR path and HOTAS model; lowest integration ambition.
- **Multimodal candidate (B):** only after A is reproducibly validated, plus identified voice commands and an accessible simulator event source.
- **Advanced concept (C):** only when supported gaze and/or MR APIs, device permission, calibration and custom integration are separately demonstrated.

These are design sequencing suggestions, not claims that any tier works or improves training.

## Scholarly and API boundary

- Auer et al., *Aircraft Cockpit Interaction in Virtual Reality with Visual, Auditive, and Vibrotactile Feedback*, DOI https://doi.org/10.1145/3626481, documents existing multimodal VR cockpit work.
- Hebbar et al., *Cognitive Load Estimation in VR Flight Simulator*, DOI https://doi.org/10.16910/jemr.15.3.11, provides a relevant eye-tracked flight simulator and HOTAS antecedent.
- Khronos runtime eye-gaze capability: https://registry.khronos.org/OpenXR/specs/1.1/man/html/XrSystemEyeGazeInteractionPropertiesEXT.html
- bHaptics SDK guidance: https://docs.bhaptics.com/sdk/unity/guide

Originality of Quest-MFTS's general component combination is **NOT ESTABLISHED**. This trade-off register is an analytical expansion of the existing report, not evidence of new functionality or empirically supported superiority.
