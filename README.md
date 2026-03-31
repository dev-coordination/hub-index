# Retriever Hub Index

Module registry for Retriever Hub. Used by APIs like `hub.use()` to discover modules.

## Structure

```
modules/
  {org}/
    {module-name}.toml
```

## Module entry format

```toml
[module]
repo = "https://github.com/org/module-name"
description = "Short description"
author = "Author Name"
license = "MIT"
tags = ["tag1", "tag2"]

[module.links]
docs = "https://..."
support = "https://..."
```

## Submitting a module

Open a PR adding `modules/{org}/{name}.toml`. Requirements:

- Repo is publicly accessible
- Repo contains `pyproject.toml` with a `[tool.retriever.module]` section
- At least one semver Git tag (e.g. `v1.0.0`)

## Usage

```python
from retriever import hub

Flow = hub.use("org/module-name:FlowName")
```
