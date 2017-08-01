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

### Installation

As described in the manual, to [install unregistered packages][unregistered], use `Pkg.clone()` with the repository url:

```julia
Pkg.clone("https://github.com/johnkevinbarrera/drbasisj.jl")
Pkg.clone("https://github.com/johnkevinbarrera/drbasisj.jl")
```

Julia version 0.4 or higher is required (install instructions [here][version]).


```
## Trabajando con el pkg drbasisprueba

for use this package, yo should do:

```

```julia

using drbasisprueba


drbasisprueba.drbasis(500,6)

```

### Usage

As `SearchMatch` supports a number of model variants, there are specific constructors for the two main types:

* `SearchClosed`: closed-system where agents cycle between singlehood and marriage
* `SearchInflow`: steady-state population is determined by exogenous inflows and type-specific death rates

## Example

RELLENAR

```julia
using drbasisj
using Gadfly

n = 100
Basis=[drbasisj.drbasis(n,1),
	drbasisj.drbasis(n,2),
	drbasisj.drbasis(n,3),
	drbasisj.drbasis(n,4),
	drbasisj.drbasis(n,5),
	drbasisj.drbasis(n,6)]

set_default_plot_size(12cm, 8cm)
p1 = plot(x=1:n, y=Basis[1][3], Geom.line, Guide.Title("Eigenvalues (q=1)")) 
p2 = plot(x=1:n, y=Basis[2][3], Geom.line, Guide.Title("Eigenvalues (q=2)"))
p3 = plot(x=1:n, y=Basis[3][3], Geom.line, Guide.Title("Eigenvalues (q=3)")) 
p4 = plot(x=1:n, y=Basis[4][3], Geom.line, Guide.Title("Eigenvalues (q=4)"))
p5 = plot(x=1:n, y=Basis[5][3], Geom.line, Guide.Title("Eigenvalues (q=5)")) 
p6 = plot(x=1:n, y=Basis[6][3], Geom.line, Guide.Title("Eigenvalues (q=6)"))

set_default_plot_size(24cm, 24cm)
gridstack([p1 p2 ; p3 p4; p5 p6])
```







[unregistered]:http://docs.julialang.org/en/release-0.5/manual/packages/#installing-unregistered-packages
[version]:http://julialang.org/downloads/platform.html

