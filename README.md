# Fantasy API

A Python library for fetching, organizing, storing, and serving fantasy football data locally.

Fantasy API provides a reusable data layer for applications that need access to fantasy football player, team, match, and performance data. It fetches data from external sources, normalizes and stores it locally, and can optionally expose the stored data through a local API.

It was originally built as the data layer for [Fantasy RL](https://github.com/tesfayecf/fantasy-rl), a reinforcement learning project for fantasy football management.

## Features

* Fetch fantasy football data from external sources
* Store datasets locally for reliable and repeatable access
* Update and refresh local data using the included update utilities
* Provide structured access to player, team, match, and performance data
* Optionally serve locally stored data through an API
* Designed as a reusable Python library
* Suitable for machine learning and sports analytics workflows
* Local-first architecture for development and experimentation

## Architecture

```text
fantasy-api/
├── common/          # Shared data and configuration
├── src/             # Library and API implementation
├── update.py        # Data update utilities
├── pyproject.toml   # Project configuration
├── requirements.txt # Dependencies
└── setup.py         # Package configuration
```

The project separates data collection from data consumption. External data is fetched and processed before being stored locally, allowing downstream applications to work against a consistent local dataset rather than repeatedly depending on external data sources.

## Getting Started

### Requirements

* Python 3.10+
* [uv](https://docs.astral.sh/uv/) or pip

### Installation

Clone the repository:

```bash
git clone https://github.com/tesfayecf/fantasy-api.git
cd fantasy-api
```

Install dependencies with `uv`:

```bash
uv sync
```

Or install using pip:

```bash
pip install -r requirements.txt
```

## Updating Data

The repository includes an update utility for fetching and refreshing the local dataset.

```bash
python update.py
```

The update process retrieves the available fantasy football data and updates the local data used by the library and local API.

## Related Projects

### Fantasy RL

Reinforcement learning for fantasy football management.

https://github.com/tesfayecf/fantasy-rl

## License

See the [LICENSE](./LICENSE) file for license information.
