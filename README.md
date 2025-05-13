# LLM_Robot_Task_Allocation

Prompt:

You are a mission planner AI responsible for coordinating the actions of autonomous construction robots in a controlled environment. Your objective is to generate an optimized task sequence for a single robot to construct a wall composed of W bricks in width and H bricks in height, by fetching materials from the storage zone and assembling them in the building zone.

The environment includes three zones:

Charging Zone (C)

Storage Zone (S)

Building Zone (B)
Each zone is separated by a fixed distance D = 1 unit. Time advances in discrete units.

Robot Capabilities & Constraints:
Cargo capacity: 3 material units

Build rate: 3 material units per time unit

Battery: Starts at 100%, consumes 25% per movement time unit

Actions allowed (only 1 per time unit):

MOVE_S, MOVE_B, MOVE_C: moves to a target zone

PICK: picks 3 units (instantaneous, no battery use)

BUILD: builds 3 units (instantaneous, no battery use)

CHARGE: recharges to full battery (takes 1 time unit)

IDLE: performs no operation (takes 1 time unit)

Instructions:
Generate a plan as a sequence of steps using this API format:

css
Copy
Edit
{ STEP #, [CURRENT LOCATION], [ACTION], [INTERNAL CARGO], PLACED BRICKS, [REMAINING BATTERY] }
Where:

LOCATION: One of C, S, B, T (Traveling)

ACTION: One of MOVE_S, MOVE_B, MOVE_C, PICK, BUILD, CHARGE, IDLE

INTERNAL CARGO: 0–3 units

PLACED BRICKS: Cumulative total placed

REMAINING BATTERY: % level (0–100)

Scenario to simulate:

Wall size: 3 bricks wide × 3 bricks tall (total = 9 bricks)

1 robot only

Distance between any two zones = 1 unit

Cargo capacity = 3 units

Build rate = 3 units per time unit

Battery use per movement = 25%

Expected Output Format:
Only respond with the ordered steps in the defined API format to complete the wall-building task, managing material movement, battery usage, and final return to the charging station.
