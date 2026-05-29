# sport-os-ai — Stack Conventions

## Stack
- Python 3.11+, PyTorch 2.x or scikit-learn
- pandas, NumPy, Polars for data processing
- FastAPI for model-serving endpoints
- MLflow or Weights & Biases for experiment tracking

## Code Conventions
- Ruff for formatting and linting
- Type hints required; Pydantic for config objects
- Notebooks in notebooks/; production code in src/
- Large model artifacts tracked via DVC or Git LFS

## Testing
- pytest; model tests use small fixture datasets
- Data validation assertions before training loops

## Git
- Conventional commits (feat:, fix:, exp: for experiments)
- Model artifacts (.pt, .pkl, .onnx) excluded via .gitignore
