# <p align="center"> **Autonomous Driving Small-Scale Cars** </p> 

<p align="center">
  <a href="https://ieeexplore.ieee.org/document/11034663">
    <img src="https://img.shields.io/badge/IEEE%20Xplore-10.1109%2F3572394-blue" alt="IEEE Xplore">
  </a>
  <a href="https://arxiv.org/abs/2404.06229">
    <img src="https://img.shields.io/badge/arXiv-2404.06229-b31b1b?logo=arxiv&logoColor=white" alt="arXiv">
  </a>
</p>


This repository collects and summarizes recent research, toolkits, and hardware approaches for autonomy on small-scale cars (e.g., 1/10–1/5 scale platforms, micro‑UAV‑sized ground vehicles, and robotics education platforms). It covers perception, localization, planning, control, simulation, and representative datasets, with links to code and notable papers. The goal is to provide a practical resource for researchers, students, and hobbyists who want to prototype and evaluate autonomy on physically small vehicles. 

---

## 📝 Citation

If you find this project useful, we'd appreciate a star ⭐ and a citation of our survey.

```bibtex

@article{li2025autonomous,
  author={Li, Dianzhao and Auerbach, Paul and Okhrin, Ostap},
  journal={IEEE Transactions on Intelligent Transportation Systems}, 
  title={Autonomous Driving Small-Scale Cars: A Survey of Recent Development}, 
  year={2025},
  volume={},
  number={},
  pages={1-24},
  keywords={Automobiles;Sensors;Surveys;Hardware;Cameras;Pipelines;Autonomous automobiles;Wheels;Vehicle dynamics;Safety;Small-scale car;autonomous driving;robotics},
  doi={10.1109/TITS.2025.3572394}}

@article{li2024towards,
  title={Towards autonomous driving with small-scale cars: A survey of recent development},
  author={Li, Dianzhao and Auerbach, Paul and Okhrin, Ostap},
  journal={arXiv preprint arXiv:2404.06229},
  year={2024}
}

```

## 📋 Table of Contents



