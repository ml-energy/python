# mlenergy

Namespace package for the [ML.ENERGY](https://ml.energy) Python ecosystem.

This distribution contains no code of its own. It exists to give the ecosystem a single PyPI handle and to install its constituent packages as a bundle.

## Install

`pip install mlenergy` alone installs nothing — every subpackage is opt-in:

```bash
pip install mlenergy[all]         # all subpackages
pip install mlenergy[data]        # data toolkit (https://ml.energy/data)
pip install mlenergy[benchmark]   # benchmark runner (https://github.com/ml-energy/benchmark)
```

The Python import namespace `mlenergy` is a [PEP 420 implicit namespace package](https://peps.python.org/pep-0420/). Each subpackage (`mlenergy.data`, ...) is shipped by its own distribution and merged at import time.

| distribution | imports as | repo |
|---|---|---|
| `mlenergy-data` | `mlenergy.data` | [ml-energy/data](https://github.com/ml-energy/data) |
| `mlenergy-benchmark` | `mlenergy.benchmark` | [ml-energy/benchmark](https://github.com/ml-energy/benchmark) |

## Adding a new subpackage

1. New repo publishes a `mlenergy-<name>` distribution that ships `mlenergy/<name>/` (with no top-level `mlenergy/__init__.py`).
2. Add `mlenergy-<name>` to this package's `dependencies` and to `[project.optional-dependencies]`.
3. Cut a new release of `mlenergy`.
