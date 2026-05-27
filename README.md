# ARI Anthropometry and Metadata

This repository stores two CSV files derived from the official ARI HRTF database anthropometry file. They are prepared for the subject naming and resource loading conventions used by [`hrtfpykit`](https://github.com/ArielAlvarez-Martinez/hrtfpykit), especially `hrtfpykit.datasets.ARI`.

Source data:

- ARI HRTF database: <https://www.oeaw.ac.at/en/ari/outreach/software/hrtf-database>
- SOFA Acoustics ARI database mirror: <https://sofacoustics.org/data/database/ari/>
- Original MATLAB file: <https://www.oeaw.ac.at/fileadmin/Institute/ISF/IMG/software/anthro.mat>
- Measurement description: <https://www.oeaw.ac.at/fileadmin/Institute/ISF/IMG/software/readme.pdf>

## Files

| File | Rows | Description |
| --- | ---: | --- |
| `anthro.csv` | 60 | Anthropometric measurements from the `X`, `A`, `D`, and `theta` variables in `anthro.mat`. |
| `metadata.csv` | 60 | Subject information from `sex`, `age`, `WeightKilograms`, `CreateDate`, and `MeasurementDate`. |

`SubjectID` uses the `nh<number>` format used by the ARI SOFA files in hrtfpykit. It is derived from the ARI normal hearing IDs stored in `anthro.mat`; for example, ARI ID `3002` becomes `nh2`.

## Anthropometry Columns

`anthro.csv` contains:

- `x*` columns for the general anthropometric measurements from `X`
- `L_a*`, `L_d*`, and `L_theta*` columns for left ear measurements
- `R_a*`, `R_d*`, and `R_theta*` columns for right ear measurements

The known wrong `D` measurements marked in the ARI source material are not included. Missing numeric values are written as `NaN`. Numeric values are preserved from the source file without unit conversion.

## Metadata Columns

`metadata.csv` contains:

- `sex`
- `age`
- `WeightKilograms`
- `CreateDate`
- `MeasurementDate`

## Checksums

SHA-256 checksums for the current CSV files:

| File | SHA-256 |
| --- | --- |
| `anthro.csv` | `d4a0ddc346eb5cb8f07f64360c1291cf4dea96b96b801315a9765725ee50e1d1` |
| `metadata.csv` | `174132eee78ffb8b9c7bea5a3774586b0527befad41322a08fa005c68d8a0862` |

## Citation

These files are derived from ARI data. Cite the ARI HRTF database when using them.