1. [Motivation](#Motivation)
2. [Overview](#Overview)
3. [Hardware](#Hardware)
4. [Software](#Software)
	1. [Workspace setup](#Workspace-for-ROS-package)
	2. [Train](#Training)
		1. [Configuration files](#Configuration-files)
		2. [Start training](#Start-training)
	3. [Evaluation](#Evaluation)
		1. [Evaluation in Gym environment](#Evaluation-in-gym-environment)
		2. [Evaluation in real-world environment](#Evaluation-in-real-world-environment)



## Motivation

* A concise literature survey and annotated bibliography of recent papers and projects.
* A comparison of common small‑scale platforms (hardware, sensors, compute).
* Recommended datasets and simulators for development and benchmarking.
* Example code snippets and pointers to open-source implementations (perception, planning, control).
* Suggested experiment recipes and evaluation metrics for reproducible research.

---

## Overview

1. Clone this repo:

```bash
git clone https://github.com/<your-username>/smallscale-autonomous-cars.git
cd smallscale-autonomous-cars
```

2. Browse `survey/` for the annotated bibliography and `platforms/` for hardware summaries.
3. See `examples/` for runnable demos and setup instructions.

---

## Hardware

```
smallscale-autonomous-cars/
├── README.md
├── survey/                # annotated bibliography, short summaries
├── platforms/             # hardware comparison, BOMs, sensor setups
├── datasets/              # links and notes on datasets and how to use them
├── simulators/            # recommended simulators and setup notes (e.g., Gazebo, Webots, CARLA forks)
├── examples/              # small demos, scripts, and instructions
│   ├── perception/
│   ├── planning/
│   └── control/
├── tools/                 # utilities, conversion scripts, dataset loaders
├── benchmarks/            # evaluation scripts and baseline results
└── CONTRIBUTING.md
```

---

## Software

| **Platforms**      | **Software Programming** | **Simulation Platform** | **Focused Tasks**         | **User Manual** |
|--------------------|-------------------------|------------------------|---------------------------|-----------------|
| ART/ATK            | ROS2                    | [Chrono](https://projectchrono.org/)                 | General                   | ❌              |
| MuSHR              | ROS                     | --                     | General                   | [Link](https://mushr.io/)              |
| Qcar               | ROS, Python, MATLAB     | Gazebo                 | General                   | ❌              |
| Autominy           | ROS                     | Gazebo                 | General                   | [Link](https://autominy.github.io/AutoMiny/)              |
| AutoDRIVE          | ROS                     | [AutoDRIVE Simulator](https://autodrive-ecosystem.github.io/)    | General                   | [Link](https://autodrive-ecosystem.github.io/)              |
| WolfBot            | ROS                     | MATLAB                 | General                   | ❌              |
| HydraOne           | ROS                     | --                     | General                   | [Link](https://weisongshi.org/hydraone/)              |
| Turtlebot3         | ROS                     | [Gazebo](https://emanual.robotis.com/docs/en/platform/turtlebot3/simulation/)                 | General                   | ✔️              |
| RACECAR(MIT)       | ROS                     | [Gazebo](https://github.com/mit-racecar/racecar_gazebo)                 | SLAM, Path Following      | [Link](https://github.com/mit-racecar)              |
| Donkeycar          | Python                  | [Gym-Donkeycar](https://github.com/tawnkramer/gym-donkeycar)      | Lane Keeping, Racing      | [Link](https://docs.donkeycar.com/)              |
| Duckietown         | ROS                     | Gazebo,[Gym-Duckietown](https://github.com/duckietown/gym-duckietown) | Lane Keeping, Obstacle Avoidance | [Link](https://duckietown.com/)      |
| PiRacer            | ROS                     | --                     | Lane Keeping              | [Link](https://www.waveshare.com/wiki/PiRacer_Pro_AI_Kit)              |
| Jetbot             | ROS                     | Gazebo                 | Lane Keeping, Obstacle Avoidance | [Link](https://jetbot.org/master/)      |
| Autonomouscar      | ROS, LabVIEW            | --                     | Lane Keeping, Obstacle Avoidance | ❌      |
| AutoRally          | ROS                     | Gazebo                 | Racing                    | [Link](https://autorally.github.io/)              |
| BARC               | ROS                     | --                     | Racing, Drifting          | ❌              |
| F1TENTH            | ROS                     | Gazebo, [F1TENTH Gym](https://github.com/f1tenth/f1tenth_gym)| Racing                    | [Link]()              |
| JetRacer           | --                      | --                     | Racing                    | [Link]()              |
| DeepRacer          | ROS                     | Gazebo                 | Racing                    | [Link]()              |
| ORCA Racer         | C++                     | --                     | Racing                    | ❌              |
| Epuck              | ROS                     | Enki, [Webots](https://cyberbotics.com/), V-REP, ARGoS | Swarm                | [Link]()              |
| Kilobot            | --                      | V-REP                  | Swarm                     | [Link]()              |
| GRITSBot           | --                      | --                     | Swarm                     | ❌              |
| Pheeno             | Python                  | --                     | Swarm                     | [Link]()              |
| MarXbot            | ROS                     | Gazebo                 | Swarm                     | ❌              |
| LabRAT             | C                       | Player/Stage           | Swarm                     | ❌              |
| CoRoLa             | ROS2                    | Based on LGSVL         | Cooperative Driving       | ❌              |
| µcar               | C++, Matlab             | --                     | Cooperative Driving       | [Link]()              |
| UDSSC MCAV         | ROS                     | SUMO                   | Cooperative Driving       | ❌              |
| Chronos            | ROS                     | --                     | Cooperative Driving       | [Link]()              |
| Go-CHART           | ROS                     | --                     | Cooperative Driving       | ❌              |
| Cambridge Minicar  | Python                  | --                     | Cooperative Driving       | [Link]()              |

[^1]: Focused tasks are identified based on the main research paper or proposed by us according to the sensor configuration.
[^2]: [Gym-Donkeycar](https://github.com/tawnkramer/gym-donkeycar)
[^3]: [Gym-Duckietown](https://github.com/duckietown/gym-duckietown)
[^4]: [F1TENTH Gym](https://github.com/f1tenth/f1tenth_gym)

## Licence

This repository is provided under the **MIT License** by default — change as needed.

---

## How to cite

If you use this repository in a paper or project, please cite it as:

```
@misc{smallscale-autonomous-cars,
  title={smallscale-autonomous-cars: Survey of recent developments},
  author={<Your Name or Organization>},
  year={2025},
  howpublished={\url{https://github.com/<your-username>/smallscale-autonomous-cars}}
}
```

---

## Contact

Questions, suggestions, or contributions? Open an issue or reach out via GitHub.

---

---

## What you'll find here

* A concise literature survey and annotated bibliography of recent papers and projects.
* A comparison of common small‑scale platforms (hardware, sensors, compute).
* Recommended datasets and simulators for development and benchmarking.
* Example code snippets and pointers to open-source implementations (perception, planning, control).
* Suggested experiment recipes and evaluation metrics for reproducible research.

---

## Quick start

1. Clone this repo:

```bash
git clone https://github.com/<your-username>/smallscale-autonomous-cars.git
cd smallscale-autonomous-cars
```

2. Browse `survey/` for the annotated bibliography and `platforms/` for hardware summaries.
3. See `examples/` for runnable demos and setup instructions.

---

## Suggested folder structure

```
smallscale-autonomous-cars/
├── README.md
├── survey/                # annotated bibliography, short summaries
├── platforms/             # hardware comparison, BOMs, sensor setups
├── datasets/              # links and notes on datasets and how to use them
├── simulators/            # recommended simulators and setup notes (e.g., Gazebo, Webots, CARLA forks)
├── examples/              # small demos, scripts, and instructions
│   ├── perception/
│   ├── planning/
│   └── control/
├── tools/                 # utilities, conversion scripts, dataset loaders
├── benchmarks/            # evaluation scripts and baseline results
└── CONTRIBUTING.md
```

---

## How to *contribute*

Contributions welcome! Please open an issue to propose additions or corrections, and submit pull requests for:

* New papers or projects to add to the survey.
* Corrections to platform specs or dataset links.
* Small runnable examples or reproducible benchmarks.

If you're adding code, include a short README in the example folder that explains dependencies and how to run it.

---

## Licence

This repository is provided under the **MIT License** by default — change as needed.

---

## How to cite

If you use this repository in a paper or project, please cite it as:

```
@misc{smallscale-autonomous-cars,
  title={smallscale-autonomous-cars: Survey of recent developments},
  author={<Your Name or Organization>},
  year={2025},
  howpublished={\url{https://github.com/<your-username>/smallscale-autonomous-cars}}
}
```

---

## Contact

Questions, suggestions, or contributions? Open an issue or reach out via GitHub.

---

---

## What you'll find here

* A concise literature survey and annotated bibliography of recent papers and projects.
* A comparison of common small‑scale platforms (hardware, sensors, compute).
* Recommended datasets and simulators for development and benchmarking.
* Example code snippets and pointers to open-source implementations (perception, planning, control).
* Suggested experiment recipes and evaluation metrics for reproducible research.

---

## Quick start

1. Clone this repo:

```bash
git clone https://github.com/<your-username>/smallscale-autonomous-cars.git
cd smallscale-autonomous-cars
```

2. Browse `survey/` for the annotated bibliography and `platforms/` for hardware summaries.
3. See `examples/` for runnable demos and setup instructions.

---

## Suggested folder structure

```
smallscale-autonomous-cars/
├── README.md
├── survey/                # annotated bibliography, short summaries
├── platforms/             # hardware comparison, BOMs, sensor setups
├── datasets/              # links and notes on datasets and how to use them
├── simulators/            # recommended simulators and setup notes (e.g., Gazebo, Webots, CARLA forks)
├── examples/              # small demos, scripts, and instructions
│   ├── perception/
│   ├── planning/
│   └── control/
├── tools/                 # utilities, conversion scripts, dataset loaders
├── benchmarks/            # evaluation scripts and baseline results
└── CONTRIBUTING.md
```

---

## How to *contribute*

Contributions welcome! Please open an issue to propose additions or corrections, and submit pull requests for:

* New papers or projects to add to the survey.
* Corrections to platform specs or dataset links.
* Small runnable examples or reproducible benchmarks.

If you're adding code, include a short README in the example folder that explains dependencies and how to run it.

---

## Licence

This repository is provided under the **MIT License** by default — change as needed.

---

## How to cite

If you use this repository in a paper or project, please cite it as:

```
@misc{smallscale-autonomous-cars,
  title={smallscale-autonomous-cars: Survey of recent developments},
  author={<Your Name or Organization>},
  year={2025},
  howpublished={\url{https://github.com/<your-username>/smallscale-autonomous-cars}}
}
```

---

## Contact

Questions, suggestions, or contributions? Open an issue or reach out via GitHub.

---


