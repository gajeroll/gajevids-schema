# Gajevids Schema

Provides YAML validation and autocompletion for `gajevids.yml`, the configuration file used in [Gajevids](https://github.com/gajeroll/homebrew-gajevids) — a command-line tool for automated FFmpeg video composition.

## What is Gajevids?

Gajevids is a CLI tool that automatically composes multiple video files using YAML configuration. You define the input videos, transitions, and sequence using simple, human-readable files.

### Key Features

- **Simple YAML Configuration** — Easy-to-read syntax for video editing
- **Automatic Timeline Calculation** — Start times are automatically computed
- **Rich Transitions** — Supports fade, dissolve, slide, and many more
- **Cross-platform** — Works on macOS, Linux, and Windows (via WSL)

## Getting Started with Gajevids

Install the Gajevids CLI using [Homebrew](https://brew.sh):

```bash
# Add the Gajevids tap
brew tap gajeroll/gajevids

# Install the CLI
brew install gajevids
````

Once installed, you can run:

```bash
# Generate an example config file
gajevids --example

# Compose videos based on a YAML config
gajevids example_gajevids.yml

# View help
gajevids --help
```

## Features of This Extension

This VSCode extension provides:

* Full schema validation for `gajevids.yml`
* Autocompletion for keys like `videos`, `transitions`, `timeline`
* Hover tooltips and error highlighting based on `gajevids.schema.json`

## How to Use

1. Open or create a file named `gajevids.yml` (or `gajevids.yaml`) in VSCode.
2. Start editing — validation and suggestions will appear automatically.

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

# Additional FFmpeg arguments
ffmpeg_args:
  "-movflags": "+faststart"
  "-pix_fmt": "yuv420p"
  "-c:v": "libx264"
  "-profile:v": "main"
  "-preset": "medium"
```

<!-- end example_gajevids.yml -->
