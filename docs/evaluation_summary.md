# Evaluation summary (development logs, 10–12 Nov 2026 — dry runs and real runs mixed)

| run | pegs | success | total time (s) | e-stop |
|---|---|---|---|---|
| 20261110-214740-ee50 | 2 | 0 | 27.17 | 0 |
| 20261110-215259-82b4 | 2 | 2 | 10.28 | 0 |
| 20261110-215639-eb75 | 2 | 2 | 10.28 | 0 |
| 20261110-220240-7a1d | 4 | 3 | 15.42 | 0 |
| 20261110-220644-3ce1 | 4 | 3 | 15.42 | 0 |
| 20261110-225143-ca9d | 4 | 4 | 20.54 | 0 |
| 20261110-225345-0e69 | 4 | 0 | 56.18 | 0 |
| 20261111-165144-3ce0 | 1 | 1 | 10.71 | 0 |
| 20261111-165630-4e03 | 3 | 0 | 40.95 | 1 |
| 20261111-174025-f763 | 4 | 0 | 604.47 | 0 |
| 20261111-180327-51a4 | 0 | 0 | 0.0 | 0 |
| 20261111-194512-adda | 1 | 1 | 9.35 | 0 |
| 20261111-203819-8fe5 | 0 | 0 | 0.0 | 0 |
| 20261111-203846-a916 | 0 | 0 | 0.0 | 0 |
| 20261112-190140-cf4d | 1 | 1 | 23.79 | 0 |

## Overall

- Pegs attempted: 27
- Success rate: 17/27 = 63.0 %
- First-try success (zero-failure bonus): 17/27
- Mean time per successful peg: 6.1 s
- Best full run (all pegs placed): 9.3 s

## Per shape

| shape | success | mean time (s) | mean yaw error (deg) |
|---|---|---|---|
| circle | 4/5 | 5.2 | 0.0 |
| hexagon | 3/6 | 5.1 | 7.9 |
| square | 6/9 | 7.9 | 13.1 |
| triangle | 4/7 | 5.1 | 38.6 |

## Failures

- 20261110-214740-ee50 yellow triangle: dxy=214mm dz=27mm
- 20261110-214740-ee50 red hexagon: dxy=26mm dz=24mm
- 20261110-220240-7a1d yellow triangle: hover pose (0.218,-0.172,0.086) unreachable: target out of reach (r=0.268, z=0.086)
- 20261110-220644-3ce1 red hexagon: pre-grasp pose (0.223,0.132,0.113) unreachable: target out of reach (r=0.249, z=0.113)
- 20261110-225345-0e69 yellow triangle: dxy=150mm dz=20mm
- 20261110-225345-0e69 blue square: pre-grasp pose (0.178,-0.192,0.105) unreachable: target out of reach (r=0.253, z=0.105)
- 20261110-225345-0e69 orange hexagon: pre-grasp pose (0.102,-0.112,0.192) unreachable: target out of reach (r=0.144, z=0.192)
- 20261110-225345-0e69 green circle: pre-grasp pose (0.305,0.037,0.073) unreachable: target out of reach (r=0.295, z=0.073)
- 20261111-165630-4e03 blue square: aborted (e-stop)
- 20261111-174025-f763 blue square: no grasp height is both reachable and collision-free for peg at r=0.127 / socket at r=0.225 — move it, space the pegs out, or raise the robot
