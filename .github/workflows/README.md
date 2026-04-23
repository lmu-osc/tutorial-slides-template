# GitHub Workflows

This folder contains the GitHub Actions workflows that support the template repository. Together, they help keep the project tidy, validate key metadata, and publish the Quarto site when changes land on the main branch.

The workflows are intentionally small and focused:

- `filename-checks.yml` runs on pull requests, pushes to `main`, and manual dispatch. It checks file names and paths against the repository's filename rules, including the limits configured in `.filenameignore`.
- `citation-check.yml` runs when `CITATION.cff` changes on `main`, or when started manually. It validates that the citation file is still correct before the change is merged.
- `publish.yaml` runs on pushes to `main`, on a weekly schedule, and when started manually. It renders the Quarto site and publishes the output to GitHub Pages.
- `style.yaml` runs manually. It formats the repository's R and Quarto-related files with `styler`, then commits and pushes any resulting changes back to the branch.

If a workflow fails, the README for the repository root usually points to the most likely file or configuration to inspect next.

