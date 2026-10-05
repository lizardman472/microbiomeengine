# Bioconductor readiness assessment

Assessed 5 October 2026 against the current official contributor guidance and the actual tester source. This package has not been submitted to Bioconductor. BiocCheck, Bioconductor development-environment checks and cross-platform submission checks have not been run.

## Effort and fit

The engine is a plausible software-package candidate: it uses TreeSummarizedExperiment and public mia/miaViz APIs, separates reusable analysis functions from the interface, and has synthetic tests and reproducible exports. Shiny packages are eligible, subject to specific architecture and documentation requirements. The proposal should explain the added value of explicit measurements, study/design gates and replay alongside related miaverse dashboards, rather than claim a new statistical method. [Submission criteria](https://contributions.bioconductor.org/bioconductor-package-submissions.html), [Shiny guidance](https://contributions.bioconductor.org/shiny.html).

Our planning estimate is **5–10 focused developer-days** for a submission candidate, assuming the existing calculations work with development dependencies. This is an estimate from the gaps below, not measured effort or a commitment. Licence clarification, platform failures, dependency drift or reviewer changes could extend it. External review time is separate; the guide describes reviews commonly taking 2–6 weeks, without guaranteeing acceptance or a release date. [Review process](https://contributions.bioconductor.org/bioconductor-package-submissions.html).

## Observed gaps and bounded work

| Area | Observed source | Work before submission |
| --- | --- | --- |
| Executable vignette | No vignettes directory or VignetteBuilder | Build a synthetic end-to-end Rmd vignette with evaluated analysis/export, method references, limitations and session information. |
| API examples and result structure | 40 exports, five grouped Rd pages; only microbiomeengine.Rd has examples, limited to example_project and its mass summary | Add useful runnable examples and document project/result structures. Grouped help pages can remain. |
| Example-data provenance | Three original synthetic files in inst/extdata; no inst/scripts generation/provenance record | Document their construction, units and intended validation role. |
| Submission metadata | Version 0.1.0, one-sentence Description, no biocViews or NEWS | Prepare submission version 0.99.0, fuller Description, valid biocViews and changelog; preserve true contact and new repository URLs. |
| Shiny construction API | run_app immediately calls shiny::runApp; UI/server code is already under R | Provide a documented function returning a Shiny app object; keep launching as an explicit user step. |
| Build/check environment | Windows release dependencies tested; no BiocCheck or devel/platform submission runs | Full build/check including vignette, BiocCheckGitClone and new-package BiocCheck in current devel; fix actual errors/warnings/notes and test supported platforms. |
| Tester conveniences | install.R, .Rprofile, Rproj and feedback templates are in tester GitHub source and excluded from the R build where relevant | Keep installer/development conveniences outside the submission source/default branch structure; examples assume dependencies already installed. |
| Licence and provenance | GPL-3 engine, separately installed dependencies; GPL-version boundary disclosed | Resolve or obtain authoritative clarification on GPL-2-only/GPL-3 combined distribution; record AI-assisted development and adapted-source provenance in code and submission as required. |

Documentation and data requirements come from the [documentation chapter](https://contributions.bioconductor.org/docs.html); metadata from [DESCRIPTION requirements](https://contributions.bioconductor.org/description.html). Environment, package size/runtime and repository cleanliness are governed by [general development requirements](https://contributions.bioconductor.org/general.html). App-return behavior is described in [Shiny guidance](https://contributions.bioconductor.org/shiny.html). AI/source disclosure and human maintenance responsibility are in the [AI and third-party policy](https://contributions.bioconductor.org/ai-policy-third-party.html). The licence boundary is detailed in [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).

## Proposed preparation sequence

1. Clarify licence compatibility and document AI/source provenance; agree on the contribution compared with miaDash and related tools.
2. Add executable vignette, examples, data provenance, metadata and the app-construction API.
3. Run devel/full BiocCheck and platform checks, repair findings, and collect tester feedback.
4. Submit through the current BiocContributions process, respond to review, and maintain the package and support responses afterward. Submission is a future user-authorised action.

The submission process changed in June 2026 to BiocContributions with R-universe-backed checks; the older Bioconductor/Contributions tracker is frozen for new issues. [Official process update](https://blog.bioconductor.org/posts/2026-06-15-new-submission-process-with-Runiverse/index.html).

The current 17-test and replay results are useful starting evidence, but do not substitute for these submission checks. No need to finish every proposed analysis module before assessing a bounded, documented MetaPhlAn package.
