# stirling-pdf

Stirling PDF — powerful PDF manipulation tool (merge, split, convert,
OCR, compress, sign, and more) all in the browser.

## Services

| Container | Image | Port |
|---|---|---|
| stirling-pdf | `stirlingtools/stirling-pdf:latest` | 8084 |

## Volumes

| Host | Container |
|---|---|
| `~/homelab_volumes/stirling-pdf/trainingData` | `/usr/share/tessdata` |
| `~/homelab_volumes/stirling-pdf/extraConfigs` | `/configs` |
| `~/homelab_volumes/stirling-pdf/logs` | `/logs` |
