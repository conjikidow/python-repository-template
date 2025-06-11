# python-repository-template

[![uv](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/uv/main/assets/badge/v0.json)](https://github.com/astral-sh/uv)
[![Ruff](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/ruff/main/assets/badge/v2.json)](https://github.com/astral-sh/ruff)

This is a template repository for Python projects.

## GitHub Actions Permissions Setup

To enable GitHub Actions to run properly in your repository, you need to adjust the default permissions granted to the `GITHUB_TOKEN`. This is especially important for **private repositories**.

Follow these steps to configure the permissions:

1. Go to the **Settings** tab of your repository.
2. On the left-hand menu, select **Actions/General**.
3. Under the **Workflow permissions** section, ensure the following options are selected:
   - **`Read and write permissions`**: This grants read and write access to the repository for all scopes.
   - **`Allow GitHub Actions to create and approve pull requests`**: This allows GitHub Actions to create pull requests.
4. Save the changes.

![GitHub Actions permissions setup screenshot](https://github.com/user-attachments/assets/da55e896-e087-486e-aadc-7fc1283dc652)

These settings are **necessary only for private repositories**. For public repositories, this configuration is not required.

## Project Name Setup

Replace `project-name` with your project name in the following files:

- `pyproject.toml`

  ```toml
  [project]
  name = "project-name"  # Replace with your project name
  version = "0.1.0"
  description = "Add your description here"
  readme = "README.md"
  requires-python = ">=3.13"
  dependencies = []
  ```

- `.bumpversion.toml`

  ```toml
  [[tool.bumpversion.files]]
  filename = "uv.lock"
  search = 'name = "project-name"\nversion = "{current_version}"'  # Replace with your project name
  replace = 'name = "project-name"\nversion = "{new_version}"'     # Replace with your project name
  regex = true
  ```

## Pre-commit Hooks Setup

To enable pre-commit hooks in your repository, you need to install `pre-commit` by running the following command:

```console
uv run pre-commit install
```
