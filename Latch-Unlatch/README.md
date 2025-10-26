Latch-Unlatch Conveyor Project

Automation for a simple conveyor sequence using CODESYS and Factory I/O.
When a box is detected at Sensor 1, the motor turns on and stays latched.
When the box reaches Sensor 2, the motor turns off, completing one transfer cycle.

⚙️ Features

Two sensors for box detection

Latching and unlatching motor control

Simple seal-in circuit using ladder logic

Simulated conveyor and sensors in Factory I/O

🛠️ Tools Used

CODESYS v3.5 — Ladder Logic (IEC 61131-3)

Factory I/O — Conveyor simulation environment

🎯 Goal

Practice sensor-based control, latching logic, and basic sequencing for a discrete automation process.

📁 Included Files

Latch-Unlatch.project — CODESYS ladder logic

2 - From A to B (Latch Unlatch).factoryio — Factory I/O scene

🚀 How to Run

Open the scene in Factory I/O and select the CODESYS driver.

Map the sensors and motor outputs to the corresponding CODESYS variables.

Open the CODESYS project, download it to your runtime or SoftPLC.

Start both programs and place a box on the conveyor to observe the operation.

🧠 Logic Summary
Tag	Type	Description
In_Sensor1	BOOL	Detects box at entry — latches motor on
In_Sensor2	BOOL	Detects box at exit — unlatches motor
Ou_Motor2	BOOL	Conveyor motor output
