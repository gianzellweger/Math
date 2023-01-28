<h1>Applescript Math Library</h1>

<h2>Interactive documentation can be found at [https://gianzellweger.github.io/math-docs]</h2>

<h2>Table of Contents</h2>

* Usage
* Methods
* Contributing
* Why

<h2>Usage</h2>

1. Check if either `/Library/Script Libraries/` or `/Users/[Your name]/Library/Script Libraries/` exists. If not, create either of them.
2. Move `Math.scptd` in one of those two directories. Move it to the first one if you want all users of the Computer to have access to it and the second one if only you should have access to it.
3. You can use this library in 3 different ways:

```lang-applescript
global math
set math to load script "/path/to/library.scptd"
math's sqrt(64)
```

<sup>This is a bit convoluted but every other method loads the library at compile time, while this loads the library at runtime.</sup>

```lang-applescript
global math
set math to script "Math"
math's sqrt(64)
```

<sup>This is the simplest method if you don't plan on updating the library.</sup>

```lang-applescript
tell script "Math" to sqrt(64)
```

<sup>This is the shortest method if you plan on using the library one time.</sup>

<h2>Methods</h2>

This library has the following methods and constants:

<h3>Constants</h3>

* infinity / inf: Biggest number that Applescript can handle.
* E: [Euler's Number](https://en.wikipedia.org/wiki/E_%28mathematical_constant%29).
* tau: Ratio of the circumference to the radius of a circle.
* SQRT2: The square root of 2.
* SQRT1_2: The square root of 0.5.
* LOG10E: Returns the base 10 logarithm of E.
* LOG2E: Returns the base 2 logarithm of E.
* LN10: Returns the natural logarithm of 10.
* LN2: Returns the natural logarithm of 2.

<sup>Note: `pi` is an Applescript builtin</sup>

<h3>Methods</h3>

* sqrt(x): Returns the square root of x.
* cbrt(x): Returns the cubic root of x.
* exp(x): Returns E to the power of x.
* expm1(x): Returns E to the power of x - 1.
* ceil(x): If x is a float/real, returns the next bigger number. If x is an integer, returns x.
* round(x): Rounds x to the nearest integer. 7.5 gets rounded to 8.
* floor(x): If x is a float/real, returns the next lower number. If x is an integer, returns x.
* trunc(x): Returns the integer part of x.
* sign(x): Returns -1 if x is negative, 0 if x is 0, and 1 if x is positive.
* pow(x, y): Returns x to the power of y.
* abs(x): If x is negative, returns -x. If x is an empty string or list, returns 0.
* sin(x): Returns the the sine of x.
* cos(x): Returns the cosine of x.
* tan(x): Returns the tangent of x.
* log(x) given base:E: Returns the natural logarithm of x. base is an optional parameter which has to be given in the fashion described here or above.
* log1p(x): Returns the natural logarithm of 1+x
* log2(x): Returns the base-2 logarithm of x.
* log10(x): Returns the base-10 logarithm of x.
* acos(x): Returns the arc cosine of x.
* acosh(x): Returns the inverse hyperbolic cosine of x.
* asin(x): Returns the arc sine of x.
* asinh(x): Returns the inverse hyperbolic sine of x.
* atan(x): Returns the arc tangent of x.
* atan2(x, y): Returns the arc tangent of x/y in radians:
* atanh(x): Returns the hyperbolic arctangent value of x.
* cosh(x): Returns the hyperbolic cosine of x.
* tanh(x):  Returns the hyperbolic tangent of x.
* min(x): Returns the smallest value in x.
* max(x): Returns the largest value in x.
* random(): Returns a random number between 0 and 1.
* factorial(x): Returns the factorial of x.
* comb(x, y): Returns the total number of possibilities to choose x things from y items.
* perm(x, y): Returns the number of ways to choose k things from n items.
* copysign(x, y): If y is negative, returns x as a negative number. If y is positive, returns y as a positive number.
* dist(x, y): Calculates the euclidian distance between x and y as points in euclidian space. x and y must have the same dimension.
* erf(x): Returns the error function of x.
* erfc(x): Returns 1 - the error function of x.
* fabs(x): Returns the abs of x as a float/real.
* fmod(x, y): Returns the remainder of x divided by y.
* fsum(x): Returns the sum of all items in x.
* gamma(x): Returns the gamma function of x.
* lgamma(x): Returns the natural logarithm of the gamma function of x.
* gcd(x, y): Returns the greatest common divisor of x and y
* hypot(x): Returns the square root of all elements of x squared.
* isclose(x, y): Checks if x and y are close. Currently not useable because optional parameters are not yet implemented.
* isfinite(x): Checks if x is finite.
* isinf(x): Checks if x is infinite.
* isqrt(x): Returns the floored square root of x.
* ldexp(x, y): Returns x * 2 to the power of y.
* frexp(x): Returns mantissa and exponent of x.
* prod(x): Returns the product of all items of x.
* radians(x): Converts degrees to radians.
* degrees(x): Converts radians to degrees.
* remainder(x, y): Returns the remainder of x divided by y as a float/real.
* clz32(x): Returns 32 minus the count of places used by x as a binary representation.
* imul(x, y): Multiplies x and y.
* fround(x): Is supposed to return x as a 32-bit floating point number. Is currently obsolete.
* modf(x): Returns the fractional and the integer part of x in that order.s

<h2>Contributing</h2>

This library is currently in development and could be improved. Things that are currently needed, sorted by importance:

1. Testing. A lot of testing.
2. Optional Parameters for `isclose` and `prod`.
3. A way to pass an arbitrary number of arguments to `min` and `max`.
4. A more accurate way to calculate `erf` and `erfc` since it is relying on `erf`.
5. Give the `fround` function some use without breaking the original use.

<h2>Why?</h2>

I did this because of the following reasons:

* I wanted a challenge.
* I wanted it to be less of a headache to port code from Javascript or Python to Applescript, because as soon as there was some more complicated math in it, you would have to write ~100 functions. Now I wrote ~100 functions.
* I wanted to learn something new.
