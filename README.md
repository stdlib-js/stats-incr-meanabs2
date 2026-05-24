<!--

@license Apache-2.0

Copyright (c) 2018 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# incrmeanabs2

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Compute an [arithmetic mean][arithmetic-mean] of squared absolute values incrementally.

<section class="intro">

The [arithmetic mean][arithmetic-mean] of squared absolute values is defined as

<!-- <equation class="equation" label="eq:arithmetic_mean_squared_absolute_values" align="center" raw="m = \frac{1}{n} \sum_{i=0}^{n-1} x_i^2" alt="Equation for the arithmetic mean of squared absolute values."> -->

```math
m = \frac{1}{n} \sum_{i=0}^{n-1} x_i^2
```

<!-- <div class="equation" align="center" data-raw-text="m = \frac{1}{n} \sum_{i=0}^{n-1} x_i^2" data-equation="eq:arithmetic_mean_squared_absolute_values">
    <img src="https://cdn.jsdelivr.net/gh/stdlib-js/stdlib@d08c5f0a491ba12729c84e40455fb75cf8666874/lib/node_modules/@stdlib/stats/incr/meanabs2/docs/img/equation_arithmetic_mean_squared_absolute_values.svg" alt="Equation for the arithmetic mean of squared absolute values.">
    <br>
</div> -->

<!-- </equation> -->

</section>

<!-- /.intro -->



<section class="usage">

## Usage

```javascript
import incrmeanabs2 from 'https://cdn.jsdelivr.net/gh/stdlib-js/stats-incr-meanabs2@deno/mod.js';
```

#### incrmeanabs2()

Returns an accumulator `function` which incrementally computes an [arithmetic mean][arithmetic-mean] of squared absolute values.

```javascript
var accumulator = incrmeanabs2();
```

#### accumulator( \[x] )

If provided an input value `x`, the accumulator function returns an updated mean. If not provided an input value `x`, the accumulator function returns the current mean.

```javascript
var accumulator = incrmeanabs2();

var m = accumulator( 2.0 );
// returns 4.0

m = accumulator( -1.0 );
// returns 2.5

m = accumulator( -3.0 );
// returns ~4.67

m = accumulator();
// returns ~4.67
```

</section>

<!-- /.usage -->

<section class="notes">

## Notes

-   Input values are **not** type checked. If provided `NaN` or a value which, when used in computations, results in `NaN`, the accumulated value is `NaN` for **all** future invocations. If non-numeric inputs are possible, you are advised to type check and handle accordingly **before** passing the value to the accumulator function.

</section>

<!-- /.notes -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
import randu from 'https://cdn.jsdelivr.net/gh/stdlib-js/random-base-randu@deno/mod.js';
import incrmeanabs2 from 'https://cdn.jsdelivr.net/gh/stdlib-js/stats-incr-meanabs2@deno/mod.js';

var accumulator;
var v;
var i;

// Initialize an accumulator:
accumulator = incrmeanabs2();

// For each simulated datum, update the mean...
for ( i = 0; i < 100; i++ ) {
    v = ( randu()*100.0 ) - 50.0;
    accumulator( v );
}
console.log( accumulator() );
```

</section>

<!-- /.examples -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

* * *

## See Also

-   <span class="package-name">[`@stdlib/stats-incr/mean`][@stdlib/stats/incr/mean]</span><span class="delimiter">: </span><span class="description">compute an arithmetic mean incrementally.</span>
-   <span class="package-name">[`@stdlib/stats-incr/meanabs`][@stdlib/stats/incr/meanabs]</span><span class="delimiter">: </span><span class="description">compute an arithmetic mean of absolute values incrementally.</span>
-   <span class="package-name">[`@stdlib/stats-incr/mmeanabs2`][@stdlib/stats/incr/mmeanabs2]</span><span class="delimiter">: </span><span class="description">compute a moving arithmetic mean of squared absolute values incrementally.</span>
-   <span class="package-name">[`@stdlib/stats-incr/sumabs2`][@stdlib/stats/incr/sumabs2]</span><span class="delimiter">: </span><span class="description">compute a sum of squared absolute values incrementally.</span>

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2026. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/stats-incr-meanabs2.svg
[npm-url]: https://npmjs.org/package/@stdlib/stats-incr-meanabs2

[test-image]: https://github.com/stdlib-js/stats-incr-meanabs2/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/stats-incr-meanabs2/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/stats-incr-meanabs2/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/stats-incr-meanabs2?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/stats-incr-meanabs2.svg
[dependencies-url]: https://david-dm.org/stdlib-js/stats-incr-meanabs2/main

-->

[chat-image]: https://img.shields.io/badge/zulip-join_chat-brightgreen.svg
[chat-url]: https://stdlib.zulipchat.com

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/stats-incr-meanabs2/tree/deno
[deno-readme]: https://github.com/stdlib-js/stats-incr-meanabs2/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/stats-incr-meanabs2/tree/umd
[umd-readme]: https://github.com/stdlib-js/stats-incr-meanabs2/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/stats-incr-meanabs2/tree/esm
[esm-readme]: https://github.com/stdlib-js/stats-incr-meanabs2/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/stats-incr-meanabs2/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/stats-incr-meanabs2/main/LICENSE

[arithmetic-mean]: https://en.wikipedia.org/wiki/Arithmetic_mean

<!-- <related-links> -->

[@stdlib/stats/incr/mean]: https://github.com/stdlib-js/stats-incr-mean/tree/deno

[@stdlib/stats/incr/meanabs]: https://github.com/stdlib-js/stats-incr-meanabs/tree/deno

[@stdlib/stats/incr/mmeanabs2]: https://github.com/stdlib-js/stats-incr-mmeanabs2/tree/deno

[@stdlib/stats/incr/sumabs2]: https://github.com/stdlib-js/stats-incr-sumabs2/tree/deno

<!-- </related-links> -->

</section>

<!-- /.links -->
