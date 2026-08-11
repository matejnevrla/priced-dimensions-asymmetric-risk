# Data Dictionary

All dates are month identifiers in ISO format, stored as the first day of the
calendar month. All return columns are decimal monthly returns.

## `arm_pca_returns_wide.csv`

| Column | Description |
| --- | --- |
| `month` | Monthly observation date. |
| `PC1`-`PC10` | Monthly PC portfolio returns. |

## `arm_basis_returns.csv`

| Column | Description |
| --- | --- |
| `month` | Monthly observation date. |
| `Broad_tail_crash` | Pre-specified broad tail/crash ARM basis factor. |
| `Lower_tail_CIQ` | Pre-specified lower-tail CIQ ARM basis factor. |
| `Residual_coskewness` | Pre-specified residual-coskewness ARM basis factor. |
