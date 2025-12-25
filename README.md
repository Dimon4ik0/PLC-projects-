# PLC-projects-
some plc projects
---------------------

  Project 1
The pneumatic line (Fig. 13–15) consists of a rotary table with 4 positions (pos1–pos4), 3 cylinders (P1, P2, P3), conveyor D1, and a compressor. At the only loading point at P1 there is an optical sensor OS1 (NC) for detecting the presence of an object on the platform. The end of conveyor D1 is monitored by OS2 (NC).

P1 (loading to pos1) and P2 (processing at pos2) are single-solenoid cylinders (TRUE = extend, FALSE = retract; spring return). P3 at the conveyor has two outputs: P3_to_table (extend toward the table) and P3_to_conveyor (retract toward the conveyor). The outputs P3_to_table and P3_to_conveyor must not be activated at the same time. All cylinder movements are permitted only when COMPRESSOR = TRUE (note: otherwise the movement would not be executed).

The rotary table rotates clockwise via the output TABLE_ROTATE. The position is time-controlled: one quarter turn (90°) takes time T90. Table initialization is done with KS1 (manual contact at P1): hold = rotate, release = TABLE_OK. Removal at pos4 is confirmed by KS2.

Routing according to ID:
On the platform at OS1, before loading, the object_ID is set (e.g. in the watch table). Objects with a lower ID (e.g. up to fifty) are routed to the conveyor via pos3 using P3. Objects with a higher ID (e.g. above fifty) are not removed at pos3 and continue rotating to pos4, where they are removed manually with confirmation by KS2. The exact thresholds can be adjusted; it is important that this decision is tied to the stored object_ID and is carried along with the object.
---------------------------------

  Project 2
