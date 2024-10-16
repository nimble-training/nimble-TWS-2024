# nimble-TWS-2024

This repository contains materials for the NIMBLE workshop at the 2024 Annual Conference of The Wildlife Society in Baltimore, Maryland, USA.

This is scheduled as a one-day workshop from 8am-5pm. The schedule will provide plenty of time for breaks and lunch.

To prepare for the workshop:

 - Install NIMBLE (see below)
 - Install additional packages (see below)
 - Download the materials provided in this repository

All materials for the workshop will be in this GitHub repository. If you're familiar with Git/GitHub, you already know how to get all the materials on your computer. If you're not, go [here](https://github.com/nimble-training/nimble-TWS-2024), click the (green) "Code" button, and choose the "Download ZIP" option.

## Background for the workshop

This workshop will focus on the `nimble` R package, not on statistical methodology per se.  The material assumes attendees have basic knowledge of ecological statistical models such as capture-recapture, occupancy, N-mixture, and hidden Markov models. (We will not use all of those!) You will still be able to follow the workshop without this background, but the workshop is geared towards participants already familiar with these topics.

## Tentative Schedule

Tuesday October 22nd:

1. (8:00 am - 8:50 am) Primer (Optional): Coding in the NIMBLE model language (a dialect of the BUGS language)
2. (9:00 am - 9:50 am) Introduction to NIMBLE: Basic concepts and workflows
3. (10:00 am - 10:50 am) Comparing and customizing MCMC methods in NIMBLE
4. (11:00 am - 12:00 pm) User-defined distributions and functions in models
6. (12:00 pm - 1:00 pm) Break for lunch
7. (1:00 pm - 1:50 pm) Strategies for improving MCMC
8. (2:00 pm - 2:50 pm) Special modeling components and methods (spatial, Bayesian non-parametrics, and reversible jump for variable selection)
9. (3:00 pm - 3:50 pm) Laplace approximation and other numerical methods in NIMBLE
10. (4:00 pm - 4:50 pm) Writing new samplers and algorithms

## Help with NIMBLE

The NIMBLE web site is [here](https://r-nimble.org).

The NIMBLE user manual is [here](https://r-nimble.org/html_manual/cha-welcome-nimble.html).

A NIMBLE "cheatsheet" is available [here](https://r-nimble.org/documentation).

## Installing NIMBLE

NIMBLE is an R package available on CRAN, so in general it will be straightforward to install as with any R package. However, NIMBLE does require a compiler and related tools installed on your system.

The steps to install NIMBLE are:

1. Install compiler tools on your system. [https://r-nimble.org/download](https://r-nimble.org/download) will point you to more details on how to install *Rtools* on Windows and how to install the command line tools of *Xcode* on a Mac. Note that if you have packages requiring a compiler (e.g., *Rcpp*) on your computer, you should already have the compiler tools installed.

2. Install the *nimble* package from CRAN in the usual fashion of installing an R package (e.g. `install.packages("nimble")`). More details (including troubleshooting tips) can also be found in Section 4 of the [NIMBLE manual](https://r-nimble.org/html_manual/cha-installing-nimble.html).

3) Test that the installation is working, by running the following code in R:

```
library(nimble)
code <- nimbleCode({ x ~ dnorm(0, 1) })
model <- nimbleModel(code)
cModel <- compileNimble(model)
```

If the above code runs without error, you're all set. If not, please see the troubleshooting tips.  The most common problems have to do with proper installation of the compiler tools.  On Windows, the `PATH` system variable must be set (see link to Rtools installation details from our download linked above).  On Mac OSX, command line tools must be installed as part of Xcode.  If you still have problems, please email the [nimble-users group](https://r-nimble.org/more/issues-and-groups) for help.

In general, we encourage you to update to the most recent version of NIMBLE (version 1.2.1).

## Installing additional packages

Prior to the workshop, you should also install the following R packages (beyond those automatically installed with `nimble`), which can be installed as follows:

```
install.packages(c("nimbleHMC", "mcmcplots", "coda", "nimbleEcology", "compareMCMCs"))
```

