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
