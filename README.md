<!--

@license Apache-2.0

Copyright (c) 2022 The Stdlib Authors.

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

# isConstantcase

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Test if a value is a constantcase string.

<section class="installation">

## Installation

```bash
npm install @stdlib/assert-is-constantcase
```

Alternatively,

-   To load the package in a website via a `script` tag without installation and bundlers, use the [ES Module][es-module] available on the [`esm` branch][esm-url].
-   If you are using Deno, visit the [`deno` branch][deno-url].
-   For use in Observable, or in browser/node environments, use the [Universal Module Definition (UMD)][umd] build available on the [`umd` branch][umd-url].
-   To use as a general utility for the command line, install the corresponding [CLI package][cli] globally

The [branches.md][branches-url] file summarizes the available branches and displays a diagram illustrating their relationships.

</section>

<section class="usage">

## Usage

```javascript
var isConstantcase = require( '@stdlib/assert-is-constantcase' );
```

#### isConstantcase( value )

Tests if a `value` is a constantcase `string`.

```javascript
var bool = isConstantcase( 'BEEP_BOOP' );
// returns true

bool = isConstantcase( 'BEEP and BOOP' );
// returns false
```

</section>

<!-- /.usage -->

<section class="notes">

## Notes

-   The function validates that a `value` is a `string`. For all other types, the function returns `false`.

</section>

<!-- /.notes -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var isConstantcase = require( '@stdlib/assert-is-constantcase' );

console.log( isConstantcase( 'BEEP_BOOP' ) );
// => true

console.log( isConstantcase( 'BEEP and BOOP' ) );
// => false

console.log( isConstantcase( 'BEEP_BOOP_BEEP' ) );
// => true

console.log( isConstantcase( 'b' ) );
// => false

console.log( isConstantcase( 'B' ) );
// => true

console.log( isConstantcase( '!' ) );
// => false

console.log( isConstantcase( 'beep boop' ) );
// => false

```

</section>

<!-- /.examples -->

* * *

<section class="cli">

## CLI

<section class="installation">

## Installation

To use as a general utility, install the CLI package globally

```bash
npm install -g @stdlib/assert-is-constantcase-cli
```

</section>

<!-- CLI usage documentation. -->

<section class="usage">

### Usage

```text
Usage: is-constantcase [options] [<string>]

Options:

  -h,    --help                Print this message.
  -V,    --version             Print the package version.
         --split sep           Delimiter for stdin data. Default: '/\\r?\\n/'.
```

</section>

<!-- /.usage -->

<!-- CLI usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

### Notes

-   If the split separator is a [regular expression][mdn-regexp], ensure that the `split` option is either properly escaped or enclosed in quotes.

    ```bash
    # Not escaped...
    $ echo -n $'beEp booP\nFOO' | is-constantcase --split /\r?\n/
    # Escaped...
    $ echo -n $'beEp booP\nFOO' | is-constantcase --split /\\r?\\n/
    ```

-   The implementation ignores trailing delimiters.

</section>

<!-- /.notes -->

<section class="examples">

### Examples

```bash
$ is-constantcase BEEP_BOOP
true
```

To use as a [standard stream][standard-streams],

```bash
$ echo -n 'beep Boop' | is-constantcase
false
```

By default, when used as a [standard stream][standard-streams], the implementation assumes newline-delimited data. To specify an alternative delimiter, set the `split` option.

```bash
$ echo -n 'beepBoop\tBEEP_BOOP' | is-constantcase --split '\t'
false
true
```

</section>

<!-- /.examples -->

</section>

<!-- /.cli -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

* * *

## See Also

-   <span class="package-name">[`@stdlib/assert/is-string`][@stdlib/assert/is-string]</span><span class="delimiter">: </span><span class="description">test if a value is a string.</span>

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2023. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/assert-is-constantcase.svg
[npm-url]: https://npmjs.org/package/@stdlib/assert-is-constantcase

[test-image]: https://github.com/stdlib-js/assert-is-constantcase/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/assert-is-constantcase/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/assert-is-constantcase/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/assert-is-constantcase?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/assert-is-constantcase.svg
[dependencies-url]: https://david-dm.org/stdlib-js/assert-is-constantcase/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://gitter.im/stdlib-js/stdlib/

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[cli-url]: https://github.com/stdlib-js/assert-is-constantcase/tree/cli
[main-url]: https://github.com/stdlib-js/assert-is-constantcase

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/assert-is-constantcase/tree/deno
[umd-url]: https://github.com/stdlib-js/assert-is-constantcase/tree/umd
[esm-url]: https://github.com/stdlib-js/assert-is-constantcase/tree/esm
[branches-url]: https://github.com/stdlib-js/assert-is-constantcase/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/assert-is-constantcase/main/LICENSE

[standard-streams]: https://en.wikipedia.org/wiki/Standard_streams

[mdn-regexp]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions

<!-- <related-links> -->

[@stdlib/assert/is-string]: https://github.com/stdlib-js/assert-is-string

<!-- </related-links> -->

</section>

<!-- /.links -->
