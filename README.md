# sport-os-ai

[![CI](https://github.com/valentinmariusdynu-tech/sport-os-ai/actions/workflows/ci.yml/badge.svg)](https://github.com/valentinmariusdynu-tech/sport-os-ai/actions/workflows/ci.yml)

ML/AI model training, evaluation, and inference services for the Sport-OS platform.

## Stack
Python 3.11 · PyTorch · FastAPI · MLflow · pandas · scikit-learn · uv

## Architecture
```
src/
├── models/       — PyTorch model definitions
├── training/     — training loops and callbacks
├── inference/    — FastAPI inference service
├── data/         — dataset loaders and transforms
├── evaluation/   — metrics and evaluation scripts
└── serve.py      — inference server entrypoint
experiments/      — MLflow experiment configs
notebooks/        — exploratory analysis (not shipped)
tests/
```

## Quick Start
```bash
uv sync
uv run python -m src.serve         # start inference API
uv run python -m src.training.run  # launch training
```

## Dev Commands
```bash
uv run pytest -m "not slow"       # fast tests only
uv run ruff check . --fix        # lint + autofix
uv run mypy src/                  # type check
uv run mlflow ui                  # experiment tracking UI
```

## Related Repos
| Repo | Role |
|---|---|
| [sport-os-backend](https://github.com/valentinmariusdynu-tech/sport-os-backend) | Consumes inference API |
| [sport-os-mobile](https://github.com/valentinmariusdynu-tech/sport-os-mobile) | Displays AI insights |
| [sport-os-infra](https://github.com/valentinmariusdynu-tech/sport-os-infra) | ML model deployment |
| [sport-os-docs](https://github.com/valentinmariusdynu-tech/sport-os-docs) | Documentation |
