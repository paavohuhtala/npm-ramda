##Type definitions for [Ramda](https://github.com/ramda/ramda)

Test with:
```bash
tsc --module amd ramda-tests.ts
```

Will be pushed to [DefinitelyTyped](https://github.com/borisyankov/DefinitelyTyped) when finished.

Pull requests are welcome!

[![Gitter](https://badges.gitter.im/Join Chat.svg)](https://gitter.im/donnut/typescript-ramda?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

##Usage and limitation
To use the Ramda type definitions include the following line in each of the .ts files
that use Ramda:
```
    /// <reference path=./path/to/ramda.d.ts />
```

In Ramda almost all functions are curried. TypeScript is not equipped well to support
this. We have tried to use TypeScript to its max and allow for curried functions
to be applied in maximum two steps like this:

- `R.indexOf(10, [1,2,3,4])` or `R.indexOf(10)([1,2,3,4])`
- `R.insert(2, 'x', [1,2,3,4])`, `R.insert(2)('x', [1,2,3,4])` or `R.insert(2, 'x')([1,2,3,4])`

If you try to use `R.insert(2)('x')([1,2,3,4])`, TypeScript will complain that the
supplied parameters do not match the target.

##Status
The definitions are reorganized and updated and are more or less compatible with Ramda v0.13. The API of Ramda is not stable yet.

This needs to be done:
- include all functions of v0.13
- reorganize functions by categories (List, Object, Function, etc)
- find a elegant way to reflect the Ramda categories into TypeScript interface names
  that are displayed when hovering over a function. At to moment `R.List.<function name>` is displayed, regardless of the real category a function resides.
- Shorten function descriptions to one or two sentences to limit the size of the
  tooltip in some IDE's.
