# SIP-INVESTMENT-CALCULATOR

[readme_md.md](https://github.com/user-attachments/files/34309489/readme_md.md)
# SIP Investment Calculator Pro

A simple, fast, and cross-platform command-line tool written in C to calculate the future value of a Systematic Investment Plan (SIP). 

This calculator features a unique **two-phase financial model** that accounts for both your active monthly investment period and an optional passive growth (hold) period, letting you see the full power of long-term compounding.

---

## Features

- **Two-Phase Compounding Model:**
  - **Phase 1 (Accumulation):** Calculates growth with regular monthly contributions.
  - **Phase 2 (Passive Growth):** Simulates compounding growth after contributions stop.
- **Cross-Platform Interface:** Supports terminal screen clearing on both Windows (`cls`) and Linux/macOS (`clear`).
- **Input Validation:** Gracefully handles invalid non-numeric inputs.
- **Lightweight & Portable:** Written in standard C with no external dependencies.

---

## How It Works

1. **Monthly Rate Calculation:**  
   $$\text{Monthly Rate} = \frac{\text{Annual Interest Rate}}{100 \times 12}$$

2. **Phase 1 (Active Contributions):**  
   Every month, your monthly contribution is added to the total corpus, and interest is applied:
   $$\text{Corpus}_{\text{new}} = (\text{Corpus}_{\text{old}} + \text{Monthly Amount}) \times (1 + \text{Monthly Rate})$$

3. **Phase 2 (Hold Period):**  
   If your total hold duration exceeds your investment duration, the corpus continues to compound without any new contributions:
   $$\text{Corpus}_{\text{new}} = \text{Corpus}_{\text{old}} \times (1 + \text{Monthly Rate})$$

---

## Usage Example

```text
==========================================
        INVESTMENT CALCULATOR PRO          
==========================================
 Monthly Investment : 500
 Annual Interest Rate: 12
 Investment Duration : 10
 Total Hold Period   : 15

--- INVESTMENT SUMMARY ---
Monthly Contribution: 500.00
Annual Rate         : 12.00%
Investment Period   : 10 years
Total Duration      : 15 years
--------------------------
FINAL AMOUNT        : 206584.28
--------------------------
```

---

## Getting Started

### Prerequisites
- A standard C compiler installed (e.g., `gcc`, `clang`, or MSVC).

### Compilation & Execution

#### Linux / macOS:
```bash
gcc -o sip_calculator sip_calculator.c
./sip_calculator
```

#### Windows:
```cmd
gcc -o sip_calculator.exe sip_calculator.c
sip_calculator.exe
```

---

## License

This project is free and open-source software under the [MIT License](LICENSE).
