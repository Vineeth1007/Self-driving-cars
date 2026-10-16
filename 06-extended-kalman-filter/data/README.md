# Input data

Lidar and radar measurements with ground truth, read by the `ExtendedKF` executable. Part of [06 - Extended Kalman Filter](../README.md).

| File | Lines | Notes |
|---|---|---|
| `obj_pose-laser-radar-synthetic-input.txt` | 500 | Synthetic data; same content as the file in project 07. Has two extra ground-truth columns that the program does not read. |
| `sample-laser-radar-measurement-data-1.txt` | 1,224 | Sample measurements. |
| `sample-laser-radar-measurement-data-2.txt` | 200 | Sample measurements. |

Lidar line: `L meas_px meas_py timestamp gt_px gt_py gt_vx gt_vy`. Radar line: `R meas_rho meas_phi meas_rho_dot timestamp gt_px gt_py gt_vx gt_vy`. Timestamps are in microseconds. The data comes from the Udacity project starter material. Run the program from `build/` and pass `../data/<file>` as the first argument.
