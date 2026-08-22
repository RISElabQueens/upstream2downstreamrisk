# Upstream2Downstream Replication Package

This replication package contains the notebooks and datasets used to reproduce the analyses for RQ1, RQ2, and RQ3. It was prepared as a clean copy from the working directory while keeping the original files unchanged.

## Contents

```text
upstream2downstream/
  notebooks/
    RQ1/    Upstream reporting and lifecycle analysis
    RQ2/    Downstream exposure and adoption analysis
    RQ3/    Dependabot evidence, classification, and analysis
  data/
    baseline/              Raw CVE, patch, artifact, dependency, and response data
    rq1/                   Reporting, severity, popularity, and lifecycle inputs
    rq1/transparent_data/  Transparent-reporting date inputs and supporting notebook
    rq1/external_release_nvd/
                            Fixed-release and NVD disclosure inputs
    rq2/                   RQ2 pairwise, exposure, burden, and stage datasets
    rq3/                   Dependabot evidence and classified datasets
```

The package intentionally excludes planning files, generated figures, generated paper tables, token files, and unrelated Markdown files.

## Running The Notebooks

Run notebooks from their own directory so the relative data paths resolve correctly. For example:

```bash
cd upstream2downstream/notebooks/RQ2
jupyter notebook
```

Recommended order:

1. RQ1: run notebooks `01` through `11` in `notebooks/RQ1`.
2. RQ2: run notebooks `01` through `08` in `notebooks/RQ2`.
3. RQ3: run notebooks `01` through `03` in `notebooks/RQ3`.

Some mining notebooks use the GitHub API. No GitHub token is included in this package. To rerun those mining steps, provide a token through the `GITHUB_TOKEN` environment variable or a local untracked token file.

## Reproducing Existing Results

Several mined and intermediate datasets are already included under `data/`. Therefore, notebooks that analyze existing data can be rerun without repeating all remote mining steps. Notebooks that re-mine GitHub data may produce updated results if repository state or API responses have changed.

Generated tables and figures can be recreated by running the analysis notebooks, but those outputs are not included in this package.

