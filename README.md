# Elevate MedSpa — Customer Segmentation & Marketing Audit


[Open In Colab](https://colab.research.google.com/github/pratyushpradhan1801/medspa-customer-segmentation-kpmg/blob/main/MedSpa_Customer_Segmentation.ipynb) ([image](https://camo.githubusercontent.com/eff96fda6b2e0fff8cdf2978f89d61aa434bb98c00453ae23dd0aab8d1451633/68747470733a2f2f636f6c61622e72657365617263682e676f6f676c652e636f6d2f6173736574732f636f6c61622d62616467652e737667)) [Python](https://camo.githubusercontent.com/fcdf47071178fa8539294173dc5716605fa3856c2ffc6fd9c2c31e1e742747be/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f507974686f6e2d332e31302b2d626c7565) [scikit-learn](https://camo.githubusercontent.com/2ac471bcd725c5cffba8809255f2871fa1caa9e3af364b2e8f8cc471e9b39955/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f7363696b69742d2d6c6561726e2d4b2d2d4d65616e732d6f72616e6765) [Power BI](https://camo.githubusercontent.com/841398e3f32aab5bae08e3c04fdef546660fd37197f64d05d5f4301d3d44a057/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f506f77657225323042492d64617368626f6172642d79656c6c6f77) [Data](https://camo.githubusercontent.com/70bb398a3c6306f54a16742d63a6cff2ee00147ba341ae1c1dafb521eef09710/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f646174612d73696d756c617465642d6c6967687467726579)

## *An unsupervised machine-learning audit that segments 5,000 med-spa clients into behavioural cohorts, and uses them to show why a discount-led acquisition strategy is quietly losing money — with an honest read on what the data does and does not support.*


## Overview


**Elevate Aesthetics** is a premium medical spa (fictional, used here for demonstration) offering treatments such as laser therapy, CoolSculpting, and medical-grade facials priced between **$500 and $2,500**. A loyal client who visits quarterly is worth over **$4,000 a year**.

The owner has been driving foot traffic with *"50% off your first treatment"* ads on Facebook and Groupon. The waiting room is full, but margins are thin. This project audits a simulated CRM export of 5,000 clients to test a single hypothesis: **the discount-led strategy is attracting predominantly low-retention customers.**

The analysis lives in a Python notebook (K-Means segmentation) and an interactive Power BI dashboard.

> All data is simulated for demonstration purposes. No real company or customer data is used. Currency figures are illustrative ($).

---

## Key Findings


*Segment names are playful Hindi-English labels; each plain-English descriptor is in italics, with fuller profiles under *[*Customer Segments*](https://github.com/PratyushPradhan1801/medspa-customer-segmentation-kpmg#customer-segments)*.*

| **Segment** | **Clients** | **Revenue** | **Share** | **Avg Order Value** | **Repeat Rate** |
|---|---:|---:|---:|---:|---:|
| **Glow Ke Nawab** *(Organic VIPs)* | 1,135 | $8.21M | 77.9% | $1,939 | 98.41% |
| **Hamesha 25 Club** *(Referral Regulars)* | 574 | $0.98M | 9.3% | $823 | 70.56% |
| **Self-Care Sena** *(Facebook one-timers)* | 2,069 | $0.84M | 8.0% | $361 | 7.39% |
| **Gayab Grahak** *(Groupon one-timers)* | 1,222 | $0.51M | 4.8% | $368 | 7.69% |

- **Revenue is extremely concentrated.** The Organic VIP cohort is \~23% of clients but drives **\~78% of revenue** at a \~98% repeat rate.
- **Discount channels are the volume, not the value.** The two one-timer cohorts (Self-Care Sena + Gayab Grahak) total **3,291 clients — 66% of the base** — but under **13% of revenue**, with \~90% never returning after the first visit.
- **The signal lives in the acquisition channel.** Lifetime value per client ranges from **\~$7,050 (Organic)** to **\~$410 (Facebook/Groupon)** — a \~17x gap that tracks almost entirely with *how the client was acquired*, not their age, gender, or location.

---

## Strategic Recommendation


The clearest data-supported action is to **stop subsidising one-and-done discount traffic and reinvest in the channels that retain.**

1. **Cut or cap the "50% off" Facebook/Groupon spend.** These channels fill the calendar but churn \~90% after one discounted visit, eroding margin on every appointment.
2. **Reallocate budget to organic and referral acquisition** (educational content, consultation funnels, referral incentives), which together produce \~87% of revenue at far higher retention.
3. **Pivot from offer-led to authority-led marketing** — attract high-intent clients searching for expert treatment, not bargain hunters.

**Illustrative acquisition-cost scenario.** The \~3,291 Facebook/Groupon one-timers contribute under **$1.3M** combined yet consume the bulk of ad spend, and \~90% never rebook. At a **$30 CPA**, that is roughly **$99K** of acquisition cost chasing the lowest-value clients — before counting the margin erased by the 50%-off first visit. Redirecting even 60% of that budget into **referral incentives** (e.g. $50 per referred client) and **organic/content acquisition** targets the cohorts that actually retain (Organic \~97%, Referral \~70%).

**A simple guardrail:** fund a channel only when projected **LTV\:CAC clears \~3:1**. Organic clears it comfortably (~~$7,050 LTV); discounted Facebook/Groupon (~~$410 LTV) does not.

> Channel and demographic targeting *beyond acquisition source* should be treated as **hypotheses to validate with controlled A/B tests**, not conclusions. In this dataset, age, gender, and location are near-uniform across segments and provide no reliable targeting signal on their own.

---

## Customer Segments


> **Read this first.** The model clusters on **behavioural, financial, channel, and price-sensitivity features**. Segment *names are interpretive overlays.* The strongest separators are **acquisition channel, repeat behaviour, and order value** — the age/gender/location columns are roughly uniform across segments, so any demographic claim is a hypothesis to be tested, not a finding.

**Glow Ke Nawab — Organic VIPs (n = 1,135) — the revenue engine**

- *Data:* highest income (\~$103k), oldest (\~45), longest sessions (\~15 min), most frequent (3.7 visits), highest AOV ($1,939); \~98% repeat; \~78% of total revenue. Almost entirely acquired via Organic Search.
- *Interpretation (hypothesis):* high-intent clients who research, book a consultation, pay full price, and return.

**Hamesha 25 Club — Referral Regulars (n = 574) — the steady middle**

- *Data:* mid income (\~$86k), 2.1 visits, $823 AOV, 70% repeat; \~9% of revenue. Predominantly referral-acquired.
- *Interpretation (hypothesis):* trust-driven clients who arrive through word of mouth and convert reliably.

**Self-Care Sena — Facebook one-timers (n = 2,069) — high volume, low value**

- *Data:* young (~~30), lower income (~~$55k), 1.1 visits, $361 AOV, \~10% repeat; the **largest** cohort by headcount but only \~8% of revenue. Almost entirely Facebook-acquired.
- *Interpretation (hypothesis):* discount-motivated first-timers who claim the offer and leave.

**Gayab Grahak — Groupon one-timers (n = 1,222) — the leak**

- *Data:* near-identical to Self-Care Sena (young, low income, 1.1 visits, $368 AOV, \~10% repeat); \~5% of revenue. Groupon-acquired. *"Gayab Grahak" = the customer who vanishes.*
- *Interpretation (hypothesis):* deal-site bargain hunters with no intent to return at full price.

---

## Methodology


1. **Data validation** — confirmed the 5,000-row export was complete (no nulls, no duplicate `Client_ID`s) across all 12 columns.
2. **Feature selection** — five behavioural/financial signals (`Age`, `Income`, `Engagement_Time_Minutes`, `Purchase_Frequency`, `Average_Order_Value`) **plus** the two business-critical categoricals (`Acquisition_Source`, `Price_Sensitivity`), one-hot encoded.
3. **Standardisation** — `StandardScaler` on the numeric features so high-magnitude columns (income, revenue) don't dominate the distance calculation.
4. **Clustering** — `KMeans(n_clusters=4, init='k-means++', random_state=42)`.
5. **Validation & profiling** — chose *k* with elbow + silhouette analysis, then profiled each cluster's feature averages (heatmap) before mapping clusters to named segments.

> **On the choice of k = 4:** silhouette actually peaks at **k = 2** (\~0.51), meaning the cleanest statistical split is simply *"high-value vs bargain-hunter."* **k = 4** was chosen for interpretability — it separates the four acquisition channels into actionable cohorts — and that trade-off is stated openly rather than hidden behind a metric.

> **Note on the dashboard vs the notebook:** the Power BI dashboard reflects an earlier clustering pass (numeric features only); the notebook here is the **refined version** with the channel and price variables added. The refined segmentation maps each cohort cleanly onto its acquisition source.

---

## Dataset


A simulated export of **5,000 med-spa clients x 12 columns**:

| **Column** | **Type** | **Description** |
| ------------------------- | ----- | ------------------------------------------------- |
| `Client_ID`               | str   | Unique client identifier                          |
| `Age`                     | int   | Client age                                        |
| `Gender`                  | cat   | Female / Male / Non-binary                        |
| `Location`                | cat   | Urban / Suburban / Rural                          |
| `Income`                  | int   | Annual income ($)                                 |
| `User_Interest`           | cat   | Skincare / Anti-aging / Wellness                  |
| `Acquisition_Source`      | cat   | Facebook Ad / Groupon / Organic Search / Referral |
| `Device_Type`             | cat   | Mobile / Desktop / Tablet                         |
| `Engagement_Time_Minutes` | float | Avg session length                                |
| `Price_Sensitivity`       | cat   | High / Medium / Low                               |
| `Purchase_Frequency`      | int   | Visits in the period                              |
| `Average_Order_Value`     | float | Mean spend per visit ($)                          |
| `Cluster`                 | int   | K-Means cluster ID                               |
| `Cluster_Name`            | str   | Human-readable segment label                     |

A "churn / repeat" signal is **derived**, not given: a client is counted as *retained* when `Purchase_Frequency >= 2` (i.e. they came back at least once). This definition is stated explicitly so every retention figure is traceable to a formula.

---

## Visualisations


The clearest view of the segmentation is the **cluster profile** — the average of each feature per segment (cell = actual value, colour = relative to other segments):

![Cluster Profile Heatmap](./cluster-profile-heatmap.png)

Glow Ke Nawab stands out in red on every feature; the two one-timer cohorts sit blue and low, separated almost entirely by acquisition channel.

A 3D scatter (Income x Order Value x Session Duration) gives a complementary view:

![3D Segment Map](./3d-persona-map.png)

Open `3d-persona-map.html` in a browser to explore it interactively, or run the notebook in Colab.

---

## Power BI Dashboard

An interactive Power BI dashboard accompanies the analysis, with slicers for gender, location, segment, acquisition source, and price sensitivity; KPI cards for revenue, customers, AOV, retention, and churn; and revenue / lead-volume / retention breakdowns by channel and cohort.

The dashboard is synced with the refined GitHub CSV and currently reports:

- **Total Revenue:** $10.54M
- **Customers:** 5,000
- **Average Order Value:** $774.23
- **Retention Rate:** 35.38%
- **Churn Rate:** 64.62%

The cluster revenue and retention visuals use the same final segment assignments as the notebook and GitHub dataset.

- **Power BI file:** the `.pbix` dashboard file is included in the repository root.

---

## Skills Demonstrated


- Data validation, feature encoding, standardisation, and cluster profiling
- Unsupervised ML (K-Means) with elbow + silhouette validation
- Honest interpretation — separating evidence from narrative
- Communicating analysis as a testable business recommendation, across Python and Power BI

---

## Tech Stack


Python . pandas . NumPy . scikit-learn . Plotly . Matplotlib . Power BI . Google Colab

---

## Getting Started


**Run in Google Colab (recommended):** use the badge at the top of this page.

**Run locally:**

```
git clone https://github.com/pratyushpradhan1801/medspa-customer-segmentation-kpmg.git
cd medspa-customer-segmentation-kpmg
pip install -r requirements.txt
jupyter notebook

```

## Project Structure

medspa-customer-segmentation-kpmg/
├── data/
│   └── medspa_customer_cohorts.csv
├── README.md
├── requirements.txt
├── .gitignore
├── MedSpa_Customer_Segmentation.ipynb
├── Power BI dashboard (.pbix)
├── cluster-profile-heatmap.png
├── 3d-persona-map.png
└── 3d-persona-map.html
```
```
## Limitations & Future Work


- **Simulated data, stated conclusion.** The data is synthetic and the case brief pre-states the expected outcome, so this project showcases the *workflow and communication*, not an independent discovery.
- **Retention is a proxy.** It means a repeat purchase (`Purchase_Frequency >= 2`), not time-windowed cohort retention (which would need visit timestamps).
- **The clusters mostly recover the channel.** Acquisition source dominates the encoded features, so the segments map almost 1:1 onto channels — handy for action, but it means K-Means adds little here beyond a channel grouping. **K-Prototypes** (Gower distance) would handle the mixed numeric/categorical data more rigorously.
- **Demographics don't separate segments.** Age, gender, and location are near-uniform across cohorts, so any demographic-targeting claim is a hypothesis for A/B testing, not a finding.

*Future work:* validate channel and demographic hypotheses with controlled tests; evaluate K-Prototypes or another mixed-data clustering approach; train a classifier to score new clients into a segment; and publish the dashboard as a shareable Power BI report.

```
```

## Author

**Pratyush Pradhan** . [GitHub](https://github.com/pratyushpradhan1801) . [LinkedIn](https://www.linkedin.com/in/pratyush-pradhan1/)

*Built as a learning project. All data simulated.*
```
