# DetectionTheory

`DetectionTheory.jl` is a [Julia](http://www.julialang.org) package to compute signal detection theory measures. Signal detection theory (SDT) is commonly used in psychophysics to quantify the performance of an observer in a variety of tasks. `DetectionTheory.jl` includes functions to compute _d'_ for the following tasks:

- ABX
- Multiple alternatives forced choice
- Odd-One-Out with 3 response alternatives (also known as oddity, or triangular method)
- Same-Different
- Yes-No


Most of the functions have been ported from the [psyphy](http://cran.r-project.org/web/packages/psyphy/index.html) R package.


# Installation and Usage

`DetectionTheory` can be installed using:

```julia
Pkg.add("DetectionTheory")
```

once the package is installed, to access the functions in the module you can
type:

```julia
using DetectionTheory
```

A complete description of each function is given in the [Function Reference](API.md) section. Information on individual functions can also be obtained using the Julia help system:

```julia
?dprimeABX
?dprimeSD
```

A few usage examples for `DetectionTheory` functions are given in the next section.

## Examples


Compute _d'_ for an ABX task when the observer with a hit rate of 0.8 and a false alarm rate of 0.4. If we assume that the observer is following a differencing strategy, we can compute _d'_ with:

```julia
dprimeABX(0.8, 0.4, "diff")
```

if we assume that the observer is using the independent observations strategy instead, we can compute _d'_ with:

```julia
dprimeABX(0.8, 0.4, "IO")
```

_d'_ for the same-different and odd-one-out tasks can also be computed for the differencing of independent observations strategies. For an observer with a hit rate of 0.7 and a false alarm rate of 0.2 in the same-different task:

```julia
dprimeSD(0.7, 0.2, "diff") #differencing strategy
dprimeSD(0.7, 0.2, "IO") #independent observations strategy
```

for an observer with a proportion of correct responses of 0.7 in the odd-one-out task:

```julia
dprimeOddity(0.7, "diff") #differencing strategy
dprimeOddity(0.7, "IO") #independent observations strategy
```

To compute _d'_ in a Yes-No task for an observer with a hit rate of 0.6 and a false alarm rate of 0.3:

```julia
dprimeYesNo(0.6, 0.3)
```

To compute the _d'_ value corresponding to a proportion of correct responses of 0.75 in a 2-alternatives forced choice task:

```julia
dprimeMAFC(0.75, 2)
```

for a 3-alternatives forced choice task:

```julia
dprimeMAFC(0.75, 3)
```



