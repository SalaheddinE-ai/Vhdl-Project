# RS Flip-Flop in VHDL

## Description

This exercise presents the implementation of an RS Flip-Flop using the VHDL language.
The objective is to understand the basic behavior of sequential digital circuits and memory elements.

The RS Flip-Flop has two inputs:

* **S (Set)**
* **R (Reset)**

and two outputs:

* **Q**
* **Q' (inverse of Q)**

The circuit changes its state according to the values of the inputs S and R.

---

## Project Content

This project contains:

* The VHDL **Entity** of the RS Flip-Flop
* The VHDL **Architecture**
* The **Truth Table**
* The **Timing Diagram** obtained after simulation

---

## Results

### 1. Entity of RS Flip-Flop

![Entity](Exam2024/Ex1/Ex1_Exam2024.png)

---

### 2. Architecture and Truth Table

![Architecture](Exam2024/Ex1/SimEx1Exam2024.png)

---

### 3. Timing Diagram

![Timing Diagram](Exam2024/Ex1/SimulationEx1Exam2024.png)

---

## Tools Used

* VHDL
* ModelSim / Vivado / Quartus
* Digital Logic Simulation

---

## Objective

The main goal of this exercise is to learn:

* Basic VHDL syntax
* Sequential logic design
* RS Flip-Flop operation
* Simulation and waveform analysis

# 3-Bit Counter in VHDL

## Description

This exercise presents the implementation of a 3-bit binary counter using the VHDL language.

The counter increments its value on each rising edge of the clock signal (`clk`).
A reset signal is also used to initialize the counter value to `000`.

The output `q` represents the current binary value of the counter.

---

## VHDL Code

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.STD_LOGIC_ARITH.ALL;
use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity Compteur3Bit is
    Port (
        clk   : in STD_LOGIC;
        reset : in STD_LOGIC;
        q     : out STD_LOGIC_VECTOR (2 downto 0)
    );
end Compteur3Bit;

architecture Behavioral of Compteur3Bit is
    signal count : STD_LOGIC_VECTOR (2 downto 0) := "000";
begin
    process (clk, reset)
    begin
        if reset = '1' then
            count <= "000";
        elsif rising_edge(clk) then
            count <= count + 1;
        end if;
    end process;

    q <= count;
end Behavioral;
```

---

## Project Content

This project contains:

* The VHDL **Entity**
* The VHDL **Architecture**
* The simulation **Waveform**
* The counter execution results

---

## Results

### 1. Entity of 3-Bit Counter

![Entity](Exam2024/Ex2/Ex2_Exam2024.png)

---

### 2. Architecture of 3-Bit Counter

![Architecture](Exam2024/Ex2/SimEx2Exam2024.png)

---

### 3. Timing Diagram / Simulation Result

![Timing Diagram](Exam2024/Ex2/SimulationEx2Exam2024.png)

---

## Counter Operation

The counter sequence is:

```text
000 → 001 → 010 → 011 → 100 → 101 → 110 → 111
```

After reaching `111`, the counter returns to `000`.

---

## Tools Used

* VHDL
* ModelSim / Vivado / Quartus
* Digital Logic Simulation

---

## Objective

The objective of this exercise is to learn:

* Sequential circuit design
* Clock signal handling
* Binary counting in VHDL
* Simulation and timing analysis

# Quiz Game Circuit in VHDL

## Description

This exercise presents the design of a digital circuit for a quiz game using the VHDL language.

The system contains:

* 3 participants
* 3 push buttons
* 3 lamps
* 1 reset button controlled by the host

Each participant can press their button to answer the question.
The first participant who presses their button activates their corresponding lamp.

Once a participant wins:

* the selected lamp remains ON
* all other buttons become disabled
* no other participant can answer

The system returns to the initial state only when the host presses the `reset` button.

---

## System Operation

### Initial State

* All lamps are OFF
* All buttons are active

### During the Game

* The first pressed button is detected
* The corresponding lamp turns ON
* Other buttons are ignored

### Reset State

* All lamps turn OFF
* The system becomes ready for a new question

---

## Project Content

This project contains:

* The VHDL **Entity**
* The VHDL **Architecture**
* The circuit **Simulation**
* The **Timing Diagram**
* The game execution results

---

## Inputs and Outputs

### Inputs

* `btn1` : Button of participant 1
* `btn2` : Button of participant 2
* `btn3` : Button of participant 3
* `reset` : Reset button

### Outputs

* `lamp1` : Lamp of participant 1
* `lamp2` : Lamp of participant 2
* `lamp3` : Lamp of participant 3

---

## Results

### 1. Entity of Quiz Game Circuit

![Entity](Exam2024/Ex3/Ex3_Exam2024.png)

---

### 2. Architecture of the Circuit

![Architecture](Exam2024/Ex3/SimEx3Exam2024.png)

---

### 3. Timing Diagram / Simulation Result

![Timing Diagram](Exam2024/Ex3/SimulationEx3exam2024.png)

---

## Example Scenario

```text id="64nndt"
- Participant 2 presses first
- Lamp 2 turns ON
- Buttons 1 and 3 are disabled
- The system waits for reset
- After reset, all lamps turn OFF
```

---

## Tools Used

* VHDL
* ModelSim / Vivado / Quartus
* Digital Logic Simulation

---

## Objective

The objective of this exercise is to learn:

* Event detection in digital systems
* Sequential logic design
* Priority management
* State control using reset signals
* Simulation and waveform analysis
