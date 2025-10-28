Queue of Items Project

Automation for a conveyor buffer system using CODESYS and Factory I/O.
The system automatically loads boxes into a buffer area up to a defined limit and then unloads them once full.

⚙️ Features

Entry and buffer conveyor motors

CTUD counter tracks the number of boxes in the buffer

Edge sensors at entry and exit points for position tracking

Automatic transition between loading and unloading states

Adjustable buffer capacity (set to 3 boxes)

🛠️ Tools Used

CODESYS v3.5 — Ladder Logic (IEC 61131-3)

Factory I/O — Conveyor and sensor simulation

🎯 Goal

Practice counting logic, state control, and sequential automation for managing buffered material flow.

📁 Included Files

QueueOfItems.project — CODESYS ladder logic

QueueOfItems.factoryio — Factory I/O scene

🚀 How to Run

Open the scene in Factory I/O and select the CODESYS driver.

Map all I/O for sensors and conveyor motors.

Open the CODESYS project, download it to your runtime or SoftPLC.

Start both programs — boxes will automatically fill the buffer up to 3, then unload once full.

🧠 Logic Summary
Tag	Type	Description
In_AtEntry	BOOL	Detects box at the transition between conveyors and triggers a function to briefly run the buffer motor, ensuring the box is fully transferred into the buffer
Var_AddedBoxInBuffer	BOOL	Increments the CTUD counter after the box has completely entered the buffer
In_AtExit	BOOL	Detects a box leaving the buffer — decrements the counter
CTUD_0	CTUD	Up/down counter tracking the number of boxes currently in the buffer (preset = 3)
Var_BufferFull	BOOL	Indicates the buffer has reached full capacity
Var_BoxesClear	BOOL	Indicates the buffer is empty
Var_EmptyingBuffer	BOOL	Enables unloading sequence
Var_AddingBoxToBuffer	BOOL	Enables loading sequence
Ou_EntryMotor	BOOL	Controls the entry conveyor motor
Ou_BufferMotor	BOOL	Controls the buffer conveyor motor
🧩 Operation Overview

Box Detection: When a box reaches In_AtEntry, it triggers a short buffer motor run to pull the box completely into the buffer.

Counting: Once fully transferred, Var_AddedBoxInBuffer increments the CTUD counter.

Buffer Full: When the count reaches 3, the entry conveyor stops to block further boxes.

Unloading Phase: The buffer conveyor activates and unloads all boxes one by one, decrementing the counter.

Cycle Reset: Once the counter reaches zero (Var_BoxesClear), the system returns to the loading phase.

💡 Possible Extensions

Simplified Control: Rebuild the logic using Set/Reset (SR) coils to streamline the sequence structure while still using the CTUD counter for tracking buffer count.

Realistic Addition: Add logic to stop the entry conveyor when no box is detected at the Item Ready Sensor.

While unnecessary in the simulation, this would improve real-world efficiency by reducing wear and energy use.
