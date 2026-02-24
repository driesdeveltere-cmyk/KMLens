# KMLens — Kaplan-Meier Digitizer & Censoring Explorer

A browser-based tool for digitizing Kaplan-Meier survival curves from oncology publications and performing censoring analysis with sensitivity exploration.

## Features

- **Axis calibration** — 3-click pixel-perfect coordinate mapping
- **Interactive digitization** — click along curves to capture data points
- **Exact censoring calculation** — derived from number-at-risk table using the Guyot method
- **Greenwood 95% confidence intervals** — complementary log-log method
- **Log-rank test** — Mantel-Haenszel statistic with chi-squared p-value
- **Peto hazard ratio** with 95% CI
- **Sensitivity analysis** — toxicity-driven and disappointment-driven informative censoring scenarios
- **CSV export** — full results including digitized points and CI bounds

## Live Demo

👉 **[kmlens.yourname.github.io](https://yourname.github.io/kmlens)**

## Deploy in 3 Steps

### Option A — GitHub Pages (recommended, free)

1. **Fork or upload** this repository to your GitHub account
2. Go to **Settings → Pages**
3. Under *Source*, select **Deploy from a branch → main → / (root)**
4. Click **Save** — your site will be live at `https://yourusername.github.io/kmlens` within ~60 seconds

### Option B — Netlify (drag & drop, 30 seconds)

1. Go to [netlify.com](https://netlify.com) and sign up (free)
2. Drag the entire `kmlens` folder onto the Netlify dashboard
3. Done — you get a public URL instantly

### Option C — Run locally

Just open `index.html` in any modern browser. No server needed.

```bash
# Or serve with Python if you want a local URL:
cd kmlens
python3 -m http.server 8080
# Open http://localhost:8080
```

## Usage

| Step | Action |
|------|--------|
| 1 | Upload a screenshot of the KM figure. Set axis ranges. |
| 2 | Click the plot origin, x-axis end, and y-axis top to calibrate. Then click along each curve. |
| 3 | Enter the number-at-risk table from the publication. |
| 4 | View censoring breakdown, CI, HR, p-value. Run sensitivity analysis. |

## Methods

- **Censoring**: `C(t1→t2) = N(t1) - N(t2) - Events(t1→t2)`  
  Events estimated as `⌊N(t1) × (S(t1) - S(t2)) / S(t1)⌋` (Guyot et al., BMC Med Res Methodol 2012)
- **CI**: Greenwood formula with complementary log-log transformation
- **HR**: Peto method — `exp((O-E)/V)`
- **p-value**: Mantel-Haenszel log-rank test

## Browser Support

Chrome, Firefox, Safari, Edge — any modern browser. No installation, no backend, no data leaves your browser.

## License

MIT
