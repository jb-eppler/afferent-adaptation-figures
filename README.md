# Afferent-Gain Adaptation — Figure Notebooks

Code used to generate figures for the two-mechanism neural adaptation model in:

Johannes P.-H. Seiler, Jens-Bastian Eppler, Saman Seifpour, Lukas C. Wiese, Til Ole Bergmann, Florian Müller-Dahlhaus, Oliver Tüscher, Simon Rumpel.
Boredom and the representation of information content in the neocortex.
bioRxiv 2026.07.09.737454; doi: https://doi.org/10.64898/2026.07.09.737454 

1. **Recurrent Hebbian facilitation** on the network outputs (`eff` on `W`,
   driven by `outer(r, r)`, recovering toward 1 with `TAU_HEBBIAN`).
2. **Afferent (feedforward) gain plasticity** — a per-input-synapse gain
   vector `g`, driven by the raw input magnitude, recovering toward 1 with
   `TAU_AFFERENT`.

Both notebooks are self-contained: the stimulus/validation sequences are
hardcoded in-notebook, so no external data files are required.

## Notebooks

- **`figure_example_plots_afferent.ipynb`** — runs the model for a single
  parameter setting across `N_NETWORKS` random networks and produces the
  full example-plot suite (entropy-binned activity heatmaps, stimulus
  correlation matrices, PCA colourings, PCA trajectories, boring vs.
  max-entropy activity panels) as PNG + EPS.
- **`figure_scan_afferent.ipynb`** — sweeps the two adaptation rates
  (`ETA_HEBBIAN` × `ETA_AFFERENT`) over a 9×9 grid, computes six
  discriminability/regime metrics plus two activity-change metrics per
  condition, and saves one heatmap per metric plus a binary working-regime
  map.

## Requirements

- Python 3.10+
- numpy
- scipy
- matplotlib
- scikit-learn
- jupyter

Install with:

    pip install numpy scipy matplotlib scikit-learn jupyter

## Running

Open either notebook in Jupyter and run all cells top to bottom:

    jupyter notebook figure_example_plots_afferent.ipynb

Figures are written to a folder created automatically in the same directory
as the notebook (e.g. `./output_examples_afferent/`). The scan notebook runs
a large number of simulations (9×9 conditions × `N_NETWORKS` networks each)
and can take a while — reduce `N_NETWORKS` in the settings block for a
quicker/coarser check.

## Citation

If you use this code, please cite:

Johannes P.-H. Seiler, Jens-Bastian Eppler, Saman Seifpour, Lukas C. Wiese, Til Ole Bergmann, Florian Müller-Dahlhaus, Oliver Tüscher, Simon Rumpel.
Boredom and the representation of information content in the neocortex.
bioRxiv 2026.07.09.737454; doi: https://doi.org/10.64898/2026.07.09.737454 

## License

MIT — see `LICENSE`.
