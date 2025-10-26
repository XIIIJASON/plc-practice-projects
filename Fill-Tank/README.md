Fill-Tank Project

Automation for a simple tank filling and discharging process using CODESYS and Factory I/O.
The tank fills and empties through timed control of valves using off-delay timers (TOF).

⚙️ Features

Manual Fill and Discharge buttons

Timed filling and emptying using TOF timers

Separate outputs for filling and discharging valves

Prevents simultaneous fill/discharge operation

🛠️ Tools Used

CODESYS v3.5 — Ladder Logic (IEC 61131-3)

Factory I/O — Tank and valve simulation

🎯 Goal

Practice using timers, button sequencing, and process timing for liquid-level control in a tank system.

📁 Included Files

Fill-Tank.project — CODESYS ladder logic

FillTank.factoryio — Factory I/O scene

🚀 How to Run

Open the scene in Factory I/O and select the CODESYS driver.

Map the I/O for the fill/discharge buttons and valve outputs.

Open the CODESYS project, download it to your runtime or SoftPLC.

Start both programs and use the buttons to fill and discharge the tank.

🧠 Logic Summary
Tag	Type	Description
In_FillButton	BOOL	Starts the fill timer and opens fill valve
In_DischargeButton	BOOL	Starts the discharge timer and opens discharge valve
Ou_Filling	BOOL	Fill state output
Ou_FillValve	BOOL	Output controlling fill valve
Ou_Discharging	BOOL	Discharge state output
Ou_Discharge	BOOL	Output controlling discharge valve
TOF_0	TOF	Controls fill duration (13.5 seconds)
TOF_1	TOF	Controls discharge duration (10.5 seconds)
🧩 Notes

The tank requires multiple presses of the Fill and Discharge buttons to complete a full cycle.

Each button press runs the corresponding TOF timer for its preset duration.

💡 Possible Extension

Add logic to display the active timer value on the digital display labeled “Timer” in Factory I/O.
