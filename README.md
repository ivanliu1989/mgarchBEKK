# mgarchBEKK

*mgarchBEKK* is an R Package designed to simulate, estimate, predict
and diagnose MGARCH processes, in particular of *BEKK* and *mGJR*
(bivariate asymmetric GARCH) specifications.

> **Please note** that this package is being revised after a long
> time. The original codebase is currently available on
> https://github.com/vst/mgarch. The objective is to standardize the
> simulation, estimation, prediction/forecasting and diagnostics
> processes and optimize for speed in the long run. Therefore, please
> expect significant API changes, ie. function names, parameters and
> their meaning may change along the way.

> *TODO: Provide a complete README file.*

## Installation

The package is on CRAN:

    install.packages("mgarchBEKK")

However, you can still install the package straight from out GitHub
repository. The easiest way is to use devtools:

    install.packages("devtools")

For the `master` branch which is usually the same as the
CRAN version:

    install_github("vst/mgarchBEKK")

For the `develop` branch which is the latest development version:

    install_github("vst/mgarchBEKK", ref="develop")

## Usage

    ## Load the library:
    library(mgarchBEKK)

    ## Simulate a BEKK process:
    simulated <- simulateBEKK(2, 1000, c(1,1))

    ## Prepare the input for the estimation process:
    simulated <- do.call(cbind, simulated$eps)

    ## Estimate with default arguments:
    estimated <- BEKK(simulated)

    ## Show diagnostics:
    diagnoseBEKK(estimated)

    ## Likewise, you can estimate an mGJR process:
    estimated2 <- mGJR(simulated[,1], simulated[,2])

## LICENSE

This R library is licensed under
[GPLv3](http://www.gnu.org/licenses/gpl-3.0.en.html).

    mgarchBEKK - Simulating, Estimating & Diagnosing BEKK/mGJR Processes

    Copyright (C) 2004-2016 Harald Schmidbauer, Angi Roesch, Vehbi Sinan
    Tunalioglu

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or (at
    your option) any later version.

    This program is distributed in the hope that it will be useful, but
    WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
    General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.
