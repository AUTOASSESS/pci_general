# pci_general
Interface between gbplanner and controller

`camera_pitch_tracking_enabled` defaults to `true` for actuated-camera robots.
Set it to `false` for fixed-camera inspection: PCI then tracks position and yaw
without waiting for `/cam_pitch` or publishing camera-pitch commands. Select
GBPlanner's `basic_inspection_viewpoints` for inspection without pitch sweeps.

Agentic TargetReach optionally preserves a terminal yaw. When
`/agentic_mission/target_yaw_enabled` is true for a TargetReach path, PCI requires
the final heading within `path_end_yaw_thr` radians (default 0.4), using wrapped
angular distance. Position-only TargetReach and other paths retain their existing
heading progression. The same waypoint tracker reports path completion.
