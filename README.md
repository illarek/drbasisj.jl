# Computation of the Demmler-Reinsch basis.

[![Build Status](https://travis-ci.org/ChrisRackauckas/ExamplePackage.jl.svg?branch=master)](https://travis-ci.org/ChrisRackauckas/ExamplePackage.jl)
[![Build status](https://ci.appveyor.com/api/projects/status/9iuvdt0j0mw6au0k?svg=true)](https://ci.appveyor.com/project/ChrisRackauckas/examplepackage-jl)



The `Demmler-Reinsch basis` is provided for a given smoothness degree in a uniform grid. 
- `drbasis(nn,qq)`
- `nn`: Number of design points in the uniform grid. 
- `qq`: Smoothness degree of the basis.

### Details

The use of large numbers required by the basis is handled by the package Brobdingnag. The method assumes the grid is equidistant. Missing values are not supported.

### Value

A list object containing the following information.

- `eigenvalues`: estimadted eigenvalues.
- `eigenvectors`: estimated eigenvectors.
- `eigenvectorsQR`: orthonormal eigenvectors.
- `x`: equidistant grid used to build the basis.

### References

`Rosales F. (2016).` Empirical Bayesian Smoothing Splines for Signals with Correlated Errors: Methods and Applications
`Serra, P. and Krivobokova, T. (2015)` Adaptive Empirical Bayesian Smoothing Splines

### Authors

Francisco Rosales

John Barrera


## Intallation

As described in the manual, to [install unregistered packages][unregistered], use `Pkg.clone()` with the repository url:

```julia
Pkg.clone("https://github.com/johnkevinbarrera/drbasisj.jl")
Pkg.clone("https://github.com/johnkevinbarrera/drbasisj.jl")
```

Julia version 0.4 or higher is required (install instructions [here][version]).

```

## Trabajando con el pkg drbasisprueba

for use this package, yo should do:

```julia

using drbasisprueba


drbasisprueba.drbasis(500,6)
```
