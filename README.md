# deep_merge-rails

This gem is an extraction of #deep_merge from [ActiveSupport](https://github.com/rails/rails/tree/master/activesupport/lib/active_support).

## Basic Usage

`gem install deep_merge-rails`

(Taken from core docs.)

Returns a new hash with `self` and `other_hash` merged recursively.



```
h1 = { a: true, b: { c: [1, 2, 3] } }
h2 = { a: false, b: { x: [3, 4, 5] } }

h1.deep_merge(h2) #=> { a: false, b: { c: [1, 2, 3], x: [3, 4, 5] } }
```

Like with Hash#merge in the standard library, a block can be provided to merge values:

```
h1 = { a: 100, b: 200, c: { c1: 100 } }
h2 = { b: 250, c: { c1: 200 } }
h1.deep_merge(h2) { |key, this_val, other_val| this_val + other_val }
# => { a: 100, b: 450, c: { c1: 300 } }
```

[Documentation can be found here.](https://apidock.com/rails/Hash/deep_merge)

__NOTE: version of this gem is pinned to the version of activesupport it is extracted from.__
