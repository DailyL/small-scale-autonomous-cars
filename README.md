# small-scale-autonomous-cars
# smallscale-autonomous-cars

**Survey of recent developments in autonomous driving for small‑scale cars**

This repository collects and summarizes recent research, toolkits, datasets, and hardware approaches for autonomy on small-scale cars (e.g., 1/10–1/5 scale platforms, micro‑UAV‑sized ground vehicles, and robotics education platforms). It covers perception, localization, planning, control, simulation, and representative datasets, with links to code and notable papers. The goal is to provide a single, practical resource for researchers, students, and hobbyists who want to prototype and evaluate autonomy on physically small vehicles.

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

## How to contribute

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

*Want a shortened README (1 paragraph) for the repo description or a more detailed literature review section? Tell me which and I’ll update the canvas.*
