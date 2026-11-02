# Samarth Prashant Bankar

**Control systems, mechatronics and autonomous driving.** I build the whole loop: the rig,
the firmware that runs it, the model that predicts it, and the measurements that say which
of the two was wrong.

Most of what is here follows the same pattern. Derive the physics from first principles,
write it down with its conventions and its sign choices, implement it, then check it
against a closed-form answer, a conservation law or a second independent derivation — and
record the number, not the impression. The hardware repositories carry every run the rig
ever did, including the ones that failed.

---

## Autonomous driving

| | |
|---|---|
| **[OdyssiX — Bosch Future Mobility Challenge](https://github.com/OdyssiX-BFMC2026)** | Team repositories for the 2025 and 2026 editions: the perception and planning stack on a Jetson, and the embedded platform on an STM32 — a 1:10 scale vehicle that has to drive an urban circuit on its own. |
| **[thin-structure-segmentation-evaluation](https://github.com/Samarth030312/thin-structure-segmentation-evaluation)** | Why mean-IoU misleads for lane lines and thin road markings, with a geometric explanation and a reproducible benchmark. An evaluation study, not a new model — no state-of-the-art claim. 62 tests. |

## Control systems and mechatronics

Each of these is a real rig, a model of it, and the gap between them.

| | |
|---|---|
| **[steval-edukit](https://github.com/Samarth030312/steval-edukit)** | A rotary inverted pendulum, from first principles to a rig that swings up and balances. Bare-metal STM32F401RE firmware deciding 500 times a second, a MATLAB lab app, a Simulink model, and every measurement. |
| **[rhino-rmcs-2303-dc-servo-control](https://github.com/Samarth030312/rhino-rmcs-2303-dc-servo-control)** | Speed and position control of a geared encoder motor through a Modbus servo drive from an Arduino. 201 recorded runs over four days; the identified model predicts runs it never saw to about 5 %, and a textbook PI design that limit-cycles on the rig is predicted by it. |
| **[arduino-temperature-control-lab](https://github.com/Samarth030312/arduino-temperature-control-lab)** | A bulb heater, a DHT sensor and a solid-state relay, with the firmware's own safety behaviour — over-temperature cut-off, sensor-failure stop, host watchdog — tested against an emulated plant. |
| **[arduino-water-level-control-lab](https://github.com/Samarth030312/arduino-water-level-control-lab)** | A pumped tank with an ultrasonic level sensor: echo rejection, a median filter, a gate on how fast water can physically move, and an overflow latch. |
| **[pneumatic-circuits-openmodelica](https://github.com/Samarth030312/pneumatic-circuits-openmodelica)** | Pneumatic circuits from first principles in OpenModelica — a component library, animated circuits, eight lessons, and a Python twin that cross-checks the Modelica results. |

## Robotics and simulation

| | |
|---|---|
| **[rigid-body-simulator](https://github.com/Samarth030312/rigid-body-simulator)** | Three-dimensional rigid-body dynamics in MATLAB: a tumbling die whose face is read from the simulated orientation rather than chosen, a 3R manipulator with recursive Newton–Euler dynamics, and a four-bar linkage solved through its loop-closure constraint. An interactive lab app and 115 tests. |

## Teaching and tooling

| | |
|---|---|
| **csc210-csc530-assessment** *(private)* | A self-hosted coding-quiz platform — Moodle, CodeRunner and Jobe in Docker — for running programming assessments at course scale. |

---

## How I work

- **The physics is written down before the code is.** Frames, rotation order, sign
  conventions and units are fixed in a document and then frozen; changing one is a recorded
  decision with its own tests, because a silent change of convention is the hardest bug to
  find.
- **A claim without a number is not a claim.** Energy conserved to 9×10⁻⁶ J, a loop closing
  to 8×10⁻¹⁶ m, a model predicting unseen runs to 5 % — the repositories say which, measured
  how, and over how many runs.
- **The failures stay in.** A servo drive that ran a motor backwards at full voltage twelve
  times out of twelve is documented, together with the firmware change that made it zero out
  of twenty-nine.
- **It has to run on someone else's computer.** One entry point, cross-platform CI, pinned
  toolchains, and installers that fetch what they need rather than vendoring it.

**Tools:** MATLAB and Simulink · C and C++ on STM32 and Arduino · Python · Modelica ·
Docker · Git and GitHub Actions
