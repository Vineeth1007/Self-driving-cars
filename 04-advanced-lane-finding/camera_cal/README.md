# Camera calibration

Part of [04 - Advanced Lane Finding](../README.md).

| File | Contents |
|---|---|
| `calibration_data.pickle` | Cached result of `cv2.calibrateCamera` (a tuple of the RMS re-projection error, camera matrix, distortion coefficients, and rotation and translation vectors). `calibration_utils.py` loads it when present instead of recomputing the calibration. |

- **Not committed:** the chessboard images `calibration*.jpg` that the calibration is computed from (9 x 6 inner corners). They are only needed to recompute the calibration; place them in this folder if you want to.
