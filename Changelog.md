# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## Unreleased

## Added
- Added the [`ParallelModel`](https://repro.readthedocs.io/en/latest/api/repro.models.model.html#repro.models.model.ParallelModel) class as an easy abstraction over the `joblib` library for parallel computation.

## [v0.1.5](https://github.com/danieldeutsch/repro/releases/tag/v0.1.5) - 2022-03-21
## Added
- Added [BaryScore, InfoLM, and DepthScore](https://repro.readthedocs.io/en/latest/models/colombo2021.html)
- Added ability to set `beam_size` and `nbest` parameters for BART.
- Added GPU support for MoverScore

### Changed
- Changed the backend implementation of MoverScore to use a non-IDF dict based version.
- Changed the default BLEURT version to use `"BLEURT-20"` instead of `"bleurt-base-128"` and using length-batched optimization. 

## [v0.1.4](https://github.com/danieldeutsch/repro/releases/tag/v0.1.4) - 2022-01-29
### Changed
- Relaxed the `datasets` version requirement to match the GEM Metrics library
- Moved some dependencies into `dev-requirements.txt`

### Fixed
- Removed warnings that may happen if the Docker clients are not closed.

## [v0.1.3](https://github.com/danieldeutsch/repro/releases/tag/v0.1.3) - 2022-01-22
### Added
- Added [CLIPScore](https://repro.readthedocs.io/en/latest/models/hessel2021.html)
- Added a [QA SRL Parser](https://repro.readthedocs.io/en/latest/models/fitzgerald2018.html)
- Added [SUPERT](https://repro.readthedocs.io/en/latest/models/gao2020.html)
- Added [BLANC](https://repro.readthedocs.io/en/latest/models/vasilyev2020.html)
- Added [METEOR](https://repro.readthedocs.io/en/latest/models/denkowski2014.html)
- Added a role question generator from [Pyatkin et al. (2021)](https://repro.readthedocs.io/en/latest/models/pyatkin2021.html)
- Added using [Prism](https://repro.readthedocs.io/en/latest/models/thompson2020.html) as an MT model
- Added [COMET](https://repro.readthedocs.io/en/latest/models/rei2020.html)

### Fixed
- Fixed an error in [Lite3Pyramid](https://repro.readthedocs.io/en/latest/models/zhang2021.html) by updating to a newer version of the code.

## [v0.1.2](https://github.com/danieldeutsch/repro/releases/tag/v0.1.2) - 2021-10-07
### Changed
- Changed backend of Lite3Pyramid to use our own fork of the official repo with some modifications.

## [v0.1.1](https://github.com/danieldeutsch/repro/releases/tag/v0.1.1) - 2021-10-05
### Added
- Added [Benepar](https://repro.readthedocs.io/en/latest/models/kitaev2019.html)
- Added [Lite3Pyramid](https://repro.readthedocs.io/en/latest/models/zhang2021.html)
- Added [BARTScore](https://repro.readthedocs.io/en/latest/models/yuan2021.html)

### Changed
- Fixed silly variable name typo: `DOCKERHUB_REPRO` to `DOCKERHUB_REPO`

## [v0.1.0](https://github.com/danieldeutsch/repro/releases/tag/v0.1.0) - 2021-08-10
### Added
- Added [DAE](https://repro.readthedocs.io/en/latest/models/goyal2020.html)
- Adding [FactCC and FactCCX](https://repro.readthedocs.io/en/latest/models/kryscinski2019.html)
- Added utilities to remove empty inputs and insert values at specific indices
- Added automatically building and publishing model images
- Added a command to pull default Docker images for each model
- Added [SummaQA](https://repro.readthedocs.io/en/latest/models/scialom2019.html)
- Added [NUBIA](https://repro.readthedocs.io/en/latest/models/kane2020.html)
- Added [Prism](https://repro.readthedocs.io/en/latest/models/thompson2020.html)

### Changed
- BERTScore now returns 0 for its metrics if the input is empty. 
- BLEURT now returns the mean and max scores over the references.
- Changing Lewis et al. (2020) to download CNN/DM and XSum models by default
- Changing Liu et al. (2019) to download all models by default  

## [v0.0.3](https://github.com/danieldeutsch/repro/releases/tag/v0.0.3) - 2021-08-04
### Added
- Added [BLEURT](https://repro.readthedocs.io/en/latest/models/sellam2020.html)
- Added [BERTScore](https://repro.readthedocs.io/en/latest/models/zhang2020.html)
- Added [BLEU and SentBLEU](https://repro.readthedocs.io/en/latest/models/papineni2002.html)
- Added [QuestEval](https://repro.readthedocs.io/en/latest/models/scialom2021.html)
- Added [MoverScore](https://repro.readthedocs.io/en/latest/models/zhao2019.html)
- Added [FEQA](https://repro.readthedocs.io/en/latest/models/durmus2020.html)

### Changed
- Changed the QAEval interface to match other text generation metrics.
The backend was also changed to not rely on SacreROUGE.

## [v0.0.2](https://github.com/danieldeutsch/repro/releases/tag/v0.0.2) - 2021-07-30
### Added
- Added a `RecipeGenerationModel` class
- Added a [recipe generation model](https://repro.readthedocs.io/en/latest/models/dugan2020.html) from [Dugan et al. (2020)](https://arxiv.org/abs/2010.03070)
- Added a `TruecasingModel` class
- Added an RNN-based truecaser from [Susanto et al. (2016)](https://aclanthology.org/D16-1225/) based on an implementation [here](https://github.com/mayhewsw/pytorch-truecaser).
- Added the question-generation and question-answering models used in the [QAEval metric](https://arxiv.org/abs/2010.00490).
See [here](https://repro.readthedocs.io/en/latest/models/deutsch2021.html).
- Added [ROUGE](https://repro.readthedocs.io/en/latest/models/sacrerouge.html)
- Added `--predict-kwargs` arguments to the `predict` command
- Added support for running and writing evaluation metrics, for instance, ROUGE.
- Added a jsonl dataset reader (`JSONLinesDatasetReader`)
- Added the `SQuADv2Evaluation` metric
- Added the [BART-based sentence-guided models](https://repro.readthedocs.io/en/latest/models/dou2021.html) from [Dou et al. (2021)](https://arxiv.org/abs/2010.08014).
- Added the [LERC model](https://repro.readthedocs.io/en/latest/models/chen2020.html) from [Chen et al. (2020)](https://arxiv.org/abs/2010.03636)
- Added the [QAEval metric](https://repro.readthedocs.io/en/latest/models/deutsch2021.html)
- Adding a wrapper around the original Perl implementation of ROUGE.
See [here](https://repro.readthedocs.io/en/latest/models/lin2004.html)

### Changed
- Renamed the `--model-args`, `--dataset-reader-args`, and `--output-write-args` `predict` arguments to `--model-kwargs`, `--dataset-reader-kwargs`, and `--output-write-kwargs`.
- Renamed the `--output-file` argument in `predict` to `--output` to allow for output files or directories.

## [v0.0.1](https://github.com/danieldeutsch/repro/releases/tag/v0.0.1) - 2021-07-22
### Added
- Initial prototype of the library with `setup` and `predict` commands as well as implementations of [Gupta et al. (2020)](https://repro.readthedocs.io/en/latest/models/gupta2020.html), [Lewis et al. (2020)](https://repro.readthedocs.io/en/latest/models/lewis2020.html), and [Liu & Lapata (2019)](https://repro.readthedocs.io/en/latest/models/liu2019.html).
