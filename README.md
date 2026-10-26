# Mouse DRG paclitaxel label audit

A standalone Terputer research project containing an [executed Jupyter notebook](notebooks/terputer-paclitaxel-drg.ipynb), [reproducible analysis script](research/transcriptomics/gse230454-459/analysis.py), [source manifest](research/transcriptomics/gse230454-459/sample_manifest.tsv), and [claim-linked evidence brief](research/paclitaxel-drg-label-audit/generated/white-paper.md). The [generation receipt](research/paclitaxel-drg-label-audit/generated/generation-receipt.json) and [notebook execution receipt](research/execution-receipts/terputer-paclitaxel-drg.json) bind the report to its recorded outputs.

The GSE230459 sample titles say `Pax`, but their treatment-protocol fields say saline. The exposure label is provisional. The TPM contrast is descriptive; it does not establish a paclitaxel effect or a reproducible pathway. See the [methods and limitations](research/transcriptomics/gse230454-459/README.md).

## Use in your report fork

Fork this repository to your GitHub account with the same repository name, `terpedia-paclitaxel-drg-label-audit`. In your own `terpedia-report` fork, attach the project with the Terputer `add_research_project_submodule` tool using slug `paclitaxel-drg-label-audit`. It will appear at `projects/paclitaxel-drg-label-audit`.

To reproduce the notebook in a Codespace or local clone, install `requirements.txt`, then run:

```sh
python notebook-runner.py notebooks/terputer-paclitaxel-drg.ipynb . 180 '["research/transcriptomics/gse230454-459/results/sample_qc.tsv","research/transcriptomics/gse230454-459/results/background_summary.json","research/transcriptomics/gse230454-459/results/marker_descriptive.tsv","research/transcriptomics/gse230454-459/results/analysis_summary.json"]'
node report-generator.mjs research/transcriptomics/gse230454-459/report-spec.json
```

The script downloads the two processed GEO workbooks and verifies their SHA-256 values. The input workbooks are excluded from Git.
