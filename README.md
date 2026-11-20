# NGI Q-System Rock Mass Classification & Support Estimator

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/NarasimhaThota9/Q-System-Support-Requirement/blob/main/Q%20System%20Rock%20Mass%20Classification%20%26%20Support%20Estimator.ipynb)

An interactive Python notebook for evaluating the NGI Q-system for rock mass classification and estimating preliminary tunnel support requirements. 

This tool takes standard rock mass parameters (RQD, joint conditions, stress conditions, etc.) and calculates the Q-value, equivalent dimension (De), and provides indicative support recommendations based on Barton's guidelines. It generates interactive Plotly charts to visualize the Q-scale and the self-supporting boundary.

**Disclaimer:** This tool is for preliminary screening and educational purposes. It should not replace detailed engineering geological assessments or site-specific support design.

## Methodology

The Q-value is calculated using the standard Barton, Lien & Lunde (1974) equation:

`Q = (RQD / Jn) * (Jr / Ja) * (Jw / SRF)`

**Inputs required:**
*   **RQD:** Rock Quality Designation
*   **Jn:** Joint set number
*   **Jr:** Joint roughness number
*   **Ja:** Joint alteration number
*   **Jw:** Joint water reduction factor
*   **SRF:** Stress Reduction Factor
*   **ESR:** Excavation Support Ratio (based on the intended use of the opening)
*   **Tunnel Span:** Width or height of the excavation in meters

**Outputs generated:**
*   **Q Value:** Rounded down to the lowest integer.
*   **Quality Classification:** From "Exceptionally poor" to "Exceptionally good".
*   **Equivalent Dimension (De):** Calculated as `Span / ESR`.
*   **Support Requirement:** Compares `De` against the maximum self-supporting span (`De_max = 2 * Q^0.4`).
*   **Indicative Bolt Length:** `2 + 0.15 * De`.
*   **Indicative Roof Pressure:** Based on `(2.0 / Jr) * (Q^-1/3) * 98.0665` (kPa).

## Output Preview

The notebook produces a console printout of the results, a Q-scale classification bar chart, and a De vs Q support boundary plot.

![Q-System Output](output.png)

## Usage

**Option 1: Run in Browser (Google Colab)**
Click the "Open in Colab" badge at the top of this file. Once loaded, modify the input parameters in the code block and click `Runtime > Run all`.

**Option 2: Run Locally**
```bash
git clone https://github.com/NarasimhaThota9/Q-System-Support-Requirement.git
cd Q-System-Support-Requirement
pip install plotly numpy
jupyter notebook
