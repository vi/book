`this` &ndash; Simulating an Object Method
==========================================

```admonish warning.side "Functions are pure"

The only way for a script-defined [function](functions.md) to change an external value is via `this`.
```

Arguments passed to script-defined [functions](functions.md) are always by _value_ because
[functions](functions.md) are _pure_.

However, [functions](functions.md) can also be called in _method-call_ style:

> _object_ `.` _method_ `(` _parameters_ ... `)`

When a [function](functions.md) is called this way, the keyword `this` binds to the object in the
method call and can be changed.

```rust
fn change() {       // note that the method does not need a parameter
    this = 42;      // 'this' binds to the object in method-call
}

let x = 500;

x.change();         // call 'change' in method-call style, 'this' binds to 'x'

x == 42;            // 'x' is changed!

change();           // <- error: 'this' is unbound
```


Elvis Operator
--------------

The [_Elvis_ operator](https://en.wikipedia.org/wiki/Elvis_operator) can be used to short-circuit
the method call when the object itself is `()`.

> _object_ `?.` _method_ `(` _parameters_ ... `)`

In the above, the _method_ is never called if _object_ is `()`.
