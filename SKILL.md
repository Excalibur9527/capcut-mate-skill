# CapCut Mate Skill

This skill allows OpenClaw to automate Jianying (CapCut) video editing workflows via the CapCut Mate API.

## Installation
1. Ensure the CapCut Mate server is running (locally or via Docker).
2. Install this skill via ClawHub.
3. Configure `CAPCUT_MATE_URL` in `TOOLS.md`.

## Usage
- `capcut-mate-create-draft`: Create a new project.
- `capcut-mate-add-video`: Add video materials.
- `capcut-mate-gen-video`: Render the final video.

## Configuration
- `CAPCUT_MATE_URL`: Base URL (default: http://localhost:30000)
