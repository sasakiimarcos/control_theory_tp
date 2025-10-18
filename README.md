## LaTeX report: build and live preview

### Prerequisites (macOS)
- Install Homebrew if needed: see `https://brew.sh`
- Install a LaTeX engine (Tectonic):
```bash
brew install tectonic
```

Optional (alternative tool):
```bash
brew install latexmk
```

### Build once
From the project root:
```bash
cd /Users/marcos/Sandbox/Template_CentraleSupélec___Stage__1_
tectonic main.tex
open main.pdf
```

### Live auto‑rebuild on save (recommended)
Tectonic’s watcher runs Tectonic subcommands when files change. Pass the build command with the file:
```bash
cd /Users/marcos/Sandbox/Template_CentraleSupélec___Stage__1_
tectonic -X watch -x "build main.tex"
```
- Open `main.pdf` once in Preview; it will refresh automatically when you save `main.tex`.
- Stop the watcher with Ctrl+C. If started in the background, stop with:
```bash
pkill -f 'tectonic -X watch'
```

### Live auto‑rebuild (latexmk alternative)
```bash
cd /Users/marcos/Sandbox/Template_CentraleSupélec___Stage__1_
latexmk -pdf -pvc -interaction=nonstopmode -halt-on-error main.tex
```
- Opens a continuous preview loop; stop with Ctrl+C.

### Tips
- If Preview doesn’t refresh, ensure the PDF window is already open and you’re writing to the same `main.pdf` path.
- To clean latexmk intermediates (if you used latexmk):
```bash
latexmk -C
```


