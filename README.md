<div align="center">

# Marriott · Digital Transformation

### Loyalty. Direct. Digital. A stronger tomorrow.

**Five fiscal years. Six KPIs. One view of the business.**

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black) ![Chart.js](https://img.shields.io/badge/Chart.js_4.4.8-FF6384?style=flat-square&logo=chartdotjs&logoColor=white) ![No build step](https://img.shields.io/badge/build_step-none-31824A?style=flat-square)

[Quick start](#check-in) · [Features](#the-view-from-the-top) · [Methodology](#behind-the-numbers) · [Customization](#make-it-yours)

</div>

---

A browser-based executive dashboard exploring Marriott International’s digital transformation across **FY2021–FY2025**. It connects loyalty membership, digital engagement, room growth, and financial performance in a responsive interface built for a University of South Florida graduate digital transformation project.

Open one HTML file and get KPI summaries, trend charts, annotated turning points, management questions, and the evidence behind the numbers.

## Check in

Clone the repo:

```sh
git clone https://github.com/clarkhbrowniii/marriott-dashboard.git
cd marriott-dashboard
```

Open **[marriott-dashboard.html](marriott-dashboard.html)** in a modern browser. That’s the setup. No package installation, API keys, or build command required.

**Charts need an internet connection:** Chart.js and its annotation plugin load from jsDelivr. If those dependencies cannot load, the dashboard displays a message and retains its underlying values and explanations.

Prefer localhost? With Python installed, run:

```sh
python -m http.server 8000
```

Then visit [localhost:8000/marriott-dashboard.html](http://localhost:8000/marriott-dashboard.html).

## The view from the top

- **Executive summary:** six KPI cards with latest available values and baseline comparisons.
- **Charts with context:** bar, line, and doughnut charts, plus documented inflection notes.
- **Evidence you can inspect:** expandable value tables, data classifications, and operating margin inputs.
- **Strategic interpretation:** key insights, management questions, and research next steps.
- **Responsive presentation:** desktop and mobile layouts, print styles, and a back-to-top shortcut.
- **Accessible details:** semantic sections, chart labels, readable data tables, visible keyboard focus, and reduced-motion support.

### Six signals, one story

| KPI | Signal | What the dashboard measures |
| --- | --- | --- |
| Bonvoy membership | Leading | Rounded year-end loyalty members, in millions |
| Direct booking proxy | Lagging | Global Bonvoy member room-night penetration; available FY2023–FY2025 |
| Digital booking adoption | Leading | FY2024 digital share of worldwide systemwide room nights |
| RevPAR growth | Lagging | Provisional annual percentage growth; available FY2022–FY2025 |
| Worldwide net room growth | Leading | Annual net growth in worldwide rooms |
| Operating margin | Lagging | Reported operating income divided by total revenue |

## Behind the numbers

The dashboard is a **document-based academic analysis**. Its labels distinguish reported figures from calculations, working figures, estimates, and unavailable observations. “Reported” reflects attribution in the supplied resources; it does not imply independent verification of every original disclosure.

- **Member penetration is a proxy for direct engagement.** Bonvoy member room nights can be booked through any channel, so this is not an exact direct-versus-OTA booking share.
- **Digital adoption is a snapshot.** The supplied FY2024 figure is 38%, with 222 million digital room nights. It remains marked as a working figure; the other-channel share of 62% is a calculated complement.
- **RevPAR currently shows growth, not dollars.** Its provisional series needs consistent scope and primary-source confirmation. The candidate FY2023 annotation stays disabled pending evidence.
- **Operating margin uses reported revenue.** Owner cost reimbursements affect the denominator; this is not the adjusted fee-business margin.
- **Missing values stay missing.** Absent observations use `null`. Rounded totals and lower bounds retain their qualifiers, including FY2025 net room growth of **over 4.3%**.
- **Interpretation is not causal proof.** Inflection explanations reflect the supplied analyses and their stated limitations.

The dashboard’s **Sources & methodology** section contains the fuller notes and source references.

## Under the hood

```text
marriott-dashboard/
├── README.md
├── marriott-dashboard.html     # Layout, styles, KPI data, and rendering logic
└── kpi-resources/              # Supplied DOCX analyses and PDF research notes
```

| Layer | Implementation |
| --- | --- |
| Layout | Semantic HTML and inline SVG icons |
| Styling | CSS variables, responsive grids, and print rules |
| Data | Embedded `KPI_DATA` JavaScript object |
| Rendering | Vanilla JavaScript |
| Charts | Chart.js **4.4.8** |
| Annotations | chartjs-plugin-annotation **3.1.0** |

The files in `kpi-resources/` document the analysis. The dashboard uses transcribed data embedded in `KPI_DATA`; it does not parse those documents at runtime or fetch live Marriott data.

## Make it yours

Open `marriott-dashboard.html` and find `const KPI_DATA`.

1. Update `company` for the title, project label, summary, and methodology.
2. Update `periods` and each metric’s `values`, keeping their order aligned. Metrics can define their own `periods` for limited coverage.
3. Add source records with unique IDs, then reference those IDs from the relevant metrics.
4. Set appropriate `status`, `valueStatuses`, and qualifiers so the evidence stays visible.
5. Add documented `inflectionPoints`; set `display: true` when they are ready to appear.
6. Refresh the browser and review cards, charts, tables, and source notes together.

For visual changes, edit the CSS variables and style rules. The later style block overrides earlier defaults for the executive presentation.

### Before calling it done

There is no automated test suite configured. For edits, use a short browser review:

- Check desktop and narrow-screen layouts.
- Compare KPI cards and plotted values with the expandable tables.
- Confirm baseline periods, units, source references, and data labels.
- Check navigation, keyboard focus, and print preview.
- Confirm the fallback remains readable when chart dependencies cannot load.

---

<div align="center">

**Built for the University of South Florida · Graduate Digital Transformation**

An academic project examining Marriott International. Not affiliated with or endorsed by Marriott International.

</div>
