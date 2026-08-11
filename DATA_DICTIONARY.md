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

## `arm_portfolio_returns_long.csv`

| Column | Description |
| --- | --- |
| `month` | Monthly observation date. |
| `series_id` | Unique ARM implementation identifier. |
| `variable` | ARM family identifier. |
| `weighting` | Portfolio weighting scheme. |
| `price_min` | Minimum stock price screen used in portfolio formation. |
| `sort` | Sorting rule used to form the ARM portfolio. |
| `exchange_breaks` | Breakpoint universe. |
| `ret` | Monthly high-minus-low ARM implementation return. |
