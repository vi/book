`rhai-sci`: Functions for Scientific Computing
==============================================

{{#include ../links.md}}

`rhai-sci` is an independent Rhai [package] that provides functions useful for
scientific computing, inspired by languages like MATLAB, Octave, and R.

On `crates.io`: [`rhai-sci`](https://crates.io/crates/rhai-sci)

On `GitHub`: [`rhaiscript/rhai-sci`](https://github.com/rhaiscript/rhai-sci)

Package name: `SciPackage`


Dependency
----------

`Cargo.toml`:

```toml
[dependencies]
rhai = "{{version}}"
rhai-sci = "0.1"       # use rhai-sci crate
```


Load Package into [`Engine`]
----------------------------

```rust
use rhai::Engine;
use rhai::packages::Package;    // needed for 'as_shared_module'
use rhai_rand::SciPackage;

let mut engine = Engine::new();

// Create new 'SciPackage' instance
let sci = SciPackage::new();

// Load the package
engine.register_global_module(sci.as_shared_module());
```


Package Functions
-----------------

See <https://docs.rs/rhai-sci> for details.