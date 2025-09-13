# dB Calculator (dBm ↔ mW, Frequency ↔ Wavelength)

A tiny, client-side RF utility that runs in any modern browser. It converts:

- **dBm → mW**
- **mW → dBm**
- **Frequency ↔ Wavelength** (in free space)
- A simple **mW → dB relative to 1 W** helper (see notes)

This is the HTML tool you placed at `/db-calc.html` and also embedded on your portfolio homepage.

---

## 🎯 Features

- Zero dependencies (plain HTML + JavaScript)
- Instant results, no backend
- Works offline
- Minimal UI that fits a portfolio site

---

## 🧮 Conversions & Formulas

### dBm → mW
- **Formula:** \( P_{\text{mW}} = 10^{\frac{P_{\text{dBm}}}{10}} \)
- **Example:** 0 dBm → 1 mW; 30 dBm → 1000 mW

### mW → dBm
- **Formula:** \( P_{\text{dBm}} = 10 \log_{10}(P_{\text{mW}}) \)
- **Example:** 1 mW → 0 dBm; 0.1 mW → −10 dBm

### Frequency → Wavelength (free space)
- **Formula:** \( \lambda = \frac{c}{f} \)
- **Where:** \( c = 299{,}792{,}458 \) m/s
- **Units:** \( f \) in **Hz**, \( \lambda \) in **meters**
- **Example:** 1 GHz → 0.299792458 m

### Wavelength → Frequency (free space)
- **Formula:** \( f = \frac{c}{\lambda} \)
- **Units:** \( \lambda \) in **meters**, \( f \) in **Hz**
- **Example:** 0.5 m → 599,584,916 Hz (~0.6 GHz)

### “Convert to dB” helper (relative to 1 W)
- **Current formula in the tool:** `10 * log10(1000 / mW)`  
  This equals \( 30 - 10\log_{10}(P_{\text{mW}}) \) which is **−dBW** (dB relative to 1 W).  
  - If you actually want **dBW**, use \( \text{dBW} = 10\log_{10}(P_{\text{W}}) = 10\log_{10}(P_{\text{mW}}) - 30 \).
  - The current helper is useful when you want the *attenuation to 1 W* as a positive dB number.

> ✅ If you’d like, I can switch this helper to output **dBW** directly and label it accordingly.

---

## 📦 File

- `db-calc.html` — Standalone page containing the UI and JS.

---

## 🚀 Run locally

Just open the file in a browser:

```bash
# macOS
open db-calc.html

# Windows
start db-calc.html

# Linux (GNOME)
xdg-open db-calc.html
