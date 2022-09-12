# Contributing to Pilot Data Platform
Welcome and thank you for your interest in Pilot!

This document outlines contribution guidelines for any interested party that wishes to contribute to Pilot. 


#### Table Of Contents
🚧 UNDER CONSTRUCTION 🚧

[Styleguides](#styleguides)
  * [Python Development](#python-development)
    * [General Python Guidelines](#general-python-guidelines)
    * [Editor Config](#editor-config)
    * [Git Hooks](#git-hooks-pre-commit)
  * [Dockerfiles](#dockerfiles)
  * [JavaScript Development](#javascript-development)
  * [Git Commit Messages](#git-commit-messages)
[How to Contribute?](#how-to-contribute)
  * [Issues](#issues)
  * [Pull Requests](#pull-requests)


## Styleguides

### Python Development

#### General Python Guidelines

- Start with reading PEP 8 for essential rules. Sometimes it’s good to read it several times :slight_smile:.
- Check PEP 257 regarding doc strings formatting.
- Limit all lines to a maximum of 120 characters. This goes in contrast to PEP 8, but this gives more flexibility to write proper variable names or logging strings. Also nowadays most screens do not lack horizontal space.
- Use only UNIX newlines (\n), not Windows style (\r\n).
- When TODO is added it should be either linked to a JIRA issue or contain your name. In this case it’s easier to find the author or track the status. Examples:
  ```python
  # TODO: Here goes a description and a link https://indocconsortium.atlassian.net/browse/PROJECT-ID 

  # TODO: Here goes a description and if it doesn't fit one line it continues on a new line
  #  with a link https://indocconsortium.atlassian.net/browse/PROJECT-ID

  # TODO(yourname): Here goes a description
  ```
- Do not shadow a built-in or reserved word. This also applies to shadowing names defined in outer scopes. It makes code harder to understand. Examples:
  ```python
  id = get_id()  # Wrong, shadows `id` built-in
  id_ = get_id()  # Correct
  ```
- Each module/package should have a test file under the tests folder following the same structure so that it’s easier to find what part is tested and where unit tests must be placed. Example:
  ```
  ├── app
  │   ├── commons
  │   │   ├── __init__.py
  │   │   ├── download_manager.py
  │   │   ├── locks.py
  │   └── models
  │       ├── __init__.py
  │       ├── base_models.py
  │       └── data_download_models.py
  └── tests
      ├── __init__.py
      ├── commons
      │   ├── __init__.py
      │   ├── test_download_manager.py
      │   ├── test_locks.py
      └── models
          ├── __init__.py
          ├── test_base_models.py
          └── test_data_download_models.py
  ```
 
#### Editor Config
[EditorConfig](https://editorconfig.org/) helps maintain consistent coding styles for multiple developers working on the same project across various editors and IDEs. 
Some IDEs are already bundled with native support for EditorConfig, some - not. Support for your editor can be checked [here](https://editorconfig.org/#pre-installed).

Simple example of .editorconfig file that can be put into the root folder per each project.

```
root = true

[*]
charset = utf-8
tab_width = 4
indent_style = space

[*.py]
end_of_line = lf
indent_size = 4
trim_trailing_whitespace = true
insert_final_newline = true

[*.{yml,yaml}]
end_of_line = lf
indent_size = 2
trim_trailing_whitespace = true
insert_final_newline = true
```

#### Git Hooks (pre-commit)

Pre-commit is a framework that can run different git hook scripts that perform linting and formatting before every commit. This helps each developer to follow defined guides and focus more on writing code rather than formatting it.

##### Installation

1. Install package `pip install pre-commit`.
2. Include pre-commit as a dev dependency. 
3. Add `.pre-commit-config.yaml` file with configuration.
4. Install git hook scripts `pre-commit install`.

By default, hooks will run each time when git commit is performed and only for files that are staged for the commit. To run checks against specific files use pre-commit run --files path/to/file or recursively against folders pre-commit run --files path/to/folder/**/*.

##### Config

Simple example of `.pre-commit-config.yaml` file that can be put into the root folder per each project.

```yaml
repos:

  - repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v4.0.1
    hooks:
      - id: check-added-large-files
      - id: check-docstring-first
      - id: check-merge-conflict
      - id: check-toml
      - id: check-yaml
      - id: double-quote-string-fixer
      - id: end-of-file-fixer
      - id: requirements-txt-fixer
      - id: trailing-whitespace

  - repo: https://github.com/psf/black
    rev: 21.10b0
    hooks:
      - id: black
        args: [
            '--line-length=120',
            '--skip-string-normalization',
        ]

  - repo: https://github.com/pycqa/isort
    rev: 5.10.0
    hooks:
      - id: isort
        args: [
            '--profile=black',
            '--filter-files',
            '--force-single-line-imports',
            '--reverse-relative',
        ]

  - repo: https://gitlab.com/pycqa/flake8
    rev: 3.9.2
    hooks:
      - id: flake8
        additional_dependencies: [
            'pycodestyle==2.7.0',  # E,W
            'pyflakes==2.3.0',  # F
            'mccabe==0.6.1',  # C
            'flake8-bugbear==21.3.2',  # B
            'flake8-builtins==1.5.3',  # A
            'flake8-comprehensions==3.3.1',  # C4
            'flake8-debugger==4.0.0',  # T1
            'flake8-logging-format==0.6.0',  # G
            'flake8-print==4.0.0',  # T0
        ]
        args: [
            '--select=E,W,F,C,B,A,C4,T1,G,T0',
            '--ignore=W503,B008,B305,A003,G003,G004',
            '--max-complexity=10',
            '--max-line-length=120',
        ]

  - repo: https://github.com/myint/docformatter
    rev: v1.4
    hooks:
      - id: docformatter
        args: [
            '--wrap-summaries=120',
            '--wrap-descriptions=120',
            '--in-place',
        ]
```


Above config contains multiple steps with several checks:
1. Run basic sanity checks from pre-commit-hooks.
2. Format code using Black formatter.
3. Perform additional checks using Flake8 and its extensions to follow PEP 8 and best practices.
4. Format docstrings using docformatter according to PEP 257.

#### Dockerfiles

🚧 UNDER CONSTRUCTION 🚧

### JavaScript Development

🚧 UNDER CONSTRUCTION 🚧


### Git Commit Messages

🚧 UNDER CONSTRUCTION 🚧

## How to contribute?

🚧 UNDER CONSTRUCTION 🚧

### Issues

🚧 UNDER CONSTRUCTION 🚧

### Pull Requests

🚧 UNDER CONSTRUCTION 🚧


