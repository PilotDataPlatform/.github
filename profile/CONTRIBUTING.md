# Contributing to Pilot Data Platform

## Styleguides

### Python Development

#### General

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

### JavaScript Development
