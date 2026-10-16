# Input data

Part of [07 - Unscented Kalman Filter](../README.md).

| File | Lines | Notes |
|---|---|---|
| `obj_pose-laser-radar-synthetic-input.txt` | 500 | Interleaved lidar (`L`) and radar (`R`) measurements with ground truth. Same content as the file in project 06. After `gt_vy` each line has two more ground-truth columns that the program does not read. |

Lidar line: `L meas_px meas_py timestamp gt_px gt_py gt_vx gt_vy`. Radar line: `R meas_rho meas_phi meas_rho_dot timestamp gt_px gt_py gt_vx gt_vy`. Timestamps are in microseconds. The data comes from the Udacity project starter material. Run the program from `build/` and pass `../data/obj_pose-laser-radar-synthetic-input.txt` and an output file name.
