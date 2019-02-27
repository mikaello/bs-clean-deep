# bs-clean-deep

Complete bindings for [clean-deep](https://github.com/nunofgs/clean-deep), a library for removing falsy, empty or nullable values from javascript objects.

## Getting started

```
yarn add bs-clean-deep
```

Then add `bs-clean-deep` as a dependency to `bsconfig.json`:

```git
"bs-dependencies": [
+  "bs-clean-deep": "latest"
]
```

## Example

```reason
let jsObject = [%bs.raw {|
{
  bar: {},
  baz: null,
  biz: 'baz',
  foo: '',
  net: [],
  nit: undefined,
  qux: {
    baz: 'boz',
    txi: ''
  }
}
|}];

let cleaned = CleanDeep.cleanDeep(jsObject);

Js.log(cleaned);
/* => { biz: 'baz', qux: { baz: 'boz' } } */
```

## Contribute

If you find bugs or there are updates in [clean-deep](https://github.com/nunofgs/clean-deep), feel free to open an issue or PR. If you are upgrading any dependencies, please use yarn so `yarn.lock` is updated.
