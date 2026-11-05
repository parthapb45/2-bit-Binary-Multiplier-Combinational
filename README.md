# ⚡ 2-Bit Binary Multiplier – Combinational Circuit Design & Simulator
Design a combinational circuit to multiply two 2-bit binary numbers. Generate partial products using AND gates. Combine partial products using half adders and logic gates.

<p align="center">
  **A Digital Logic Mini Project | Computer Organization**
</p>

<p align="center">
  <a href="https://bit-binary-multiplier.web.app/">
    <img src="https://img.shields.io/badge/LIVE_DEMO-Visit_Simulator-2EA44F?style=for-the-badge&logo=firebase&logoColor=white" alt="Live Demo">
  </a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white">
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white">
  <img src="https://img.shields.io/badge/JavaScript-ES6-F7DF1E?style=flat-square&logo=javascript&logoColor=black">
  <img src="https://img.shields.io/badge/Firebase-Hosting-FFCA28?style=flat-square&logo=firebase&logoColor=black">
  <img src="https://img.shields.io/badge/Python-3-3776AB?style=flat-square&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square">
</p>

---

## 📌 Project Overview

This project presents the design, implementation, and verification of a **2-Bit × 2-Bit Combinational Binary Multiplier** using AND gates and Half Adders.

The circuit multiplies two unsigned 2-bit binary numbers and produces a 4-bit binary output.

Unlike sequential multiplication circuits, the proposed combinational architecture performs multiplication without clock signals, registers, or sequential control logic.

The project includes:

- Mathematical and Boolean formulation.
- Gate-level circuit design.
- Virtual breadboard implementation using Autodesk Tinkercad.
- Interactive web-based circuit simulator.
- Complete 16-row truth table verification.

## 🎯 Project Objectives

1. Understand the architecture of combinational binary multipliers.
2. Generate four partial products using AND gates.
3. Design two Half Adders for partial product addition.
4. Implement the circuit using 74HC08 and 74HC86 ICs.
5. Build an interactive web-based circuit simulator.
6. Verify all 16 possible input combinations.

## ⚙️ Circuit Architecture

The multiplier accepts two 2-bit inputs:

- Multiplicand: A = A1 A0
- Multiplier: B = B1 B0

**Circuit Components:**

| Component | Quantity | Purpose |
|---|---:|---|
| 2-input AND Gates | 6 | Partial products and carry |
| 2-input XOR Gates | 2 | Half Adder sum outputs |
| Half Adders | 2 | Partial product addition |
| Binary Inputs | 4 | A1, A0, B1, B0 |
| Output Bits | 4 | C3, C2, C1, C0 |

### Partial Product Generation

Four AND gates generate the partial products:

\[
P_0=A_0\cdot B_0
\]

\[
P_1=A_1\cdot B_0
\]

\[
P_2=A_0\cdot B_1
\]

\[
P_3=A_1\cdot B_1
\]

### Half Adder Operations

**Half Adder 1 (HA1)**

Inputs: P1, P2

- Sum: C1 = P1 ⊕ P2
- Carry: K1 = P1 · P2

**Half Adder 2 (HA2)**

Inputs: K1, P3

- Sum: C2 = K1 ⊕ P3
- Carry: C3 = K1 · P3

### Final Output Equations

| Output | Boolean Expression |
|---|---|
| C0 | P0 |
| C1 | P1 ⊕ P2 |
| C2 | K1 ⊕ P3 |
| C3 | K1 · P3 |

The final product is:

\[
C=C_3C_2C_1C_0
\]

## 🔌 Hardware Implementation

The circuit was designed and tested using a virtual breadboard in Autodesk Tinkercad Circuits.

**Hardware Components:**

| Component | Specification | Quantity |
|---|---|---:|
| AND Gate IC | 74HC08 / 74LS08 | 2 |
| XOR Gate IC | 74HC86 / 74LS86 | 1 |
| Voltage Regulator | LM7805 | 1 |
| DC Battery | 9V | 1 |
| Slide Switches | SPDT | 4 |
| LEDs | Green LEDs | 4 |
| Resistors | 220 Ω | 4 |
| Breadboard | Solderless | 1 |

The LM7805 regulator provides a regulated 5V supply to the circuit.

Four input switches control the binary inputs, while four LEDs display the final product.

## 💻 Web-Based Circuit Simulator

A custom interactive web application was developed to demonstrate the working principle of the multiplier.

**Simulator Features:**

- Interactive binary input controls.
- Real-time multiplication results.
- Half Adder block-level schematic.
- Gate-level circuit visualization.
- Animated logic signal paths.
- Live partial product calculation.
- Interactive gate inspector.
- Complete 16-row truth table.
- Quick input presets.
- LED-based binary output display.

