# Usage - CLI

## Installation

You can download the binaries from github releases: https://github.com/cidverse/normalizeci/releases

**Linux**:

```bash
curl -L -s -o /usr/local/bin/normalizeci https://github.com/cidverse/normalizeci/releases/download/v2.0.0-alpha.1/linux_amd64
chmod +x /usr/local/bin/normalizeci
```

## Usage

If you have installed the `normalizeci` cli tool, you can use it to normalize and denormalize environment variables.

Here are some examples:

| Id  | Command                                                  | Description                                                                       |
|-----|----------------------------------------------------------|-----------------------------------------------------------------------------------|
| 1   | `normalizeci normalize --format export --output nci.env` | generate nci variables in format export for unix systems, stored as file          |
| 2   | `normalizeci normalize --format powershell`              | generate nci variables in format export for windows powershell, written to stdout |
| 3   | `normalizeci normalize --output nci.env`                 | generate nci variables in the suggested format for the current system             |
| 4   | `normalizeci normalize --hostenv --output nci.env`       | additionally to 3 includes all env vars from the host                             |
| 5   | `normalizeci normalize --format cmd`                     | generate nci variables in format export for windows cmd, written to stdout        |
| 6   | `normalizeci denormalize --target gitlab`                | generate a gitlab ci like environment based on the normalized environment         |
| 7   | `normalizeci version`                                    | print version information                                                         |

Depending on your selected output format you will get one line per variable in the following format:

| Format | Example |
|--------|---------|
| export | `export NCI="true"` |
| cmd | `set NCI=true` |
| powershell | `$env:NCI="true";` |

### using a intermediary file

Linux/MacOS

```bash
normalizeci normalize --format export --output nci.env
source nci.env
rm nci.env
```

Windows

```powershell
normalizeci normalize --format powershell --output nci.ps1
& .\nci.ps1
rm nci.ps1
```

### using eval

Linux/MacOS

```bash
eval $(normalizeci normalize)
```

Windows

```powershell
$nenv = normalizeci normalize
Invoke-Expression "$nenv"
```

!!! danger "Piping output into your Shell"

    Please keep in mind that piping output into your shell could be dangerous, so using a intermediary file is recommended.
