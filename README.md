



GO TO:
https://joenasraiani.github.io/quest-mfts/



# Project: Multi-Function Tactical System (MFTS) for Meta Quest

## 1. Project Overview

The Multi-Function Tactical System (MFTS) is a comprehensive project to design and integrate a next-generation, immersive simulation cockpit.

The core vision is to "fuse" commercially available hardware (like the Meta Quest Pro/3 headset) with a stack of specialized peripherals and middleware. The goal is to replicate the "hands-on, heads-up" operational capabilities of an advanced fighter, such as the F-35, for high-fidelity PC-based simulators (e.g., *DCS World*, *VTOL VR*).

This system moves beyond a simple "VR headset and joystick" setup by integrating voice commands, eye-tracking, and haptic feedback into one cohesive, "fused" architecture.

## 2. Core Features (Baseline System)

The standard MFTS is built on a "Sensor Fusion Architecture," combining the following 10 sub-systems:

* **Speech-Recognition:** (via *VoiceAttack*) for hands-free control of checklists, radios, and wingmen.
* **Helmet-Mounted Display (HMDS):** The VR headset itself, used as the primary flight and targeting display.
* **Off-Boresight Targeting:** (via Quest Pro Eye-Tracking + *OpenXR Toolkit*) to cue and lock targets simply by looking at them.
* **HOTAS Integration:** (e.g., *Thrustmaster Warthog*) for tactile, muscle-memory control of the aircraft.
* **Simulated Life Support:** (via *bHaptics*) for tactile feedback simulating G-forces, impacts, and system failures (e.g., OBOGS).
* **Advanced Sensor Simulation:** Leveraging in-game sensors (AESA, DAS, EOTS) and displaying them on the HMDS.
* **Electronic Warfare Suite:** Using haptics and audio to provide directional threat warnings (RWR, MWS).
* **CNI Suite:** Integrating voice commands with in-game radios and navigation.
* **Sensor Fusion:** The software backbone (*OpenXR Toolkit*, *SteamVR*) that makes all peripherals work as a single device.
* **Logistics & Management:** The in-game "meta" layer of mission planning and re-arming.

## 3. The Upgrade Path: Block 4 & Future-Proofing

This is the primary conceptual focus of the project, defining the evolution from a Virtual Reality (VR) system to a true Mixed Reality (MR) tactical environment.

The "Block 4" upgrade is not a single piece of hardware but a developmental framework that relies on next-generation headset capabilities and new software APIs.

### Core Concept:
To leverage high-resolution, wide-FOV color passthrough (as seen in the Meta Quest 3 and Pro) to create a true **Distributed Aperture System (DAS)**. Instead of being fully blind to the real world, the pilot can "see through" the virtual cockpit to view their real-world environment, with tactical data overlaid on top.

### Implementation Method:

1.  **Hardware (Future):** Next-generation headsets with improved passthrough cameras (higher resolution, better low-light, wider dynamic range).
2.  **Software (Key APIs):**
    * **Meta Passthrough API:** To programmatically blend the real-world camera feed with the virtual game world.
    * **OpenXR Scene Understanding:** To allow the system to "map" the real-world room.

### Resulting Capabilities (The "Upgrade"):

* **True DAS Simulation:** When a pilot looks "down through the floor" of their F-35, the system will not show a 3D model of the ground. Instead, it will activate the headset's passthrough cameras, showing the **pilot's real-world floor, feet, and rudder pedals**, with the in-game targeting (EOTS) and sensor data projected directly onto that real-world view.
* **Mixed-Reality C2:** By using *OpenXR Scene Understanding*, the system could identify the pilot's real desk and walls. A custom "Tactical C2" app could then project mission maps, comms windows, or strategic data onto these real surfaces, existing *alongside* the virtual cockpit.
* **Seamless Interaction:** The pilot could glance at a real-world tablet running a navigation app, then look back "into" the cockpit to engage a target, all without removing the headset.

## 4. Project Status

This project guide documents a system that is **90% achievable today** using existing hardware (Quest Pro, bHaptics, VoiceAttack, OpenXR Toolkit).

The **"Block 4" component is conceptual** and serves as a future development roadmap. It relies on deeper, custom software development and the maturation of Mixed Reality APIs for its full implementation.
