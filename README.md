# langchain-deepagents-tensorlake

[Tensorlake](https://tensorlake.ai) sandbox provider for [Deep Agents](https://github.com/langchain-ai/deepagents).

## Installation

```bash
pip install langchain-deepagents-tensorlake
```

## Usage

```python
from tensorlake.sandbox import Sandbox
from langchain_deepagents_tensorlake import TensorlakeSandbox
from deepagents.backends import CompositeBackend

# Create a Tensorlake sandbox
sandbox = Sandbox.create(api_key="your-api-key")
backend = TensorlakeSandbox(sandbox=sandbox)

# Use directly as a DeepAgents backend
# or wrap with CompositeBackend for routing
```

With the Deep Agents CLI (`deepagents-code`), set:

```bash
export TENSORLAKE_API_KEY=your-api-key
deepagents-code --sandbox tensorlake
```

> **Note:** CLI integration requires `deepagents-code` to be configured with
> a custom `sandbox_factory` that maps `"tensorlake"` to `TensorlakeSandbox`.
> See the [examples](examples/) directory for a complete setup.

## Development

```bash
uv sync --all-groups
uv run pytest tests/unit_tests/
uv run ruff check .
```

## License

MIT
