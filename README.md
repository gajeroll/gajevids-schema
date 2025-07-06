# Gajevids Schema

Provides YAML validation and autocompletion for `gajevids.yml` used in Gajevids video composition.

## Usage

1. Open or create a `gajevids.yml` file.
2. Start editing — schema validation and autocompletion will be available.

## Features

- Full schema validation based on `gajevids.schema.json`
- Autocompletion for fields like `videos`, `transitions`, and `timeline`

## Example

<!-- start example_gajevids.yml -->

```yaml
# gajevids configuration example (v0)

# Schema version (default is 0 if omitted)
version: 0

# [Required]
# Output video path
output: "output.mp4"

# Frame rate (defaults to 30)
fps: 24

# Resolution (defaults to 1280x720)
resolution:
  w: 1280
  h: 720

# [Required]
# Video source files
videos:
  intro: "intro.mp4"
  main: "main_content.mp4"
  outro: "outro.mp4"

# [Required]
# Transition definitions
transitions:
  fade:
    type: fadeblack
    duration: 0.5
  slide:
    type: slideleft
    duration: 1.0
  fancy:
    type: zoomin
    duration: 0.8

# [Required]
# Default transition when none specified
default_transition: fade

# [Required]
# Timeline - sequence of videos and transitions
timeline:
  - video: intro
  - transition: fancy
  - video: main
  - transition: slide
  - video: outro
```

<!-- end example_gajevids.yml -->
