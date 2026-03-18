# Pupil Closed-Loop Control System Demo

[![Nature](https://img.shields.io/badge/Nature-637,_1161–1169_(2025)-blue)](https://doi.org/10.1038/s41586-024-08340-w)

A demonstration preview of a real-time pupil-tracking system for rodent sleep experiments, featuring pupil-gated, closed-loop stimulation triggered by hippocampal sharp-wave ripples (SWRs)—transient neural events linked to memory replay.

**Related publication**  
**Chang, H**., Tang, W., Wulf, A. M. *et al.* **Sleep microstructure organizes memory replay.** *Nature* **637**, 1161–1169 (2025). [https://doi.org/10.1038/s41586-024-08340-w](https://doi.org/10.1038/s41586-024-08340-w)

> This repository is provided for demonstration purposes only. The complete public release—including software, documentation, and additional materials—will be made available soon at [ayalab1](https://github.com/ayalab1/).

## Highlights

- Real-time pupil tracking at ~15-24 FPS during rodent sleep experiments
- Continuous extraction of pupil size and eye-opening measurements
- State-dependent gating of downstream SWR closed-loop stimulation
- Synchronization with electrophysiology recordings
- End-to-end demonstration of hardware, software, and online control logic

## Figures

- **Hardware Setup**  
  ![Hardware setup](assets/eye_tracking_setup.png)

- **Closed-Loop Workflow**  
  ![Closed-loop workflow](assets/pupil_closed_SWR_system.png)

- **Real-Time Tracking GUI**  
  ![Real-time pupil tracking GUI](assets/realtime_pupil_tracking_gui.png)

## System Overview

The platform records the eye using a Raspberry Pi camera with infrared illumination, streams video to a PC for online pupil detection, and continuously estimates pupil-related features. These measurements are used to identify experiment-defined pupil states and open a downstream SWR detection window when threshold conditions are met. The electrophysiology system then evaluates ripple events and can trigger stimulation if ripple criteria are satisfied.

## Main Components

- Raspberry Pi camera system
- PC workstation running the real-time pupil-tracking pipeline
- Intan electrophysiology recording hardware
- SWR closed-loop stimulation system

## Workflow

1. The Raspberry Pi camera captures the eye and streams video to the PC.
2. The PC performs frame-by-frame pupil detection and extracts measurements such as pupil area and eye height.
3. The tracking pipeline determines whether the current pupil state matches the configured experimental condition.
4. When the threshold condition is met, the system sends a digital trigger to open the SWR detection window.
5. The downstream SWR system evaluates electrophysiology signals and can trigger stimulation when ripple criteria are satisfied.

## Related SWR Closed-Loop Studies

For methodological and conceptual details on the SWR closed-loop system, see:

- Oliva, A., Fernández-Ruiz, A., Leroy, F. & Siegelbaum, S. A. **Hippocampal CA2 sharp-wave ripples reactivate and promote social memory.** *Nature* **587**, 264–269 (2020). [https://doi.org/10.1038/s41586-020-2659-3](https://doi.org/10.1038/s41586-020-2659-3)

- Fernández-Ruiz, A. *et al.* **Long-duration hippocampal sharp wave ripples improve memory.** *Science* **364**, 1082–1086 (2019). [https://doi.org/10.1126/science.aax0758](https://doi.org/10.1126/science.aax0758)

## Typical Outputs

- Annotated tracking videos
- Time-series pupil measurements
- Sleep-state or behavioral-state labels
- Trigger and stimulation event logs
- Synchronized timing aligned to electrophysiology recordings

## Demo Assets

- `assets/eye_tracking_setup.png` — hardware setup for eye imaging
- `assets/pupil_closed_SWR_system.png` — end-to-end closed-loop workflow
- `assets/realtime_pupil_tracking_gui.png` — real-time pupil-tracking GUI
- `assets/online_tracking_preview.gif` — animated preview of online tracking and SWR disruption output
- `assets/online_tracking.mp4` — full demo video&emsp;&emsp;

## Demo Video

<p align="center">
  <b>Online Pupil Tracking GUI</b> &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
  <b>Brain Signal Monitor (Intan)</b> &emsp;&emsp;&emsp;
  <b>Brain Signal Closed-Loop GUI (Spikes8)</b>
</p>

<p align="center">
  ↓ &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
  ↓ &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;
  ↓
</p>

<p align="center">
  <a href="assets/online_tracking.mp4">
    <img src="assets/online_tracking_preview.gif" alt="Online tracking demo preview" width="100%">
  </a>
</p>
