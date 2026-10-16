# Highway map

Part of [11 - Path Planning](../README.md).

| File | Contents |
|---|---|
| `highway_map.csv` | 181 waypoints around the highway loop. Columns (space separated, no header): `x y s dx dy`, i.e. map coordinates, distance along the road in metres, and the unit normal vector pointing outward of the loop. |

The Frenet `s` value runs from 0 to 6945.554 m before wrapping around (the constant `max_s` in `src/main.cpp`). The program reads this file from `../data/highway_map.csv`, so run it from `build/` with `data/` next to `CMakeLists.txt`.
