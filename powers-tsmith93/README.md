
<!-- README.md is generated from README.Rmd. Please edit that file -->

[![Build
Status](https://travis-ci.org/vincenzocoia/powers.svg?branch=master)](https://travis-ci.org/vincenzocoia/powers)

**Note**: This R package is not mean to be “serious”. It’s just for
teaching purposes.

# powers

This is an R package that gives `sqrt()` friends by providing other
power functions.

## Installation

You can install powers from github with:

``` r
# install.packages("devtools")
devtools::install_github("vincenzocoia/powers")
```

## Example

See the vignette for more extensive use, but here’s an example:

``` r
powers::reciprocal(2)
#> [1] 0.5
```
Here is an example of using the functions to cube and square these values 2, 4, 6, 8.


```{r}
powers::cube(c(2,4,6,8))
#> [1] 8 64 216 512
```

```{r}
powers::square(c(2,4,6,8))
#> [1] 4 16 36 64 
```

Here will will use frac.pow (has a default fractional power of 1/2) and squarer to get the square root of a vector, and cubicr to get the cubic root

```{r}
powers::frac.pow(c(4,9,16))
#> [1] 2 3 4
```

```{r}
powers::squarer(c(4,9,16))
#> [1] 2 3 4
```

```{r}
powers::cubicr(c(8,27,64))
#> [1] 2 3 4
```


Here is an example of a basic use of the boxcox() function in the powers package.  We will use a vector, x, consisting of 2, 3, 4, and 5. The lambda parameter, which is a measure of the strength of the boxcox transformation, is set to 2.

```{r}
x = 2:5
powers::boxcox.transform(x, lambda = 2)
#> [1] 1.5 4.0 7.5 12.0
```

## For Developers

(Again, I don’t actually intend for anyone to develop this silly
package, but if I did, here’s what I’d write.)

Use the internal `pow` function as the machinery for the front-end
functions such as `square`, `cube`, and `reciprocal`.
