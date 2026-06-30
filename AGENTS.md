# amele-linux

Python-based terminal application (TUI) acting as the Linux forensic agent for the Amele desktop app.

## Quick start

```bash
# Check syntax
python -m py_compile linux.py

# Run agent locally
python linux.py

# Format check / formatting
# (This repo does not have strict black formatting requirements yet, but keep it clean)
```

## CI rules

- All pushes to the `dev` branch trigger the GitHub Actions workflow.
- **Automated Builds & Prereleases** are only run if the commit message contains the `[build]` tag:
  ```bash
  git commit -m "feat: add capability [build]"
  ```
- Triggering manually via `workflow_dispatch` is also supported.
- Pipeline outputs: `amele-linux` standalone executable (packaged via PyInstaller).

## Architecture

- Dynamically runs local commands (e.g. `dd`, `avml`, `volatility`) to perform disk imaging and RAM acquisition.
- Communicates back to `amele-next` via a simple TCP or HTTP service configuration.
