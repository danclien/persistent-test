Anyone know why my Template Haskell generated data constructors aren't being exported in `Models.hs` for use in `Broken.hs`?


## `Works.hs`

`Works.hs` contains the first example listed in the [Yeson Book](http://www.yesodweb.com/book/persistent).

Can be tested with

```
cabal run works
```

## `Broken.hs`

`Broken.hs` moves the table declaration for `persistent` to `Models.hs`. Everything else should be the same, but it doesn't compile because it can't find missing data constructors.

Output from `cabal build broken`:

```
Preprocessing executable 'broken' for persistent-test-0.1.0.0...
[2 of 2] Compiling Main             ( Broken.hs, dist/build/broken/broken-tmp/Main.o )

Broken.hs:20:24: Not in scope: data constructor ‘Person’

Broken.hs:21:24: Not in scope: data constructor ‘Person’

Broken.hs:23:14: Not in scope: data constructor ‘BlogPost’

Broken.hs:24:14: Not in scope: data constructor ‘BlogPost’

Broken.hs:26:32: Not in scope: data constructor ‘BlogPostAuthorId’

Broken.hs:33:18: Not in scope: data constructor ‘BlogPostAuthorId’
```