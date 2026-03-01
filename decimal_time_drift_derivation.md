# Step-by-Step Numerical Derivation: Decimal Time & Yearly Drift Correction

---

## 1️⃣ Physical Constants

| Constant | Value |
|----------|-------|
| Mean tropical year | **365.2425** solar days |
| One solar day | 1 rotation (exact reference) |
| SI seconds per solar day | **86 400** (exact, by definition) |

---

## 2️⃣ Decimal Time System Definition

**Structure:**
- 1 day = 10 decimal hours
- 1 decimal hour = 100 decimal minutes
- 1 decimal minute = 100 decimal seconds

**Derivation of decimal second in terms of day:**

\[
1 \text{ decimal second} = \frac{1}{10 \times 100 \times 100} \text{ day} = \frac{1}{100{,}000} \text{ day}
\]

**Conversion to SI seconds:**

One solar day = 86 400 SI seconds (exact).

\[
1 \text{ decimal second} = \frac{1}{100{,}000} \text{ day} = \frac{86{,}400}{100{,}000} \text{ SI seconds}
\]

\[
\boxed{1 \text{ decimal second} = 0.864 \text{ SI seconds} \quad \text{(exact)}}
\]

---

## 3️⃣ Yearly Drift

A calendar year of 365 days is too short by:

\[
\Delta_{\text{year}} = 365.2425 - 365 = 0.2425 \text{ days per year}
\]

### Convert 0.2425 days to decimal time units

**Decimal hours:**
\[
0.2425 \text{ days} \times \frac{10 \text{ decimal hours}}{1 \text{ day}} = \boxed{2.425 \text{ decimal hours}}
\]

**Decimal minutes:**
\[
0.2425 \text{ days} \times \frac{10 \times 100 \text{ decimal minutes}}{1 \text{ day}} = 0.2425 \times 1000 = \boxed{242.5 \text{ decimal minutes}}
\]

**Decimal seconds:**
\[
0.2425 \text{ days} \times \frac{100{,}000 \text{ decimal seconds}}{1 \text{ day}} = 0.2425 \times 100{,}000 = \boxed{24{,}250 \text{ decimal seconds}}
\]

**SI seconds:**
\[
0.2425 \text{ days} \times \frac{86{,}400 \text{ SI seconds}}{1 \text{ day}} = 0.2425 \times 86{,}400 = \boxed{20{,}952 \text{ SI seconds}}
\]

---

## 4️⃣ Correction Per Interval

We must add a total of **0.2425 days** (or equivalently **20 952 SI seconds** or **24 250 decimal seconds**) per year.

---

### Case A — Correct every decimal second

**Intervals per year:**  
365 days × 100 000 decimal seconds/day = **36 500 000** decimal seconds per year

**Correction per decimal second (in decimal seconds):**
\[
\frac{24{,}250 \text{ decimal seconds}}{36{,}500{,}000} = \frac{2425}{3{,}650{,}000} = 0.0006643835616438356\ldots
\]

**Correction per decimal second (in SI seconds):**
\[
\frac{20{,}952 \text{ SI seconds}}{36{,}500{,}000} = \frac{20952}{36500000} = 0.000573972602739726\ldots \text{ SI seconds}
\]

**In SI nanoseconds:**
\[
0.000573972602739726 \times 10^9 = 573972.602739726\ldots \text{ ns}
\]

\[
\boxed{\approx 573{,}973 \text{ SI nanoseconds per decimal second}}
\]

---

### Case B — Correct every decimal minute

**Intervals per year:**  
365 days × 10 × 100 = 365 × 1 000 = **365 000** decimal minutes per year

**Correction per decimal minute (in decimal minutes):**
\[
\frac{242.5 \text{ decimal minutes}}{365{,}000} = \frac{2425}{3{,}650{,}000} = 0.0006643835616438356\ldots
\]

**Correction per decimal minute (in SI seconds):**
\[
\frac{20{,}952 \text{ SI seconds}}{365{,}000} = \frac{20952}{365000} = 0.0573972602739726\ldots \text{ SI seconds}
\]

**In SI microseconds:**
\[
0.0573972602739726 \times 10^6 = 57397.2602739726\ldots \text{ µs}
\]

\[
\boxed{\approx 57{,}397 \text{ SI microseconds per decimal minute}}
\]

---

### Case C — Correct every decimal hour

**Intervals per year:**  
365 days × 10 = **3 650** decimal hours per year

**Correction per decimal hour (in decimal hours):**
\[
\frac{2.425 \text{ decimal hours}}{3{,}650} = \frac{2.425}{3650} = 0.0006643835616438356\ldots
\]

**Correction per decimal hour (in SI seconds):**
\[
\frac{20{,}952 \text{ SI seconds}}{3{,}650} = \frac{20952}{3650} = 5.73972602739726\ldots \text{ SI seconds}
\]

**In SI milliseconds:**
\[
5.73972602739726 \times 10^3 = 5739.72602739726\ldots \text{ ms}
\]

\[
\boxed{\approx 5{,}739.73 \text{ SI milliseconds per decimal hour}}
\]

---

### Case D — Correct every day

**Intervals per year:** **365** days

**Correction per day (in decimal seconds):**
\[
\frac{24{,}250 \text{ decimal seconds}}{365} = \frac{24250}{365} = 66.43835616438356\ldots
\]

\[
\boxed{\approx 66.4384 \text{ decimal seconds per day}}
\]

**Correction per day (in SI seconds):**
\[
\frac{20{,}952 \text{ SI seconds}}{365} = \frac{20952}{365} = 57.3972602739726\ldots \text{ SI seconds}
\]

\[
\boxed{\approx 57.3973 \text{ SI seconds per day}}
\]

---

### Case E — Correct once per year

**Intervals per year:** **1**

**Correction (in decimal time):**
- **2.425 decimal hours**
- **242.5 decimal minutes**
- **24 250 decimal seconds**

**Correction (in SI):**
\[
\boxed{20{,}952 \text{ SI seconds} = 5 \text{ h } 49 \text{ min } 12 \text{ s (SI)}}
\]

---

## 5️⃣ Summary Table

| Correction interval | Intervals per year | Correction per interval (decimal units) | Correction per interval (SI units) |
|--------------------|--------------------|----------------------------------------|-----------------------------------|
| **Every decimal second** | 36 500 000 | 6.64384×10⁻⁴ decimal sec | 573 973 ns |
| **Every decimal minute** | 365 000 | 6.64384×10⁻⁴ decimal min | 57 397 µs |
| **Every decimal hour** | 3 650 | 6.64384×10⁻⁴ decimal hr | 5 739.73 ms |
| **Every day** | 365 | 66.4384 decimal sec | 57.3973 s |
| **Once per year** | 1 | 2.425 dec hr = 242.5 dec min = 24 250 dec sec | 20 952 s |

---

## 6️⃣ Verification Notes

- The fractional correction per unit is constant: \( \frac{0.2425}{365} = \frac{2425}{3650000} \approx 0.000664384 \) in the relevant decimal unit.
- 1 decimal second = 0.864 SI seconds, so 573 973 ns ≈ 0.573973 ms, and 0.573973/0.864 ≈ 0.6644, matching the fractional correction.
- All values carried to at least 6 significant digits as requested.
