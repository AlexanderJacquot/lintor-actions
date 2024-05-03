# SQL Linting Action

This GitHub Action provides automated linting for SQL and Python files using SQLFluff and Flake8, respectively. It supports multiple programming languages, allowing customization of the linting process through various configurable inputs.

## Features

- **Support for Multiple Languages**: Currently supports SQL and Python.
- **Customizable SQL Dialects**: Specify different SQL dialects for SQLFluff.
- **Configurable Linting Rules**: Ability to provide a custom configuration file for SQLFluff.

## Inputs

### `directory`
- **Description**: Directory containing SQL files to lint
- **Required**: Yes
- **Default**: `dir/`

### `language`
- **Description**: Programming language to lint. Possible choices are: SQL, Python
- **Required**: Yes

### `dialect`
- **Description**: SQL dialect to use for linting with SQLFluff
- **Required**: No

### `config`
- **Description**: Path to SQLFluff configuration file
- **Required**: No

## Outputs

### `output`
- **Description**: Output from SQLFluff

## Usage

To use this action in your workflows, add the following steps to your `.github/workflows` YAML file:

```yaml
jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: your-username/sql-lint-action@main # Replace with actual usage path
        with:
          directory: 'path/to/your/sql/or/python/files'
          language: 'SQL'  # Or 'Python'
          dialect: 'ansi'  # Optional for SQL
          config: '.sqlfluff'  # Optional
