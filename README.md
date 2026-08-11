# The Priced Dimensions of Asymmetric Risk: Public Data Release

This repository contains a lightweight public data package for the paper:

**The Priced Dimensions of Asymmetric Risk**  
Matej Nevrla

The release is designed for researchers who want to use the paper's public
factor return panels and the aggregate ARM implementation returns without
accessing the underlying stock-level databases.

## Contents

All returns are monthly decimal returns. For example, `0.01` means 1 percent in
that month.

| File | Description |
| --- | --- |
| `data/arm_pca_returns_wide.csv` | Full-sample covariance-PCA portfolio returns for PC1-PC10 in wide format. |
| `data/arm_basis_returns.csv` | Returns for the three pre-specified ARM basis factors. |
| `data/arm_portfolio_returns_long.csv` | Monthly returns for the 150 underlying ARM implementations in long format. |

The monthly sample covers January 1968 through December 2024.

## Quick Start

In R:

```r
pca <- read.csv("data/arm_pca_returns_wide.csv")
arm_basis <- read.csv("data/arm_basis_returns.csv")
arm_portfolios <- read.csv("data/arm_portfolio_returns_long.csv")
```

In Python:

```python
import pandas as pd

pca = pd.read_csv("data/arm_pca_returns_wide.csv")
arm_basis = pd.read_csv("data/arm_basis_returns.csv")
arm_portfolios = pd.read_csv("data/arm_portfolio_returns_long.csv")
```

## ARM Families

The PCA and ARM basis factors are constructed from 150 ARM implementations: five
ARM families combined with 30 implementation choices. The 150 implementation
returns are provided in `data/arm_portfolio_returns_long.csv`.

| `variable` | Description |
| --- | --- |
| `htcr` | Hybrid tail-covariance risk |
| `mcrash` | Multivariate crash risk |
| `beta_tr` | Tail-risk beta |
| `ciq_down` | Lower-tail commonality in quantiles |
| `resid_coskew_monthly` | Residual coskewness estimated from monthly returns |

Implementation choices vary the portfolio weighting scheme, sorting rule,
minimum-price screen, and breakpoint universe.

## ARM Basis

The three pre-specified ARM basis factors are:

| Column | Construction |
| --- | --- |
| `Broad_tail_crash` | Equal average of the HTCR, MCRASH, and tail-risk-beta family composites |
| `Lower_tail_CIQ` | Lower-tail CIQ family composite |
| `Residual_coskewness` | Residual-coskewness family composite |

## PCA Construction

The PCA portfolios are estimated from the centered covariance matrix of the 150
monthly ARM implementation returns. Eigenvectors are applied to raw returns and
normalized to unit gross exposure. PC signs are oriented so that the full-sample
average PC return is positive.

## Source Data

The repository contains only aggregate factor return series. It does not include
the raw stock-level databases, security identifiers, or licensed vendor files
used to construct the factors.

## License

This public data release is licensed under the Creative Commons Attribution 4.0
International License (CC BY 4.0). See `LICENSE`.
