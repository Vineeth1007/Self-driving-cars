# Data

Driving log used to train the behavioral cloning network. Part of [03 - Behavioral Cloning](../README.md).

| File | Contents |
|---|---|
| `driving_log.csv` | Header plus 8,036 rows with the columns `center, left, right, steering, throttle, brake, speed`. The image columns hold paths such as `IMG/center_2016_12_01_13_30_48_287.jpg`. |

- **Source:** the sample driving data that Udacity provides for the project (recorded in the Udacity simulator).
- **Not committed:** the frames. The code reads them from `data/IMG/` (relative to the project folder), so the images referenced by the CSV must be placed there before training.
