# Samarth Prashant Bankar

Control systems, mechatronics, autonomous driving. I build the rig, write the firmware that
runs it, model the plant, and measure how far the model was off.

The repositories carry the measurements as well as the code: step responses, identified
parameters, and the runs that went wrong along with what changed afterwards.

## Autonomous driving

**Bosch Future Mobility Challenge 2026** — team OdyssiX. A 1:10 scale car driving an urban
circuit unaided: lane keeping, signs and traffic lights, intersections, parking. Two
repositories, talking to each other over micro-ROS at 460 800 baud.

| | |
|---|---|
| [**BFMC2026-Brain**](https://github.com/Samarth030312/BoschFutureMobilityChallenge2026-Brain) | Jetson Orin Nano, ROS 2 Humble, C++. Perception (lane geometry, free space, detection and tracking), planning (behaviour, global and local paths, mission supervisor, trajectory generation), EKF localisation and drift estimation, a safety layer with watchdog and emergency stop, and operator UI and telemetry. colcon, CycloneDDS, Docker for the driver containers. |
| [**BFMC2026-Embedded**](https://github.com/Samarth030312/BoschFutureMobilityChallenge2026-Embedded) | STM32F401RE Nucleo, C, FreeRTOS. BNO085 IMU read at 100 Hz over I²C on an interrupt, published over micro-ROS; TIM2 PWM out to the steering servo and a Quicrun ESC against a bench-calibrated map; a 500 ms command-silence deadman that returns both to neutral. 1 kHz loop, minimal ISRs, lock-free UART ring. |

[**thin-structure-segmentation-evaluation**](https://github.com/Samarth030312/thin-structure-segmentation-evaluation)
— mean-IoU under-reports thin structures like lane lines, and the size of the error follows
from the geometry. Derivation, a benchmark against clDice, 62 tests. An evaluation study, not
a new model.

## Control systems and mechatronics

A rig, a model of it, and the gap between the two.

| | |
|---|---|
| [**steval-edukit**](https://github.com/Samarth030312/steval-edukit) | Rotary inverted pendulum on an STM32F401RE. Bare-metal C at 500 Hz, energy swing-up handing over to LQR, parameters identified on the rig, MATLAB app and Simulink model. |
| [**rhino-rmcs-2303-dc-servo-control**](https://github.com/Samarth030312/rhino-rmcs-2303-dc-servo-control) | Speed and position control of a 100:1 geared encoder motor over Modbus, from an Arduino Uno. 201 runs across four days; the identified model predicts unseen runs to about 5 %, including a textbook PI design that limit-cycles on the real drive. |
| [**arduino-temperature-control-lab**](https://github.com/Samarth030312/arduino-temperature-control-lab) | Bulb heater, DHT sensor, solid-state relay. On-off through PID, and the firmware's safety behaviour — over-temperature cut-off, sensor-failure stop, host watchdog — tested against an emulated plant. |
| [**arduino-water-level-control-lab**](https://github.com/Samarth030312/arduino-water-level-control-lab) | Pumped tank with an HC-SR04 level sensor. Echo rejection, median filter, a rate gate on how fast water can physically move, dry-run and overflow guards. |
| [**pneumatic-circuits-openmodelica**](https://github.com/Samarth030312/pneumatic-circuits-openmodelica) | ISO 6358 valves and cylinders written from first principles in OpenModelica. Two-hand press, reciprocation and pressure-stamping circuits, cross-checked against an independent Python model. |

## Simulation

| | |
|---|---|
| [**rigid-body-simulator**](https://github.com/Samarth030312/rigid-body-simulator) | 3D rigid-body dynamics in MATLAB from Newton–Euler up: a thrown die whose landing face is read off the simulated orientation, a 3R arm with recursive Newton–Euler dynamics, a four-bar linkage solved through loop closure. Interactive app, 118 tests, CI on Linux, Windows and macOS. |

## Elsewhere

[**Alpino**](https://github.com/Samarth030312/Alpino) — decision-support tooling for a health
foods business: OCR invoice reconciliation, attrition risk scoring, RFM segmentation, behind a
Streamlit front end. Python, not control.

**csc210-csc530-assessment** *(private)* — self-hosted coding-quiz platform on Moodle,
CodeRunner and Jobe in Docker, for running programming assessments at course scale.

---

How I work: conventions, frames and units fixed in writing before any code; results checked
against a closed form, a conservation law or a second derivation; the number kept rather than
the impression; and one entry point plus CI, so it runs on someone else's machine too.

**Tools** — MATLAB and Simulink · C/C++ on STM32 and Arduino · Python · Modelica · Docker ·
Git and GitHub Actions
