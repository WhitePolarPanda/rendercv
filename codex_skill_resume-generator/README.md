# Codex Skill: resume-generator

## What it does
Tailors a RenderCV YAML resume to a target role using an iterative edit loop that produces a revised YAML plus a Markdown change log, then renders a final PDF with the local RenderCV repo once approved.

## Setup
Install RenderCV (with PDF rendering support):

```bash
pip install "rendercv[full]"
```

If using a local repo checkout, install editable instead:

```bash
pip install -e C:\dev\rendercv
```

## Usage
Invoke via Codex by providing:
- A RenderCV YAML resume file path
- A Markdown file describing the target position

Codex will iterate revisions (YAML + change log) until you approve, then render the PDF:

```bash
python -m rendercv render "C:\path\to\Resume.yaml"
```

## Codex-specific assumptions
- Designed for Codex CLI with access to a local RenderCV repo at `C:\dev\rendercv`.
- The resume input must follow RenderCV’s schema (`C:\dev\rendercv\schema.json`).
