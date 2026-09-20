# Paper Reproduction Lab

A structured, reproducible workspace for reading research papers, implementing their methods, running controlled experiments, and documenting what was learned.

## Goals

- Preserve the original paper and its citation information.
- Convert the paper into concise, searchable notes.
- Reimplement the method from clearly recorded assumptions.
- Run traceable experiments with fixed configurations and seeds.
- Compare reproduced results with the reported results.
- Record failures, deviations, and lessons learned.

## Current Status

**Project phase:** Repository initialized  
**Active reproduction:** None selected yet  
**Last updated:** 2026-09-20

### Progress Dashboard

| ID | Paper | Domain | Stage | Target Metric | Reproduced Metric | Status |
|---|---|---|---|---|---|---|
| — | No paper selected yet | — | Planning | — | — | Not started |

Status values: `Not started`, `Reading`, `Implementing`, `Running`, `Analyzing`, `Reproduced`, or `Blocked`.

### Repository Setup Checklist

- [x] Create repository structure
- [x] Add note and experiment templates
- [x] Define progress and logging conventions
- [ ] Select the first paper
- [ ] Save the paper and citation
- [ ] Write the first paper summary
- [ ] Reproduce the baseline result
- [ ] Document the final comparison

## Repository Structure

```text
.
├── papers/                 # Paper PDFs, citations, and source links
├── notes/                  # Reading notes and method summaries
├── experiments/            # Code, configurations, and per-run logs
├── results/                # Tables, figures, metrics, and comparisons
├── templates/              # Reusable note and experiment templates
├── PROGRESS.md             # Detailed chronological project log
└── README.md               # High-level status and navigation
```

For each paper, use the same short identifier across folders:

```text
papers/<paper-id>/
notes/<paper-id>/
experiments/<paper-id>/
results/<paper-id>/
```

Recommended paper ID format: `<first-author>-<year>-<short-title>`.

## Reproduction Workflow

1. **Register the paper**
   - Add the PDF when redistribution is permitted, otherwise add an official link.
   - Save complete citation metadata and the original code link, if available.
   - Record the paper version, publication venue, and access date.

2. **Read and decompose**
   - Copy `templates/paper-notes-template.md` into `notes/<paper-id>/README.md`.
   - Extract the research question, assumptions, method, datasets, metrics, and key claims.
   - List every detail that is missing or ambiguous.

3. **Prepare the environment**
   - Record the operating system, hardware, language/runtime, dependencies, and versions.
   - Fix random seeds and document nondeterministic operations.
   - Keep data acquisition and preprocessing steps explicit.

4. **Implement**
   - Reproduce the simplest reported baseline first.
   - Separate configuration from code.
   - Note every deviation from the paper or official implementation.

5. **Run experiments**
   - Create one immutable log per run using `templates/experiment-log-template.md`.
   - Save the exact command, commit, configuration, seed, runtime, and outputs.
   - Never overwrite a completed run; create a new run ID.

6. **Evaluate**
   - Compare the reproduced numbers with the paper under matching conditions.
   - Report uncertainty across multiple seeds where appropriate.
   - Include failures and negative results.

7. **Conclude**
   - Classify the outcome as `Reproduced`, `Partially reproduced`, `Not reproduced`, or `Inconclusive`.
   - Explain the evidence and remaining gaps.
   - Update both this dashboard and `PROGRESS.md`.

## Experiment Naming and Logging

Use run IDs in this format:

```text
<paper-id>__<experiment>__<YYYYMMDD-HHMM>__seed-<seed>
```

Each experiment log must include:

- Objective and hypothesis
- Repository commit
- Dataset and preprocessing version
- Environment and hardware
- Full configuration and command
- Random seed
- Start/end time and runtime
- Metrics and output paths
- Deviations, warnings, and failures
- Interpretation and next action

## Reproducibility Standard

A result is considered reproducible here only when another person can:

- obtain the required data legally;
- recreate the software environment;
- run the experiment from documented commands;
- trace a result to a specific commit and configuration;
- find raw and summarized metrics;
- understand all known deviations from the paper.

Large datasets, model weights, caches, secrets, and generated artifacts should not be committed directly. Store stable download instructions, checksums, and external locations instead.

## Progress Log

| Date | Update | Outcome | Next Step |
|---|---|---|---|
| 2026-09-20 | Initialized the repository, workflow, templates, and tracking system. | Ready for the first reproduction project. | Select and register the first paper. |

Detailed updates belong in [PROGRESS.md](PROGRESS.md). Keep this table limited to major milestones.

## Adding the First Paper

1. Choose a paper ID.
2. Create matching folders under `papers/`, `notes/`, `experiments/`, and `results/`.
3. Copy the two templates.
4. Add the paper to the Progress Dashboard.
5. Record the selection in `PROGRESS.md`.

## Principles

- Evidence over memory.
- Configuration over hidden defaults.
- Immutable run records over overwritten results.
- Honest failure reports over selective success.
- Respect paper licenses, dataset terms, and artifact redistribution rules.
