# Sources

Curated sources for the NeuroAI and Brain–Computer Interface digest.

## Companies

Company-run blogs and newsrooms that regularly publish on NeuroAI and Brain–Computer Interfaces (BCI).

Each entry records its **Feed** for refreshes: an RSS/Atom URL when one exists (fetch it directly — one cheap request), or `none` when the site has no feed and must be scraped from HTML. Feed status last verified **2026-06-28**.

- **Allen Institute** — [alleninstitute.org/news](https://alleninstitute.org/news/) — Open brain atlases and neural data; AI models of the brain (NeuroAI)
  - Feed: `none` — scrape the news index; publication dates appear only on individual article pages.
- **Blackrock Neurotech** — [blackrockneurotech.com/news](https://blackrockneurotech.com/news/) — NeuroPort / Neuralace arrays; clinical BCI insights
  - Feed: `https://blackrockneurotech.com/news/feed/` (RSS, WordPress; site-wide `/feed/` also works).
- **Cognixion** — [cognixion.com/blog](https://www.cognixion.com/blog/) — Non-invasive AI BCI (Axon-R); assistive communication
  - Feed: `https://www.cognixion.com/blog?format=rss` (RSS, Squarespace; declared in page head).
- **Neuralink** — [neuralink.com/updates](https://neuralink.com/updates/) — Implantable high-bandwidth BCI; product and research updates
  - Feed: `none` — JS-rendered site; scrape the updates page or use web search to confirm dates.
- **OpenBCI** — [openbci.com/community](https://openbci.com/community/) — Open-source EEG/EMG/BCI hardware; community projects and tutorials
  - Feed: `https://openbci.com/community/feed/` (RSS, WordPress; declared in page head).
- **Paradromics** — [paradromics.com/blog](https://paradromics.com/blog/) — Connexus high-channel-count BCI; benchmarking and AI in BCI
  - Feed: `https://paradromics.com/feed` (RSS, Webflow; covers both blog and news posts).
- **Precision Neuroscience** — [precisionneuro.io/articles](https://www.precisionneuro.io/articles) — Layer 7 thin-film cortical interface; news and insights
  - Feed: `none` — scrape the articles index; press releases are hosted on GlobeNewswire (links point off-domain).
- **Synchron** — [synchron.com/news](https://synchron.com/news) — Endovascular Stentrode BCI; Chiral cognitive-AI brain foundation model
  - Feed: `none` — scrape the news page, which aggregates external press coverage (links point off-domain).

## GitHub repositories

Open-source projects that publish code in NeuroAI and Brain–Computer Interfaces — toolkits, benchmarks, and models for acquiring, decoding, and modeling neural data.

Each entry records a **Feed** pointing at the project's GitHub *releases* Atom feed (`/releases.atom`) — a clean stream of tagged releases only, without the noise of pull requests and issues. All repos selected for active release cadence; latest release and feeds verified **2026-06-28**.

- **MNE-Python** — [mne-tools/mne-python](https://github.com/mne-tools/mne-python) — Magnetoencephalography (MEG) and electroencephalography (EEG) analysis in Python; the de facto foundation for neural signal processing. _(latest: v1.12.1, 2026-04-20)_
  - Feed: `https://github.com/mne-tools/mne-python/releases.atom`
- **Braindecode** — [braindecode/braindecode](https://github.com/braindecode/braindecode) — Deep learning to decode EEG, ECG, or MEG signals. _(latest: v1.5.1, 2026-05-20)_
  - Feed: `https://github.com/braindecode/braindecode/releases.atom`
- **MOABB** — [NeuroTechX/moabb](https://github.com/NeuroTechX/moabb) — Mother of All BCI Benchmarks; standardized datasets and pipelines for reproducible BCI evaluation. _(latest: v1.5, 2026-03-21)_
  - Feed: `https://github.com/NeuroTechX/moabb/releases.atom`
- **BrainFlow** — [brainflow-dev/brainflow](https://github.com/brainflow-dev/brainflow) — Uniform library to obtain, parse, and analyze EEG, EMG, ECG, and other biosensor data across devices. _(latest: 5.22.2, 2026-05-22)_
  - Feed: `https://github.com/brainflow-dev/brainflow/releases.atom`
- **PyRiemann** — [pyRiemann/pyRiemann](https://github.com/pyRiemann/pyRiemann) — Riemannian geometry of covariance matrices for multivariate signal classification; a BCI decoding workhorse. _(latest: v0.11, 2026-04-16)_
  - Feed: `https://github.com/pyRiemann/pyRiemann/releases.atom`
- **CEBRA** — [AdaptiveMotorControlLab/CEBRA](https://github.com/AdaptiveMotorControlLab/CEBRA) — Learnable latent embeddings for joint behavioral and neural analysis (NeuroAI). _(latest: v0.6.1, 2026-05-30)_
  - Feed: `https://github.com/AdaptiveMotorControlLab/CEBRA/releases.atom`
- **NeuroKit2** — [neuropsychology/NeuroKit](https://github.com/neuropsychology/NeuroKit) — Python toolbox for neurophysiological signal processing (EEG, ECG, EDA, EMG). _(latest: v0.2.13, 2026-03-02)_
  - Feed: `https://github.com/neuropsychology/NeuroKit/releases.atom`
- **Kilosort** — [MouseLand/Kilosort](https://github.com/MouseLand/Kilosort) — Fast spike sorting with drift correction for extracellular electrophysiology. _(latest: v4.1.3, 2025-12-30)_
  - Feed: `https://github.com/MouseLand/Kilosort/releases.atom`
- **Lab Streaming Layer (liblsl)** — [sccn/liblsl](https://github.com/sccn/liblsl) — Library for real-time, time-synchronized streaming of multi-modal neural/biosensor data; backbone of many BCI rigs. _(latest: v1.18.0, 2026-06-20)_
  - Feed: `https://github.com/sccn/liblsl/releases.atom`
- **OpenBCI_GUI** — [OpenBCI/OpenBCI_GUI](https://github.com/OpenBCI/OpenBCI_GUI) — Cross-platform application for the OpenBCI Cyton and Ganglion biosensing boards. _(latest: v7.0.0-alpha1, 2025-11-21)_
  - Feed: `https://github.com/OpenBCI/OpenBCI_GUI/releases.atom`
