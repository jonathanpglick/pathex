# Changelog

## 2.4

Negative indexes, lens fixes, force_update nil filling and refactoring

**Breaking**

* matching force_update fix. Now it doesn't raise an error when called
* filtering force_update fix. Now it doesn't raise an error when called
* Tuple force_update fix. Now it works with indexes and for `force_set {}, path(2), 1` it will create `{nil, nil, 1}`.
* List force_update fix. Now it works with indexes and for `force_set [], path(2), 1` it will create `[nil, nil, 1]`.

**Non-breaking**

* Tuple negative index is now supported for all operations
* List negative indexes now work the same way as positive indexes (but backwards), except `-1` which still prepends to the list.

## 2.3

**Breaking**

* Pathex now uses Elixir 1.13 (or higher) version

**Non-breaking**

* `Pathex.t` spec fix
* `Pathex.Short` for shorter path definition
* `Pathex.pattern` for creating patterns from inlined paths
* `Pathex` now can be `use`-d inside functions or anything like this
* Paths inlining is now detected for aliased, imported and macro calls
* Internal spec fixes, dead code eliminations and formatting

## 2.2

**Breaking**

* Changed behaviour of path-closures created with `path` when working with improper `Keyword.t()`

**Non-breaking**

* Improved documentation
* Removed dead code
* Added `Pathex.Accessibility` module for creating paths in runtime

## 2.1

**Breaking**

* Updating and viewing keywords with `star` and `some` lenses now doesn't raise when they're used against non-proper keyword

**Non-breaking**

* Concatenated paths now can force_over for not only maps
* Fixed debug lens
* Added ability to pass calls and arbitary structures into `path` macro
* Unrolled some clauses for `star` and `some` for extra efficiency

## 2.0

**Breaking**

* Reworked `star` lens. Now it is less optimistic and returns `:error` when no values were viewed/updated
* Removed sigils
* Removed deprecated lens `id`
* Removed deprecated lens `either`
* Removed `recur` function

**Non-breaking**

* `compose` function for recursive lens
* `delete` method for all paths, lenses and higher order functions
* `inspect` method for all paths, lenses and higher order functions
* Matchable updater for lists and maps
* Builders are selected for combination (not for mod as they used to)
* Reworked documentation
* Annotated paths

## 1.3.0

**Breaking**

None! __(See deprecated in Non-breaking)__

**Non-breaking**

* Deprecated `id` lens
* Deprecated `either` lens

* Fixed bug with concatenation context overlapping
* `some` lens
* `star` lens
* `matching` lens
* `filtering` lens
* Removed some dead code
* Moved lenses code to separate modules

## 1.2.0

**Breaking**

None!

**Non-breaking**

* `star` lens
* `all` lens

## 1.1.0

**Breaking**

None!

**Non-breaking**

* `|||` operator
* stack-optimized version of `~>` operator
* stack-optimized version of `|||` operator

## 1.0.0

**Breaking**

* `force_set`/`get`/`set` clause in closure was renamed to `force_update`/`view`/`update`
and added a special argument with default value in it

**Non-breaking**

* `alongside` macro
* stack-optimized version of `&&&` operator
* path code generation size assertion
* better documentation format
* `id` lens
* `either` lens
* `any` lens

> Yeah, it starts from 1.0.0
> I can describe previous versions if anybody needs this. Just open an issue! :)
