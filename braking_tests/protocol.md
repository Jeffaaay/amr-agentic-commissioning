# Current-AMR braking measurement protocol — approval draft

Status: NOT APPROVED; no hardware test authorized or performed by this task. Measure the existing AMR during an authorized session in Oct 26–Nov 1; do not wait for a 600 kg variant. This document is a review worksheet, not permission to run motion.

## Approval and prerequisites

The site safety owner and qualified operator must fill in and sign: robot identity and deployed firmware/software/build configuration; verified curb/rated/test payload masses and secure load/CoG; approved floor, slope, tires and battery range; isolated exclusion area and stopping reserve; three approved safe speeds; number of repeats per load/speed; precise stop mode; independent emergency-stop operator and inspected stop function; instrumentation calibration and abort/recovery procedure. All entries are currently missing. Do not infer speeds or stopping reserve from unmeasured braking capability. Normal commanded stop and emergency stop must be treated as different test modes with separate approval.

## Measurement design for authorized operator review

Record empty and representative maximum **rated** load at each of three approved speeds. Start with the most conservative approved condition, reviewing each run before progressing. Include an independent measurement of vehicle speed and traveled distance, synchronized command/event capture and calibrated motor/wheel response. Wheel odometry alone cannot establish actual floor stopping distance when slip or scale error is unknown.

Record run/boot/command identity; host stop-command send timestamp; MCU decision and stop-state timestamps; CAN capture when supported; actual physical stop time; speed-versus-time; stopping distance; motor/wheel response; load placement; floor/slope; battery and tire condition; firmware/software/configuration digests; instrument resolution, calibration and timestamp uncertainty. Log any missing samples or dropped events. A command acknowledgement, zero target or wheel-speed threshold alone is not independent proof of physical stop.

Stop the session immediately on uncontrolled behavior, sensor/capture loss, unstable payload, unexpected motion or entry into the exclusion area. The site-approved response and independent emergency stop govern recovery. No uncontrolled fault injection on an operational fleet robot. Codex does not operate equipment, flash firmware or authorize tests.

## Analysis plan after data exist

Retain raw timestamped traces privately. Separate command-to-response delay, braking phase and stationary confirmation. Report each condition and all repeats, stopping distance and speed traces with measurement uncertainty. Estimate a conservative effective deceleration range/lower bound only over validated conditions, including variation and instrument uncertainty; document the estimator and confidence method before examining outcomes. Flag and explain exclusions and slip. Do not fit a universal constant or treat configured ramps as achieved deceleration.

The frozen feasibility approximation `v * (tau_detect + tau_comm + tau_act) + v^2 / (2*a_min) + margin <= d_available` is only one admissibility check. It does not uniquely determine a TPDO timeout, certify a vehicle, or capture every dynamic, stability or surface constraint. Keep 600/1000 kg variant claims conditional on actual vehicles and measurements.

## Outputs and readiness

`platforms/current_amr.yaml`: exists, unknown values null. `braking_tests/summary.csv`: header only, zero runs. Raw traces and speed/distance/uncertainty plots: absent because no measurement exists. Approved procedure, operator, test site, instrumentation and hardware session: outstanding. Raw data must remain private; add only sanitized approved derivatives to research repositories.
