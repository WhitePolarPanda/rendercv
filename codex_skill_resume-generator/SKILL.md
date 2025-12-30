---
name: resume-generator
description: Tailor RenderCV YAML resumes to a target role using an iterative, user-approved edit loop and generate a final PDF with the local rendercv repo. Use when a user provides a RenderCV YAML resume plus a job/position description and wants targeted revisions, an edit rationale report, or PDF output.
---

# Resume Generator

## Overview

Use an iterative loop to tailor a RenderCV YAML resume to a target role. Each iteration outputs a revised YAML plus a Markdown change log with reasoning, asks for user feedback, and repeats until approved. When approved, render the final PDF using the local `C:\dev\rendercv` repo.

## Workflow

1. Intake
   - Ask for the input RenderCV YAML path (e.g., `C:\dev\rendercv\examples\John_Doe_ClassicTheme_CV.yaml`).
   - Ask for the position/role description in Markdown (file path preferred).
   - Ask for desired output base name (optional).
   - Confirm whether reordering experiences is allowed (default: yes).

2. Tailor YAML (iteration)
   - Modify wording to better fit the role while keeping facts accurate.
   - Reorder experiences and highlights to emphasize relevance.
   - Preserve RenderCV schema validity. Use `C:\dev\rendercv\schema.json` as the reference.
   - Keep design/typography unless the user requests changes.

3. Output draft + change log
   - Write the revised YAML to a new file (do not overwrite the original).
   - Create a Markdown file listing each change and the reasoning.
   - Ask for the user's opinion and whether to iterate again.
   - Repeat steps 2-3 until the user approves.

4. Render final PDF
   - Use the local repo to render the approved YAML into a PDF in the original folder.
   - If the `rendercv` CLI is unavailable, fall back to `python -m rendercv render <yaml>`.

## Files and References

- RenderCV schema: `C:\dev\rendercv\schema.json`
- Example input: `C:\dev\rendercv\examples\John_Doe_ClassicTheme_CV.yaml`

## Commands

Render PDF:

```bash
rendercv render "C:\path\to\Resume.yaml"
```

Fallback:

```bash
python -m rendercv render "C:\path\to\Resume.yaml"
```
