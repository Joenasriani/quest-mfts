# Quest-MFTS — Phase 1 repository and technical-source audit
Audit date: 2026-10-21
Repository: https://github.com/Joenasriani/quest-mfts
Branch: main
Status: PHASE 1 SOURCE AUDIT COMPLETED; publication NOT READY.
Phase 0 verdict: DEVELOP_FURTHER. Originality NOT_ESTABLISHED.

## Source inventory and coverage
Six files were present at the start of Phase 1: `README.md`, `CITATION.cff`, `RESEARCH_QUALIFICATION.md`, `index.html`, `research.html` and `sitemap.xml`. All were fetched/read through connected GitHub; current source was examined for claims, metadata, integration code and internal consistency. The main HTML document was approximately 997 lines before Phase 1 amendments. Git history was reviewed through the 29 commits returned in the repository's commits listing; this is not a cryptographic proof of the complete historical Git object set.

| File | Classification | Phase 1 finding |
|---|---|---|
| README.md | design description | Accurately states unvalidated full integration; retains no experimental results. |
| CITATION.cff | machine-readable citation | `type: software` reflects metadata convention but should not be presented as proof of XR application implementation; preferred final report citation needs separate publication identity. |
| RESEARCH_QUALIFICATION.md | Phase 0 record | Explicit limitations and classified claims. |
| index.html | primary design document | Extensive proposed components, suggested setup and conceptual scenario; code supplies webpage disclosure/scroll effects, not XR/simulator integration. Incorrect feature and compatibility language was corrected on main. |
| research.html | research summary and structured metadata | Explicitly calls the complete architecture unvalidated; no original empirical findings. |
| sitemap.xml | website discovery | Lists website URLs; not technical evidence. |

## Source-to-claim register
Use exact status vocabulary; *implemented* means repository code exists, not that its runtime was independently tested.

| ID | Claim | Status | Repository basis | Next evidence needed |
|---|---|---|---|---|
| C01 | Technical web document and simple DOM interaction source exist | VERIFIED IMPLEMENTATION (source inspected; runtime untested) | index.html | Browser smoke/accessibility checks |
| C02 | Proposed XR cockpit modalities are documented | DOCUMENTED DESIGN | README.md; index.html; research.html | Versioned architecture specification |
| C03 | Quest Pro has native eye-tracking hardware | Externally sourced component capability, NOT a project implementation | index.html | Meta SDK/runtime permissions and selected configuration |
| C04 | Quest 3 can supply built-in eye gaze | CONTRADICTED | index.html now specifies no native gaze | Meta official device matrix |
| C05 | A Quest 3 + external Pupil Labs pipeline works | TECHNICALLY PLAUSIBLE BUT UNTESTED | index.html | Mount, gaze API, driver, runtime and application evidence |
| C06 | VoiceAttack can control every cockpit function | UNSUPPORTED | index.html now limits to candidate macros | Simulator command mapping/tests |
| C07 | HOTAS, speech, headset, simulator and haptics operate together | UNSUPPORTED | no integration implementation in root files | Working bridge and logs |
| C08 | OpenXR Toolkit is a current integration component or recommended installation | CONTRADICTED | index.html corrected | Toolkit maintainer discontinuation notice |
| C09 | Simulator radar, HMDS, EOTS and DAS are fully equivalent to aircraft systems | UNSUPPORTED | index.html corrected | Feature-specific manufacturer/simulator sources; avoid equivalence |
| C10 | Passthrough displays the world outside a fictional aircraft | CONTRADICTED | index.html corrected | Separate application and imagery source would be needed |
| C11 | A documented end-to-end system achieves performance, accuracy or training gains | UNSUPPORTED | no experimental data | Actual pre-registered evaluation and raw observations |
| C12 | System architecture can be built with compatible hardware and custom middleware | TECHNICALLY PLAUSIBLE BUT UNTESTED | proposed data flow in index.html | Requirements matrix, prototype, compatibility logs |
| C13 | Proposed F-35 launch/combat scenario occurred | DOCUMENTED DESIGN, NOT TEST | index.html explicitly frames narrative as proposed | Recorded demonstration if asserted as actual |
| C14 | Quest-MFTS is the first system to combine these modalities | UNSUPPORTED | no systematic novelty comparison | Phase 2 verified prior-art review |

## Corrective actions in main
- Earlier Phase 1 commit `13af0113b213365709048be70977e3cd55453cc4`: corrected seven overstatements including full-system status, Quest 3 gaze, full voice control, military HMDS/DAS equivalence, and discontinued toolkit reference.
- Subsequent Phase 1 correction commit: replaced inaccurate simulator F-35 module/HMDS assumptions, qualified radar and targeting feature comparisons, clarified MR limitations and removed instructions to install discontinued OpenXR Toolkit; replaced the software data-flow diagram with a proposed/unverified interface schematic.
- All changes preserve the core conceptual design and author credit. No measured results or simulator source code have been invented.

## Unresolved Phase 2 or environment-dependent verification
1. Verify each named simulator's aircraft/module list and actual API/control/helmet-display support against current vendor documentation.
2. Establish current Meta Horizon Link, passthrough, Quest gaze permissions and supported OpenXR profiles by specific version, device and runtime.
3. Check current voice-recognition backends, bHaptics interface options, PC-HOTAS adapters and simulator plugin bindings.
4. Prior-art assessment with verified scholarly citations; bibliography in the original HTML contains search instructions rather than complete academic references.
5. Test HTML interaction, navigation, mobile layout and accessibility in a browser; static inspection is not runtime verification.
6. Establish licensing/third-party rights and final technical-report citation, date, version and reference list.
7. Hardware or simulator experiment is optional for a conceptual technical report but required for functionality/performance claims.

## Verification and boundary
Technical-source inspection of the six original root files and repository history completed. Source-level improvements can be verified by fetching committed blobs. Hardware integration, live browser behavior, scientific novelty and publication readiness have NOT been verified. This document is an audit record, not a research result or Zenodo release.
