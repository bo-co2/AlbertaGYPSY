# GYPSY Stand Projection Tool

A standalone desktop application for running Alberta GYPSY (Growth and Yield Projection SYstem). Project hundreds of plots with one click and generating identical results as the goverment version.

## Download

Download the latest release from the [Releases](../../releases) page.

## System Requirements

- Windows 10 or later (64-bit)
- No installation or administrator privileges required

## Quick Start

1. Download the latest `.zip` from [Releases](../../releases)
2. Extract the zip to any folder
3. Double-click `GYPSYProjection.exe`
4. Use the **Browse** button to select your input CSV
5. Click **Validate Data** to check your input
6. Click **Run Projection** to generate results
7. Click **Save Results** to export the output CSV

## Input CSV Format

Your input CSV must contain the following columns. See `template.csv` for an example and `data_dictionary.csv` for detailed field descriptions.

### Required Columns

| Column | Description |
|--------|-------------|
| `stand_id` | Unique identifier for each stand |
| `stand_age` | Stand age |
| `spatial` | Spatial flag |
| `BA_known` | Basal area flag |

### Species Columns (for AW, SB, SW, PL)

Each species uses a prefix (`AW_`, `SB_`, `SW_`, `PL_`). At minimum, provide age, height (or site index), and density for at least one species.

| Column | Description |
|--------|-------------|
| `{SP}_tage` | Total age (years) |
| `{SP}_topht` | Top height (m) |
| `{SP}_SI_bh` | Site index at breast height (m) |
| `{SP}_den` | Density (stems/ha) |
| `{SP}_N0` | Initial density (stems/ha) |
| `{SP}_ps` | Percent stocking (%) |
| `{SP}_BA` | Basal area (m²/ha) |
| `{SP}_SI_t` | Site index at total age (m) |

### Optional Utilization Columns

| Column | Description |
|--------|-------------|---------|
| `sdob_{sp}` | Stump diameter outside bark (cm) |
| `stht_{sp}` | Stump height (m) |
| `tdib_{sp}` | Top diameter inside bark (cm) |

## Output

The projection generates 251 rows per stand (ages 0–250), with columns for stand-level and species-level volume, basal area, density, height, and MAI metrics.

## Troubleshooting

| Issue | Solution |
|-------|----------|
| App won't start | Ensure you're on 64-bit Windows. Extract the full zip — don't run from inside the archive. |
| Validation passes but projection fails | Check that species data values are within valid ranges. |
| "not found" error | Make sure the `_internal` folder is in the same directory as the `.exe`. |

## Disclaimer
This tool is an independent project and is not developed, endorsed, or affiliated with the Government of Alberta (GoA). The GYPSY model referenced herein was originally developed by the GoA, but this application is a third-party implementation.
This software is provided "as-is" without warranty of any kind, express or implied. The developer assumes no responsibility or liability for the accuracy, reliability, or completeness of the results produced by this tool. Users are solely responsible for verifying outputs and determining their suitability for any particular purpose. Use of this tool is entirely at your own risk.

## License

Copyright © 2026. All rights reserved. This software is provided as-is for use in forestry growth and yield projections. Redistribution of the application and source code is not permitted.

## Acknowledgements

This tool is powered by the GYPSY (Growth and Yield Projection SYstem) model developed by the Government of Alberta.
GoA offical GYPSY website: https://www.alberta.ca/growth-and-yield-projection-system 
