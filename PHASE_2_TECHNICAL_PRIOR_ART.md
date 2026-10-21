# Quest-MFTS — Phase 2 technical verification and prior-art register

Reviewed: 2026-10-21 (UTC). Branch: main.
Status: PHASE 2 FOCUSED VERIFICATION COMPLETED; full system UNVALIDATED; publication NOT READY.
Scope: authoritative vendor/API material and two directly relevant peer-reviewed antecedents; this is a bounded literature review, NOT an exhaustive systematic search.

## Executive determination
The documented Quest-MFTS proposal is a concept-level integration design. Its individual modalities have published antecedents, including peer-reviewed VR cockpit studies and eye-tracked flight simulation with physical HOTAS controls. Scientific first-of-kind novelty is NOT ESTABLISHED. A carefully scoped design/feasibility report remains plausible, with accurate sourcing and no performance or interoperability claims.

## Verified prior art (bibliographic identity + claim-level relevance)

**P01 — Auer et al. (2023)**. Stefan Auer, Christoph Anthes, Harald Reiterer, Hans-Christian Jetter. *Aircraft Cockpit Interaction in Virtual Reality with Visual, Auditive, and Vibrotactile Feedback.* Proceedings of the ACM on Human-Computer Interaction, 7(ISS), Article 445, 24 pages (publisher's article numbering; an institutional repository also lists pages 420–443). DOI: https://doi.org/10.1145/3626481 . Primary sources: https://iss2023.acm.org/details/iss-2023-papers/20/Aircraft-Cockpit-Interaction-in-Virtual-Reality-with-Visual-Auditive-and-Vibrotacti and https://research.uni-luebeck.de/en/publications/aircraft-cockpit-interaction-in-virtual-reality-with-visual-audit/ . The study compared VR and physical-cockpit interaction using visual, auditory and haptic feedback, with 24 participants. The reported mixed results caution against assuming simple vibrotactile augmentation improves performance. The paper does NOT verify the Quest-MFTS architecture.

**P02 — Hebbar et al. (journal version electronically published 2023; volume records 2022)**. P. Archana Hebbar, Sanjana Vinod, Aumkar Kishore Shah, Abhay A. Pashilkar, Pradipta Biswas. *Cognitive Load Estimation in VR Flight Simulator.* Journal of Eye Movement Research 15(3). DOI: https://doi.org/10.16910/jemr.15.3.11 . Primary journal landing page: https://bop.unibe.ch/JEMR/article/view/9036 ; PubMed: https://pubmed.ncbi.nlm.nih.gov/39234220/ ; publisher display: https://www.mdpi.com/1995-8692/15/3/23 . Describes a VR flight simulator with an HTC Vive Pro Eye, Thrustmaster HOTAS, ocular/EEG sensing and cognitive-load estimation. This is a substantial antecedent for eye-tracked VR flight simulation and physical controls. The manuscript should distinguish journal volume year from online publication date rather than silently conflate them.

A 2021 conference version titled *VR flight simulator with cognitive load estimation feature* also appears in a PLMSS abstract collection: https://plmss.org.in/plmss-2021/PLMSS_Book_of_Abstract.pdf . Treat as related antecedent rather than an independent replicated trial without paper-level confirmation.

## Authoritative technology evidence

| ID | Component / claim | Supported fact | Boundary for Quest-MFTS | Source |
|---|---|---|---|---|
| T01 | Eye tracking on headset | Meta lists Quest Pro native eye tracking; Quest 3/3S do not have eye-tracking hardware. Requires consent and fallback. | Do not call Quest 3 eye-tracked without a separately verified external pipeline. | https://developers.meta.com/vr/essentials/horizon-os-immersive-features/ |
| T02 | OpenXR gaze | `XR_EXT_eye_gaze_interaction` defines `supportsEyeGazeInteraction`; current device/runtime must report true for usable gaze actions. | Extension appearing in standard does not prove functioning simulator mapping. | https://registry.khronos.org/OpenXR/specs/1.1/man/html/XrSystemEyeGazeInteractionPropertiesEXT.html |
| T03 | OpenXR Toolkit | Maintainer's release notice states support discontinued as of 2024 and recommends against installing/using it for newer games. | Do not include toolkit in required modern architecture or setup instructions. | https://github.com/mbucchia/OpenXR-Toolkit/releases |
| T04 | HOTAS drivers | Thrustmaster maintains Windows T.A.R.G.E.T. support for HOTAS Warthog and other compatible controllers. | This verifies driver availability only, not a particular simulator binding or XR middleware route. | https://support.thrustmaster.com/en/product/hotaswarthog-en/ |
| T05 | Voice macros | VoiceAttack vendor documentation describes recognized command phrases, profiles and command execution. | No Quest-MFTS voice profile or measured recognition accuracy is supplied. | https://www.voiceattack.com/VoiceAttackHelpV2.pdf |
| T06 | bHaptics SDK | Official Unity integration guide supplies defined SDK, application configuration and runtime prerequisites. | Requires actual game/event bridge; no automatically functioning DCS sensor-alert-to-vest pipeline is proven. | https://docs.bhaptics.com/sdk/unity/guide |
| T07 | MR passthrough / scene integration | Platform-supported immersive features vary by device and software versions. | Headset passthrough exposes room imagery, not aircraft external sensors or DAS functionality. | https://developers.meta.com/vr/essentials/horizon-os-immersive-features/ |
| T08 | F-35 / DAS / EOTS game-feature comparisons | Repository offers conceptual simulator examples but no source establishing an official DCS F-35 module or feature-equivalence to operational systems. | Remains UNVERIFIED: require explicit simulator developer documentation for any exact aircraft, sensor, or HUD claim. | https://github.com/Joenasriani/quest-mfts/blob/main/index.html |

## Comparison of contribution
- VR cockpit simulation with haptic/visual/auditory interaction: **prior art established** by P01.
- Eye-tracked VR flight simulator with HOTAS: **prior art established** by P02.
- OpenXR, speech macros, off-the-shelf HOTAS, haptic SDKs: **existing independent toolchain capabilities**, not project inventions.
- Quest-MFTS's precise system-composition narrative and design checklist: **documented project-specific design**, but unique inventive integration and technical reproducibility NOT ESTABLISHED.
- Simultaneous end-to-end Quest Pro gaze + HOTAS + voice + haptics + simulator: **UNSUPPORTED as an implemented Quest-MFTS result**.
- Measured effectiveness, latency, reliability, safety or training gains: **UNSUPPORTED**.

## Phase 2 decision and forward constraints
**Verdict: DEVELOP_FURTHER.** A report about a *proposed* multimodal XR simulation architecture can serve as a transparent, reusable design analysis. No claim of empirical or priority novelty should appear unless supported by additional direct evidence.

Mandatory next-phase work for a responsible descriptive technical report: cite P01/P02 and authoritative sources near the claims; add a device/runtime/simulator compatibility matrix with verified, conditional and unknown categories; update/verify the main page's remaining setup prescriptions; draw a clearly proposed architecture diagram; include limitations and bibliography. Testing is NOT required to publish an explicitly conceptual report, but must precede claims that Quest-MFTS integrates or performs successfully.

Unverified in Phase 2: full systematic scholarly search, exact product/firmware configurations, DCS/VTOL VR version-specific features, physical integration, device permissions at runtime, end-to-end simulator operation, hardware performance, Google Scholar indexing, copyright clearance and release licensing.

## Source integrity
These URLs are citations to external works, not authorization to redistribute their full texts or figures. The author of Quest-MFTS is not an author of P01/P02. No invented test metrics, ORCID, DOI for Quest-MFTS, or asserted publication status.
