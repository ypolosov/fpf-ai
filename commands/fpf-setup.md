---
name: fpf-setup
description: "Download FPF-Spec.md from the official GitHub repository into the current project root"
---

# FPF Setup

Download the First Principles Framework specification file.

## Instructions

1. Check if FPF-Spec.md already exists in the current working directory:
   ```bash
   ls -la FPF-Spec.md
   ```

2. If it exists, tell the user and ask if they want to re-download (overwrite).

3. Download FPF-Spec.md from the official repository:
   ```bash
   curl -sL https://raw.githubusercontent.com/ailev/FPF/main/FPF-Spec.md -o FPF-Spec.md
   ```

4. Verify the download:
   ```bash
   wc -l FPF-Spec.md
   ```

5. Report to the user:
   - File size (lines)
   - Location (current directory)
   - Next steps: try `/fpf-analyze`, `/fpf-design`, or `/fpf-lookup`
