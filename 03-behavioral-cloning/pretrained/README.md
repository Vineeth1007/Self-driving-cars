# Pretrained model

Model description used by `drive.py` to drive in the simulator. Part of [03 - Behavioral Cloning](../README.md).

| File | Contents |
|---|---|
| `model.json` | Keras 1.1.2 architecture of the NVIDIA-style network (the same content as `../logs/model.json`). |

- **Not committed:** the trained weights `model.hdf5`. `drive.py` loads them from `pretrained/model.hdf5`, but `*.hdf5` files are excluded by the repository `.gitignore` and are not present here. Train the model with `model.py` and copy a checkpoint to this name to use `drive.py`. The upstream repository ([ndrplz/self-driving-car](https://github.com/ndrplz/self-driving-car), `project_3_behavioral_cloning/pretrained/model.hdf5`) publishes a copy of about 3 MB, which was not checked here.