### Technologies Used

| Technology | Application |
|---|---|
| HTML5 | Webpage structure |
| Tailwind CSS | User interface styling |
| JavaScript (ES6) | Circuit logic and interaction |
| SVG | Circuit visualization |
| Firebase Hosting | Website deployment |
| Python 3 | Schematic generation |
| Matplotlib & Pillow | Diagram preparation |

## 📊 Complete Truth Table

The circuit has four binary input lines, resulting in:

\[
2^4=16\text{ input combinations}
\]

| A1 | A0 | B1 | B0 | Product (C3 C2 C1 C0) | Decimal |
|---:|---:|---:|---:|---|---:|
| 0 | 0 | 0 | 0 | 0000 | 0 |
| 0 | 0 | 0 | 1 | 0000 | 0 |
| 0 | 0 | 1 | 0 | 0000 | 0 |
| 0 | 0 | 1 | 1 | 0000 | 0 |
| 0 | 1 | 0 | 0 | 0000 | 0 |
| 0 | 1 | 0 | 1 | 0001 | 1 |
| 0 | 1 | 1 | 0 | 0010 | 2 |
| 0 | 1 | 1 | 1 | 0011 | 3 |
| 1 | 0 | 0 | 0 | 0000 | 0 |
| 1 | 0 | 0 | 1 | 0010 | 2 |
| 1 | 0 | 1 | 0 | 0100 | 4 |
| 1 | 0 | 1 | 1 | 0110 | 6 |
| 1 | 1 | 0 | 0 | 0000 | 0 |
| 1 | 1 | 0 | 1 | 0011 | 3 |
| 1 | 1 | 1 | 0 | 0110 | 6 |
| 1 | 1 | 1 | 1 | 1001 | 9 |

**Verification Result:** All 16 input combinations were tested, and the outputs matched the theoretical multiplication results.

## 🧪 Key Test Cases

**Test Case 1: 2 × 3**

- A = 10₂
- B = 11₂
- Output = 0110₂
- Decimal Result = 6

**Test Case 2: 3 × 3**

- A = 11₂
- B = 11₂
- Output = 1001₂
- Decimal Result = 9

## 🚀 Live Demo

Try the interactive simulator:

**[Open 2-Bit Binary Multiplier Simulator](https://bit-binary-multiplier.web.app/)**

## 🖥️ Run Locally

1. Clone the repository:

```bash
git clone https://github.com/parthapb45/2-bit-Binary-Multiplier-Combinational.git
```

2. Open the project directory:

```bash
cd 2-bit-Binary-Multiplier-Combinational
```

3. Open `index.html` in your web browser.

No additional installation is required for the standalone HTML simulator.

## 📈 Results and Discussion

The proposed circuit successfully demonstrates 2-bit unsigned binary multiplication using combinational logic.

- All four partial products are generated simultaneously.
- Two Half Adders combine the intermediate results.
- No clock or sequential registers are required.
- The output ranges from 0000₂ to 1001₂.
- All 16 input combinations were verified.

The theoretical worst-case propagation path consists of three logic gate delays.

## 🔮 Future Scope

The project can be extended in several ways:

- Design of 4-bit and 8-bit binary multipliers.
- Implementation of larger multiplier architectures.
- Development of Wallace Tree and Dadda Tree multipliers.
- Support for signed binary multiplication.
- Integration with larger ALU architectures.
- Further improvement of interactive circuit visualization.

## 📚 References

1. M. Morris Mano, *Computer System Architecture*, 3rd Edition, Pearson Education.
2. M. Morris Mano and Michael D. Ciletti, *Digital Design*, 6th Edition, Pearson, 2018.
3. Carl Hamacher et al., *Computer Organization and Embedded Systems*, 6th Edition, McGraw-Hill.
4. William Stallings, *Computer Organization and Architecture: Designing for Performance*, 11th Edition, Pearson.
5. Texas Instruments, SN74HC08 and SN74HC86 Datasheets.

## 👥 Project Team

**Department of Computer Science & Engineering**

Budge Budge Institute of Technology (BBIT)

| Team Member | Roll Number |
|---|---|
| Partha Pratim Biswas | 27600125053 |
| Naz Yasmin | 27600125054 |
| Soumyojit Halder | 27600125055 |
| Bristi Ghosh | 27600125056 |
| Riya Khamaru | 27600125057 |

**Project Guide:** Dr. Raj Kumar Paul

**Head of Department:** Prof. Sagar Chakraborty

**Semester:** 3rd

**Academic Year:** 2026–2027

## 📄 License

This project is distributed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

<p align="center">
  **Developed as a Computer Organization Mini Project**
</p>

<p align="center">
  Made with dedication by the CSE Project Team.
</p>
