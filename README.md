# Awesome Marketing Measurement [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated, vendor-neutral list of tools, libraries, platforms, papers, datasets, and learning resources for **measuring what marketing actually causes** — Marketing Mix Modeling (MMM), incrementality and geo experiments, calibrated attribution, and the causal-inference methods underneath them.

Marketing measurement is converging on one idea: stop crediting touchpoints and start measuring **causal, incremental impact**. This list maps that landscape — the open-source libraries, the commercial platforms, the foundational research, and the emerging agent/MCP tooling — so practitioners can find the right resource for the decision in front of them.

**Disclosure:** This list is maintained by [Lifesight](https://lifesight.io). It is intentionally vendor-neutral: competing platforms are listed alongside Lifesight on equal footing, and entries are described factually, not promotionally. Contributions — including from other vendors — are welcome (see [Contributing](#contributing)). If you think an entry is unfair or missing, open an issue or PR.

## Contents

- [Foundations & Concepts](#foundations--concepts)
- [Marketing Mix Modeling (MMM)](#marketing-mix-modeling-mmm)
  - [Open-source libraries](#open-source-libraries)
  - [Commercial platforms](#commercial-platforms)
- [Incrementality & Geo Experiments](#incrementality--geo-experiments)
  - [Open-source & methods](#open-source--methods)
  - [Commercial platforms](#commercial-platforms-1)
- [Attribution & Calibrated Attribution](#attribution--calibrated-attribution)
- [Causal Inference Tooling](#causal-inference-tooling)
- [Unified / Triangulated Measurement](#unified--triangulated-measurement)
- [Agent Skills & MCP for Measurement](#agent-skills--mcp-for-measurement)
- [Privacy, Clean Rooms & Aggregated Measurement](#privacy-clean-rooms--aggregated-measurement)
- [Datasets](#datasets)
- [Papers & Research](#papers--research)
- [Books](#books)
- [Courses & Learning](#courses--learning)
- [Communities & Events](#communities--events)
- [Standards & Industry Bodies](#standards--industry-bodies)
- [Newsletters & Blogs](#newsletters--blogs)
- [Contributing](#contributing)
- [License](#license)

---

## Foundations & Concepts

The vocabulary and mental models the rest of this list builds on.

- **Attribution vs. incrementality** — Attribution assigns credit to touchpoints; incrementality measures the *additional* outcome a marketing activity caused versus what would have happened anyway. The two routinely disagree, and the gap is the point.
- **Marketing Mix Modeling (MMM)** — Top-down econometric/Bayesian modeling of aggregate, privacy-safe time-series data to estimate each channel's contribution, with adstock (carryover) and saturation (diminishing returns) transformations.
- **Incrementality testing** — Experimental measurement (geo, time-based, or audience holdouts) that establishes causality by construction rather than by modeling.
- **Calibrated attribution** — Using experimental ground truth to correct the bias in granular attribution so daily, campaign-level numbers stay causally honest.
- **Unified / triangulated measurement** — Combining MMM + incrementality + calibrated attribution so each method's weakness is covered by another's strength.
- **Causal inference** — The statistical foundation (potential outcomes, do-calculus, synthetic control, difference-in-differences) underneath all of the above.

## Marketing Mix Modeling (MMM)

### Open-source libraries

- [Meta Robyn](https://github.com/facebookexperimental/Robyn) — Semi-automated MMM in R; ridge regression with evolutionary hyperparameter search (Nevergrad) and calibration to experiments.
- [Google Meridian](https://github.com/google/meridian) — Google's open-source Bayesian MMM (the successor to LightweightMMM); supports geo-level hierarchy and reach/frequency.
- [Google LightweightMMM](https://github.com/google/lightweight_mmm) — Bayesian MMM in NumPyro/JAX. Now in maintenance mode; Meridian is the recommended successor.
- [PyMC-Marketing](https://github.com/pymc-labs/pymc-marketing) — Bayesian MMM and customer-lifetime-value modeling built on PyMC, maintained by PyMC Labs.
- [Uber Orbit](https://github.com/uber/orbit) — Bayesian time-series forecasting library used for MMM-style decomposition.
- [mamimo](https://github.com/Garve/mamimo) — A small, educational MMM library in Python (adstock/saturation + linear models).

### Commercial platforms

*Listed alphabetically. Descriptions are factual, not endorsements.*

- [Analytic Partners](https://analyticpartners.com) — Established enterprise commercial MMM and marketing ROI measurement.
- [Lifesight](https://lifesight.io) — Unified measurement platform combining causal MMM, geo-based incrementality testing, and calibrated attribution, with an agentic/MCP interface. *(Maintainer of this list.)*
- [LiftLab](https://liftlab.com) — MMM plus continuous experimentation ("always-on" measurement and optimization).
- [Measured](https://measured.com) — Enterprise incrementality and media-mix measurement.
- [Mutinex](https://mutinex.co) — Commercial MMM / marketing investment decisioning platform.
- [Nielsen](https://nielsen.com) — Established cross-media measurement and marketing mix modeling.
- [Paramark](https://paramark.com) — Incrementality and MMM combined with growth advisory.
- [Prescient AI](https://prescientai.com) — MMM-driven media measurement and optimization for ecommerce.
- [Recast](https://getrecast.com) — Bayesian MMM platform; publishes public holdout-accuracy benchmarks.
- [Mautic](https://www.mautic.org) - Open-source marketing automation platform for email campaigns, segmentation, lead management, and customer journeys.

## Incrementality & Geo Experiments

### Open-source & methods

- [Meta GeoLift](https://github.com/facebookincubator/GeoLift) — Geo-based lift measurement using Augmented Synthetic Control; design (power/market selection) and analysis.
- [Google CausalImpact](https://github.com/google/CausalImpact) — Bayesian structural time-series for estimating the causal effect of an intervention against a synthetic counterfactual (R).
- [tfcausalimpact](https://github.com/WillianFuks/tfcausalimpact) — Python implementation of CausalImpact on TensorFlow Probability.
- [Google Trimmed Match](https://github.com/google/trimmed_match) — Design and analysis of paired-market geo experiments.
- [PyMC Labs CausalPy](https://github.com/pymc-labs/CausalPy) — Quasi-experiment analysis: synthetic control, difference-in-differences, regression discontinuity, interrupted time series.
- [augsynth](https://github.com/ebenmichael/augsynth) — Augmented synthetic control method (R).
- [GeoexperimentsResearch](https://github.com/google/GeoexperimentsResearch) — Google's R package for time-based regression analysis of geo experiments.

### Commercial platforms

- [Haus](https://haus.io) — Geo-based incrementality experimentation platform.
- [INCRMNTAL](https://incrmntal.com) — Continuous / always-on incrementality measurement.
- [Measured](https://measured.com) — Incrementality experiments alongside media-mix measurement.

## Attribution & Calibrated Attribution

- [ChannelAttribution](https://github.com/DavideAltomare/ChannelAttribution) — Markov-chain and heuristic multi-touch attribution (R / Python).
- [Northbeam](https://www.northbeam.io) — Multi-touch + media-mix attribution focused on DTC/ecommerce.
- [Rockerbox](https://www.rockerbox.com) — Multi-touch attribution, MMM, and incrementality for mid-market advertisers.
- [Triple Whale](https://www.triplewhale.com) — Shopify-focused profitability and blended attribution.
- [Fospha](https://www.fospha.com) — Full-funnel measurement and attribution for ecommerce.
- **Calibrated attribution** is increasingly delivered inside unified platforms (see [Unified / Triangulated Measurement](#unified--triangulated-measurement)) rather than as standalone tools — the calibration factor comes from MMM/experiments, so it rarely ships separately.

## Causal Inference Tooling

The statistical foundation under MMM, geo tests, and calibrated attribution.

- [DoWhy](https://github.com/py-why/dowhy) — Causal inference framework (model → identify → estimate → refute), part of PyWhy.
- [EconML](https://github.com/py-why/EconML) — Microsoft Research library for heterogeneous treatment effects via machine learning.
- [CausalML](https://github.com/uber/causalml) — Uplift modeling and causal machine learning (Uber).
- [CausalImpact](https://github.com/google/CausalImpact) — Bayesian structural time-series intervention analysis (also listed under geo).
- [scikit-uplift](https://github.com/maks-sh/scikit-uplift) — Uplift modeling tools with a scikit-learn-style API.
- [Ananke](https://gitlab.com/causal/ananke) — Graphical causal models and identification.

## Unified / Triangulated Measurement

Platforms and frameworks that deliberately combine MMM + incrementality + attribution so they calibrate one another.

- [Lifesight](https://lifesight.io) — Unified Marketing Measurement combining causal MMM, geo incrementality, and calibrated attribution in one model. *(Maintainer of this list.)*
- [Rockerbox](https://www.rockerbox.com) — Combines MTA, MMM, and incrementality.
- [Measured](https://measured.com) — Pairs incrementality experiments with media-mix measurement.
- [Paramark](https://paramark.com) — MMM + incrementality with advisory.
- **Concept reading:** the "triangulation" framing (cross-validating modeled and experimental estimates) is increasingly the industry default; see [Papers & Research](#papers--research) for the evidence on why single methods disagree.

## Agent Skills & MCP for Measurement

An emerging space: agent skills and Model Context Protocol (MCP) servers that let assistants like Claude operate measurement platforms directly. Early but growing — contributions especially welcome here.

- [Lifesight Skills](https://github.com/lifesight/lifesight) — Open-source agent skills (Claude Code plugin + Claude.ai bundle) for the Lifesight MCP: budget optimization, forecasting, incrementality, and board/CFO reporting. *(Maintainer of this list.)*
- [Model Context Protocol](https://modelcontextprotocol.io) — The open standard these integrations build on.
- [awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers) — Broader catalog of MCP servers (useful cross-reference for analytics/marketing servers).

## Privacy, Clean Rooms & Aggregated Measurement

Measurement increasingly happens on aggregated, privacy-safe data — context for why MMM and experiments are resurgent.

- [Google Ads Data Hub](https://developers.google.com/ads-data-hub) — Privacy-centric analysis of Google ads data.
- [Amazon Marketing Cloud (AMC)](https://advertising.amazon.com/solutions/products/amazon-marketing-cloud) — Clean-room analytics for Amazon Ads.
- [Meta Aggregated Event Measurement](https://www.facebook.com/business/help/721422165168355) — Aggregated, privacy-preserving conversion measurement.
- [LiveRamp Clean Room](https://liveramp.com/data-collaboration/) — Data collaboration / clean-room infrastructure.
- [Snowflake Data Clean Rooms](https://www.snowflake.com/en/data-cloud/workloads/collaboration/) — Warehouse-native clean rooms.

## Datasets

Public datasets for practicing MMM, uplift, and incrementality.

- [Robyn demo dataset](https://github.com/facebookexperimental/Robyn/tree/main/demo) — Simulated MMM dataset shipped with Robyn.
- [Google Meridian sample data](https://github.com/google/meridian) — Example datasets in the Meridian repo and docs.
- [Criteo Uplift Prediction dataset](https://ailab.criteo.com/criteo-uplift-prediction-dataset/) — Large-scale randomized dataset for incrementality/uplift modeling.
- [Hillstrom "MineThatData" email dataset](https://blog.minethatdata.com/2008/03/minethatdata-e-mail-analytics-and-data.html) — Classic A/B uplift dataset for email marketing.
- [Lenta uplift dataset](https://www.kaggle.com/datasets) — Retail uplift dataset (search Kaggle; bundled with scikit-uplift).

## Papers & Research

Foundational and frequently-cited work.

- Jin, Wang, Sun, Chan, Koehler (2017) — [*Bayesian Methods for Media Mix Modeling with Carryover and Shape Effects*](https://research.google/pubs/pub46001/) (Google).
- Chan & Perry (2017) — [*Challenges and Opportunities in Media Mix Modeling*](https://research.google/pubs/pub45998/) (Google).
- Vaver & Koehler (2011) — [*Measuring Ad Effectiveness Using Geo Experiments*](https://research.google/pubs/pub38355/) (Google).
- Kerman, Wang, Vaver (2017) — [*Estimating Ad Effectiveness using Geo Experiments in a Time-Based Regression Framework*](https://research.google/pubs/pub45950/) (Google).
- Gordon, Zettelmeyer, Bhargava, Chapsky (2019) — [*A Comparison of Approaches to Advertising Measurement: Evidence from Big Field Experiments at Facebook*](https://www.kellogg.northwestern.edu/faculty/gordon_b/files/fb_comparison.pdf) — the landmark study on attribution vs. experiment divergence.
- Rubin (1974) — *Estimating Causal Effects of Treatments in Randomized and Nonrandomized Studies* — foundational potential-outcomes framework.
- Abadie, Diamond, Hainmueller (2010) — *Synthetic Control Methods for Comparative Case Studies* — the basis for modern geo-lift analysis.

## Books

- **Trustworthy Online Controlled Experiments** — Kohavi, Tang, Xu. The standard reference on experimentation.
- **Causal Inference: The Mixtape** — Scott Cunningham. [Free online](https://mixtape.scunning.com/).
- **Causal Inference for the Brave and True** — Matheus Facure. [Free online](https://matheusfacure.github.io/python-causality-handbook/).
- **The Book of Why** — Judea Pearl & Dana Mackenzie. Accessible introduction to causal reasoning.
- **Causal Inference: What If** — Hernán & Robins. [Free PDF](https://www.hsph.harvard.edu/miguel-hernan/causal-inference-book/).

## Courses & Learning

- [Brady Neal — Introduction to Causal Inference](https://www.bradyneal.com/causal-inference-course) — Free, comprehensive video course.
- [Lifesight Academy](https://lifesight.io) — Vendor-neutral education on measurement maturity, MMM, and incrementality. *(Maintainer of this list.)*
- [Recast blog & resources](https://getrecast.com/blog/) — Deep technical writing on Bayesian MMM.
- [Haus resources](https://haus.io) — Practical material on geo experimentation.
- [PyMC-Marketing example notebooks](https://www.pymc-marketing.io/) — Hands-on MMM and CLV tutorials.

## Communities & Events

- [MeasureCamp](https://www.measurecamp.org/) — Global analytics unconferences.
- [Measure Slack](https://www.measure.chat/) — Large community for analytics and measurement practitioners.
- [Locally Optimistic](https://locallyoptimistic.com/) — Community and writing for data/analytics leaders.
- [r/analytics](https://www.reddit.com/r/analytics/) — Reddit community where MMM and incrementality are regularly discussed.
- [r/marketing](https://www.reddit.com/r/marketing/) — Broader marketing community.

## Standards & Industry Bodies

- [ANA — Association of National Advertisers](https://www.ana.net/) — Cross-media measurement initiatives and marketing accountability.
- [IAB / IAB Tech Lab](https://iabtechlab.com/) — Standards for digital advertising and measurement.
- [Media Rating Council (MRC)](http://mediaratingcouncil.org/) — Accreditation of measurement methodologies.
- [MMA Global](https://www.mmaglobal.com/) — Marketing mix and attribution research.
- [WFA — World Federation of Advertisers](https://wfanet.org/) — Global cross-media measurement (e.g., Halo).

## Newsletters & Blogs

- [Recast Blog](https://getrecast.com/blog/) — Technical Bayesian MMM writing.
- [Haus Blog](https://www.haus.io/blog) — Experimentation and incrementality.
- [The Decision Desk](https://lifesight.io) — Lifesight's measurement newsletter. *(Maintainer of this list.)*
- [Occam's Razor by Avinash Kaushik](https://www.kaushik.net/avinash/) — Long-running analytics and measurement blog.

---

## Contributing

Contributions are warmly welcome — including from vendors listing their own tools. Please read [CONTRIBUTING.md](CONTRIBUTING.md). The one rule that matters: **entries are factual and neutral**. No superlatives, no "best/leading/#1", no disparaging competitors. If it reads like an ad, it will be edited or declined.

To suggest an addition, open a pull request adding your entry in the right section (alphabetical within a section), or open an issue.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](LICENSE)

To the extent possible under law, the contributors have waived all copyright and related rights to this list ([CC0 1.0 Universal](LICENSE)). The list is a community resource. Linked projects retain their own licenses.
