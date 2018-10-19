## Patch release

The maintainer's address has changed. It is the same account, just a different
alias. I sent confirmation from the previous address to Uwe Ligges and 
CRAN@r-project.org on September 7, 2018.

Issues fixed:

- ERROR on r-oldrel-windows: Tests run fine, but the R session was closed 
  unexpectedly after the tests when `detach("package:simmer", unload=TRUE)`
  was called. The package is not unloaded anymore after the tests.
- WARN on Windows: since `rticles` v0.5, the compilation of JSS vignettes
  requires pandoc v2, which is not installed on Windows machines on CRAN. Now
  this vignette falls back to an HTML vignette if pandoc v2 is not found, thus
  solving the warning on Windows.
- Other minor fixes and enhancements.

We haven't included any reference to the papers in the DESCRIPTION yet because
they are still waiting to be published and there is no DOI assigned. We will add
them in a future release.

Regarding the package title, Uwe asked us in our last submission to remove
"for R" because it is redundant. If it is not an issue, we would like to keep
it in our case. The reason is that simmer is the only DES framework for R, and
"Discrete-Event Simulation for R" has become a distinctive tag as compared to
our most direct competitors, which are "SimPy: Discrete event simulation for
Python" and "SimJulia: A discrete event process oriented simulation framework
written in Julia".

## Test environments

- Fedora 28 + GCC + clang (local), R 3.5.0
- Ubuntu 14.04 + GCC (on Travis-CI), R 3.4.4, 3.5.0, devel
- linux-x86_64-rocker-gcc-san (on r-hub)
- ubuntu-rchk (on r-hub)
- win-builder, R devel

## R CMD check results

There were no ERRORs, WARNINGs or NOTEs.

## Downstream dependencies

There are 2 downstream dependencies, simmer.plot and simmer.bricks, for which
I'm the maintainer too.
