# Gajevids Schema

Provides YAML validation and autocompletion for `gajevids.yml` used in Gajevids video composition.

## Usage

1. Open or create a `gajevids.yml` file.
2. Start editing — schema validation and autocompletion will be available.

## Features

- Full schema validation based on `gajevids.schema.json`
- Autocompletion for fields like `videos`, `transitions`, and `timeline`

## Example

```yaml
output: output.mp4
fps: 30
videos:
  a: intro.mp4
  b: outro.mp4
timeline:
  - video: a
  - transition: fadeblack
  - video: b
```
