# CLAUDE.md — sport-os-ai

## Purpose
ML/AI services for Sport-OS: model training, experiment tracking, and a FastAPI inference API consumed by sport-os-backend.

## Stack
- Python 3.11, PyTorch, FastAPI
- MLflow (experiment tracking), scikit-learn
- pandas, numpy
- uv (package manager)

## Key Directories
- `src/models/` — PyTorch model definitions
- `src/training/` — training loops, loss functions, callbacks
- `src/inference/` — FastAPI inference service
- `src/data/` — dataset loaders, transforms, preprocessing
- `src/evaluation/` — metrics and evaluation scripts
- `experiments/` — MLflow configs and run metadata
- `tests/` — pytest; mark expensive tests with `@pytest.mark.slow`

## Dev Commands
```bash
uv run python -m src.serve        # inference API
uv run pytest -m "not slow"       # skip GPU-heavy tests
uv run ruff check . --fix
uv run mypy src/
```

## Conventions
- Mark expensive tests with `@pytest.mark.slow`; CI skips them
- Model weights versioned via MLflow; never commit to git
- Inference API mirrors sport-os-backend's response envelope schema

## Related Repos
- [sport-os-backend](https://github.com/valentinmariusdynu-tech/sport-os-backend) — calls `/predict` endpoints
- [sport-os-infra](https://github.com/valentinmariusdynu-tech/sport-os-infra) — deploys model containers
