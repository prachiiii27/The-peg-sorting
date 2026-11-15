# Public demo — checklist

## Day before
- [ ] `python3 -m pytest -q tests` passes (38 tests)
- [ ] At least 3 full autonomous runs logged; `python3 scripts/evaluate_timing.py --last 3`
- [ ] Teleop practised (fallback): one full sort under 3 minutes
- [ ] Laptop charged, U2D2 + power hub, USB cables, RealSense cable, printed ArUco marker, tape measure

## Setup at the venue (~15 min)
1. Place the robot, the board strip (sockets ≤ 20.5 cm from the base, ideally 17–19 cm) and the camera.
2. Terminal A: `ros2 launch open_manipulator_x_bringup hardware.launch.py` — joints stiff, no `Fail` lines
   (if `FastSyncRead Rx Fail`: set the USB latency timer to 1, see README §1).
3. Terminal B: `ros2 launch peg_trial cameras.launch.py` — check `ros2 topic hz /cam1/camera/color/image_raw`.
4. Camera or board moved? Re-calibrate (README §4) and check one peg at a measured spot.
5. Lights different? `python3 scripts/save_frames.py` + `python3 scripts/tune_hsv.py --image data/cam1_color.png`.
6. `python3 scripts/view_camera.py` — all 4 sockets outlined in cyan (reachable), pegs outlined.
7. Terminal D: `ros2 run peg_trial teleop_keyboard` — press `h`, test `o`/`c`, keep it open for **SPACE** (e-stop).
8. Board empty → `./launch/run_autonomy.sh dry_run`, put one peg down, check the plan in the log, Ctrl+C.

## Live run
1. Announce: "Fully autonomous, RGB-D vision, no human input except placing the pegs one by one."
   Show the debug image (`rqt_image_view /peg_trial/debug/cam1`).
2. Board empty → `./launch/run_autonomy.sh`; wait for `All 4 sockets detected` and `waiting for next peg`.
3. Place peg 1 upright, hand away → robot picks, inserts, verifies, goes home. Repeat for pegs 2–4.
4. Hand near the power switch, teleop terminal ready for SPACE.
5. Show the evaluation table printed at the end.
6. If autonomy fails: SPACE, then switch to `./launch/run_teleop.sh` and finish with the keyboard.

## Talking points (30 s)
HSV + morphology for colour · depth → 3-D top face → bird's-eye shape features · ArUco extrinsic calibration ·
closed-form IK for the 4-DOF OMX · collision model of gripper + carried peg vs placed pegs · vertical approach
with settle delay · fixed carry / hover / release heights · camera verification + retry · logged success
rate and timing.
