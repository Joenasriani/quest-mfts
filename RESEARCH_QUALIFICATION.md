# Research qualification and evidence register
Date: 2026-10-21
Status: DEVELOP_FURTHER / NOT_READY
Scope: Repository documentation inspected; no hardware execution or independent literature review completed.

## Phase 0
- Artifact: public HTML systems-design document, research summary, README and citation metadata.
- Classification: conceptual XR systems architecture / technical feasibility proposal; not an empirical study, validated simulator, or operational aircraft system.
- Originality: NOT_ESTABLISHED. Multimodal inputs, OpenXR, HOTAS, haptics and VR simulation predate this project. A distinct novel integration method has not been demonstrated.
- Verified contribution: a structured, public proposal grouping multiple XR interaction modalities into a cockpit simulation scenario.
- Beneficiaries: XR interface designers, simulation educators, HCI researchers and prototyping teams; they may use the component checklist and proposed architecture as a starting point, not as a tested integration recipe.
- Research value: an explicit interoperability and human-interface validation study could answer whether specific hardware/software configurations work together reliably.
- Publication value: a citable technical report could preserve design rationale and limitations if properly sourced; Zenodo is a possible destination, not a certification.
- Recommended output: technical design / feasibility report, not a software release describing an implemented XR system.
- Decision: DEVELOP_FURTHER.

## Claim register
| Claim | Classification | Evidence / limit |
|---|---|---|
| A proposed multimodal XR cockpit architecture is documented | DOCUMENTED_DESIGN | README.md; index.html; research.html |
| The website provides navigation and interactive document disclosure | VERIFIED_IMPLEMENTATION (code inspected only) | index.html DOM event listeners; browser runtime not independently tested |
| An end-to-end Meta Quest + HOTAS + gaze + speech + haptics simulator operates | UNSUPPORTED | No integrated runtime, test logs or simulator interface code found in inspected root files |
| Components can be integrated in a selected configuration | TECHNICALLY_PLAUSIBLE_UNTESTED | Device, API and simulator compatibility not established |
| The architecture improves performance, immersion or training | UNSUPPORTED | No controlled comparisons or outcome measurements |
| The project has a unique first-of-its-kind architecture | UNSUPPORTED | No systematic prior-art comparison |
| The complete system is 90% feasible | UNSUPPORTED | No defined requirements denominator or measurements; README already rejects this percentage |
| Military interface analogy demonstrates military-grade capability | CONTRADICTED as a project capability claim | README explicitly disclaims operational equivalence |

## Mandatory work before technical-report publication
1. Establish source provenance, current Git commit, author-approved rights and license.
2. Identify each device and simulator configuration by model, firmware/software and supported API; mark all untested combinations.
3. Create a block diagram and interface/data-flow specification distinguishing existing APIs from proposed middleware.
4. Replace unsourced technical assertions with vendor specifications or peer-reviewed references; distinguish source-supported facts from proposals.
5. Perform a focused antecedent comparison against published XR cockpit, multimodal HCI and simulator integration work; do not assert novelty until evidenced.
6. Provide a reproducible evaluation protocol with measurable outcomes and explicit failure criteria. Do not invent test results.
7. Independently verify citations, accessibility, metadata, publication rights and final release package before requesting approval.

## Optional future empirical study
Record motion-to-photon/frame timing where measurable, speech recognition accuracy, gaze selection error, input-to-feedback latency, peripheral mapping reliability, task completion and simulator stability. These are proposed measures, not collected results.

## Metadata caution
CITATION.cff currently declares `type: software`. Citation File Format primarily supports software/dataset typing; do not interpret this field as evidence of implemented XR simulator software. For a future technical-report deposit, assign the correct report resource type in destination metadata and cite the actual report separately.

## Verification limitations
Only public repository contents and text/code paths were inspected. No headset, peripheral, simulator, live-browser testing, external scholarly source validation, license approval or Zenodo deposit was performed. No claim of publication readiness is made.
