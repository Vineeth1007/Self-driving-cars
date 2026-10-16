# Self-Driving Car Engineer Nanodegree - Project Solutions

Thirteen worked solutions covering perception, deep learning, sensor fusion, localization, control and planning for an autonomous car, collected from Udacity's Self-Driving Car Engineer Nanodegree (nd013).

![Python](https://img.shields.io/badge/Python-3-3776AB?logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-11-00599C?logo=cplusplus&logoColor=white)
![CMake](https://img.shields.io/badge/build-CMake-064F8C?logo=cmake&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-1.x-FF6F00?logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-1.x-D00000?logo=keras&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-computer%20vision-5C3EE8?logo=opencv&logoColor=white)

> **Provenance.** The code in this repository was written by others. It is a copy of the solutions published at [github.com/ndrplz/self-driving-car](https://github.com/ndrplz/self-driving-car) for the Udacity nanodegree projects, and projects 6-11 are built on Udacity starter code. See [Credits](#credits) before reusing anything. The source files were not modified when this repository was reorganised; only folders, documentation and file locations changed.

## Overview

The nanodegree walks through the main building blocks of a self-driving car stack. This repository keeps one folder per project, in course order:

- **Perception with classical computer vision** (projects 1, 4): finding lane lines and measuring lane curvature from a dashboard camera.
- **Deep learning** (projects 2, 3, 5, 12, 13): classifying traffic signs, cloning human steering behaviour, detecting vehicles, segmenting the road and classifying traffic lights.
- **Sensor fusion and localization** (projects 6, 7, 8): tracking a moving object with lidar and radar using Kalman filters, and localizing a vehicle on a map with a particle filter.
- **Control and planning** (projects 9, 10, 11): PID and model predictive control of steering, and a highway path planner. These talk to the Udacity simulator over WebSockets.

Every project folder has its own README with the goal, data requirements, approach, how to run it and its limitations.

## Contents

| # | Project | What it does | Key techniques | Language |
|---|---|---|---|---|
| 01 | [Lane finding (basic)](01-lane-finding-basic/) | Detects the left and right lane lines in road images and video | Grayscale, Gaussian blur, Canny edges, probabilistic Hough transform, region mask, temporal smoothing | Python (OpenCV) |
| 02 | [Traffic sign classifier](02-traffic-sign-classifier/) | Classifies German traffic signs into 43 classes | YUV luminance + histogram equalization, data augmentation, two-stage CNN with multi-scale features, dropout | Python (TensorFlow, Jupyter) |
| 03 | [Behavioral cloning](03-behavioral-cloning/) | Predicts steering angle from camera frames to drive in the Udacity simulator | NVIDIA-style CNN, side-camera and flip augmentation, steering-bias balancing, ELU and dropout | Python (Keras) |
| 04 | [Advanced lane finding](04-advanced-lane-finding/) | Finds lane boundaries, curvature and vehicle offset in video | Camera calibration, colour and gradient thresholds, perspective warp, sliding-window search, polynomial fit | Python (OpenCV) |
| 05 | [Vehicle detection](05-vehicle-detection/) | Detects cars in highway video | HOG + colour features + linear SVM with heat-map filtering; pretrained SSD300 detector | Python (scikit-learn, Keras) |
| 06 | [Extended Kalman filter](06-extended-kalman-filter/) | Tracks a bicycle from simulated lidar and radar measurements | Extended Kalman filter, Jacobian linearisation, sensor fusion | C++ (Eigen) |
| 07 | [Unscented Kalman filter](07-unscented-kalman-filter/) | Tracks a moving object with a nonlinear motion model | Unscented Kalman filter, sigma points, CTRV model, NIS | C++ (Eigen) |
| 08 | [Kidnapped vehicle](08-kidnapped-vehicle/) | Localizes a vehicle on a landmark map from noisy GPS, controls and observations | 2D particle filter, motion model, nearest-neighbour association, Gaussian weighting, resampling | C++ (uWebSockets) |
| 09 | [PID control](09-pid-control/) | Steers the simulated car from the cross-track error | PID controller, manual gain tuning | C++ (uWebSockets) |
| 10 | [MPC control](10-mpc-control/) | Computes steering and throttle by optimizing a short future trajectory, with 100 ms latency | Kinematic bicycle model, polynomial reference fit, CppAD + Ipopt, latency compensation | C++ (CppAD, Ipopt) |
| 11 | [Path planning](11-path-planning/) | Drives a simulated highway loop among other traffic, changing lanes when blocked | Frenet coordinates, spline trajectory generation, simple lane-change state logic | C++ (uWebSockets) |
| 12 | [Road segmentation](12-road-segmentation/) | Labels road pixels in images | Fully convolutional network with VGG16 encoder and skip connections, augmentation | Python (TensorFlow) |
| 13 | [Capstone: traffic light classifier](13-capstone-traffic-light-classifier/) | Classifies the state of a traffic light (none, red, yellow, green) from a camera frame | Small CNN, simulator and real-world frames | Python (TensorFlow) |

### Verified results

Only numbers that can be traced to a file in this repository or reproduced from the committed code are listed here. See each project README for context and caveats.

| Project | Result | Source |
|---|---|---|
| 02 Traffic sign classifier | 0.953 accuracy on the 12,630-image test set | Output of cell 26 in [`traffic-sign-classifier.ipynb`](02-traffic-sign-classifier/traffic-sign-classifier.ipynb) |
| 03 Behavioral cloning | Validation loss (MSE) 0.0157 after the last recorded epoch (epoch index 16) | [`logs/history.csv`](03-behavioral-cloning/logs/history.csv) |
| 04 Advanced lane finding | RMS re-projection error of 1.19 px for the cached camera calibration | First element of [`camera_cal/calibration_data.pickle`](04-advanced-lane-finding/camera_cal/calibration_data.pickle) |
| 06 Extended Kalman filter | Position RMSE 0.097 / 0.085 on the bundled synthetic data set | Reproduced by building and running the committed code (see the project README) |
| 07 Unscented Kalman filter | Position RMSE 0.060 / 0.086 on the bundled synthetic data set | Reproduced by building and running the committed code (see the project README) |

## Tech stack

- **Python projects (01-05, 12, 13):** OpenCV, NumPy, SciPy, scikit-learn, scikit-image, Matplotlib, MoviePy, TensorFlow 1.x, Keras 1.x, Jupyter; Flask, python-socketio and eventlet for the simulator bridge in project 03.
- **C++ projects (06-11):** C++11, CMake, Eigen (vendored), nlohmann/json (vendored), uWebSockets, and CppAD + Ipopt for project 10.
- **Simulation:** the [Udacity Self-Driving Car simulator](https://github.com/udacity/self-driving-car-sim/releases) for projects 03 and 08-11.

## How to build and run

Every project is self-contained. Open a terminal **inside the project folder**: the scripts read data with paths relative to the working directory.

### Python projects

1. Create a virtual environment and install the project's `requirements.txt`. The code was written in 2017 against old releases (for example TensorFlow with `tf.contrib`, Keras 1.x `Convolution2D(border_mode=...)`, `scipy.misc.imread`), so use a matching legacy environment rather than current library versions. The notebook in project 02 records Python 3.5.2.
2. Obtain the data described in the project README. Data sets, videos and trained weights are mostly **not committed**.
3. Run the entry point named in the project README, for example `python main.py` or `jupyter notebook`.

### C++ projects (06-11)

Requirements: `cmake >= 3.5`, `make >= 4.1`, `gcc/g++ >= 5.4`. Projects 08-11 also need uWebSockets and the Udacity simulator; they ship `install-ubuntu.sh` and `install-mac.sh` that build uWebSockets at commit `e94b6e1` (in project 11 the checkout line of `install-ubuntu.sh` is commented out). Project 10 additionally needs Ipopt and CppAD.

```bash
cd <project-folder>
mkdir build && cd build
cmake .. && make
```

The executable name differs per project (`ExtendedKF`, `UnscentedKF`, `particle_filter`, `pid`, `mpc`, `path_planning`). Projects 06 and 07 read a data file and need no simulator. Keep `data/` next to `CMakeLists.txt`: the executables read `../data/...` relative to `build/`.

## Repository structure

```text
.
├── README.md                                  # this index
├── .gitignore
├── 01-lane-finding-basic/                     # Python, OpenCV
├── 02-traffic-sign-classifier/                # Jupyter notebook, TensorFlow
├── 03-behavioral-cloning/                     # Keras, simulator client
├── 04-advanced-lane-finding/                  # Python, OpenCV
├── 05-vehicle-detection/                      # HOG + SVM and SSD
├── 06-extended-kalman-filter/                 # C++/CMake, vendored Eigen 3.2.10
├── 07-unscented-kalman-filter/                # C++/CMake, vendored Eigen 3.2.10
├── 08-kidnapped-vehicle/                      # C++/CMake, particle filter
├── 09-pid-control/                            # C++/CMake, PID
├── 10-mpc-control/                            # C++/CMake, MPC (vendored Eigen 3.3.3)
├── 11-path-planning/                          # C++/CMake, highway planner
├── 12-road-segmentation/                      # Python, TensorFlow FCN
└── 13-capstone-traffic-light-classifier/      # Python, TensorFlow
```

Each folder contains its own `README.md`, source files, and (where applicable) `data/`, `img/` and `docs/` folders.

## Limitations and known issues

- **Data and weights are not included.** Image sets, videos and trained model weights are not committed (for example the project 03 frames and `pretrained/model.hdf5`, the KITTI road images, the vehicle/non-vehicle sets). Each project README lists what is missing and where the code expects it.
- **Legacy dependencies.** The code targets 2017-era TensorFlow, Keras, SciPy and Eigen releases and has not been ported.
- **Machine-specific paths.** Some scripts contain absolute or home-relative paths from the original author's computer (projects 05 and 12). They must be edited before running; the project READMEs name the exact lines.
- **Repository size.** The demo GIFs (about 60 MB) and vendored Eigen copies (about 3,800 files) are stored as regular git objects, so a full clone is on the order of 70 MB.

## Credits

- **Udacity** - the [Self-Driving Car Engineer Nanodegree](https://www.udacity.com/course/self-driving-car-engineer-nanodegree--nd013) curriculum, project specifications, the simulator and the starter code and scaffolding used in projects 6-11 (CMake files, uWebSockets install scripts, helper headers such as those by Tiffany Huang and `mufferm` in project 8, and the starter README text).
- **[ndrplz](https://github.com/ndrplz)** - author of the upstream repository [ndrplz/self-driving-car](https://github.com/ndrplz/self-driving-car), from which the project solutions, write-ups and demo media in this repository are taken. The upstream commit metadata names Andrea Palazzi as the author. Upstream commit inspected: `2bdcc7c`.
- **Third-party components included in the source tree:**
  - [Eigen](https://eigen.tuxfamily.org) 3.2.10 (projects 6, 7) and 3.3.3 (projects 10, 11), MPL 2.0.
  - [nlohmann/json](https://github.com/nlohmann/json) 2.1.1, MIT (projects 8-11).
  - `spline.h` by Tino Kluge, GNU GPL v2 or later (project 11).
  - The SSD network port from [rykov8/ssd_keras](https://github.com/rykov8/ssd_keras) (project 5).
- **Papers and data sets referenced by the projects:** NVIDIA, "End to End Learning for Self-Driving Cars" (project 3); Sermanet and LeCun, traffic sign classification with multi-scale CNNs (project 2); Liu et al., SSD (project 5); Long et al., fully convolutional networks (project 12); the German Traffic Sign Recognition Benchmark (project 2); the KITTI road benchmark (project 12).

## License

No license file is included in this repository, and the upstream repository contains none at the commit inspected. All rights are reserved by the respective authors. Third-party components keep their own licences, listed above.
