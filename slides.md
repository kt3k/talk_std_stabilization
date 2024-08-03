class: middle, center

# Summary <br/> of Standard Library stabilization

---

class: middle, center

Yoshiya Hinosawa @kt3k

Call me Yoshi

<img src="./assets/hinosawa.jpg" width="180" />

---

Deno Standard Library is collection of 38 packages.

- std/http
- std/testing
- std/fmt

---

We stabilized 

---

Deno Standard Library

- When was it started?
- Why does it exist?

---

Deno Standard Library

- It didn't exist at the beginnig of Deno
- It first appeared in the source code in [Dec 2018](https://github.com/denoland/deno_std/commit/99e276eb89fbe0003bfa8d9e7b907ff3ef19ee47) (a half year later the beginning of Deno)
- It was first publicly explained in JS Fest in April, 2019 [Video](https://www.youtube.com/watch?v=z6JRlx5NC9E&t=2482s)

---

Dependency Hell

- Node.js didn't have standard library, and had small core APIs.
- People started publishing lot of one-liner-ish modules to npm.
- That caused 'dependency hell'

Deno Std was intended as the solution to this issue.

---

Now Deno Std seems very successful!

- Most Deno programs use standard library
- Not many competitions against the standard library
- It seems well accepted, well understood by the community
- Node.js now introduced to its core some of what deno_std does.
  - e.g. flags, bdd testing, dotenv, etc

---

class: middle center inverse

Updates from 2023 - 2024

---

# std/expect

```
expect(foo).toEqual(42);
expect(bar).toEqual({ x: 1 });
...
```

- Mostly Jest compatible
- Not 100% compatible yet
- Many contributions have been coming form the community

---

# std/ulid

- UUID alternative
- 6-byte timestamp part + 10-byte random part
- Useful for KV keys

---

# std/cli

- std/flags are moved to here
- There's also other utils such as `Spinner`, `promptSecret`

---

# std/url

- url version of `std/path`

```ts
dirname(new URL("https://example.com/foo/bar"))
// => new URL("https://example.com/foo")
dirname(import.meta.url);
// returns parent dir of this file
```

---

# Other new modules

- `std/ini` handles INI files
- `std/webgpu`, essentials for WebGPU programming
- `std/text` has utils about levenshtein distance
- `std/net` currently only has `getAvailablePort` util

---

class: middle center inverse

Updates towards the Stabilization

---

# Standard library will be split into small independent modules

```
https://deno.land/std@0.220.0/path/mod.ts

↓↓↓

jsr:@std/path@0.220.0
```


---


# Stabilities of modules are defined

- 19 modules are stable
- 22 modules are unstable

stable modules will become v1.0.0 when we migrate to JSR

---

# Started publishing to JSR

- Standard modules are now available from both JSR and deno.land/std

```js
import { assert }
  from "https://deno.land/std@0.220.0/assert/mod.ts";

import { assert } from "jsr:@std/assert@0.220.0";
```

Currently these 2 have the same versions, but that might change in the future.


---

class: middle center inverse

Some future plans and topics

<!---

`std/dotenv` vs `--env`

- They have significant overlap,
- but also have some difference

Should we remove `std/dotenv` or keep both?

--->
---

# Node.js compat of @std/fs

- ~70% of @std modules are compatibile with All runtimes.
- Maybe it's good to expand it
- `@std/fs` is a good first candidate

---

# Node.js compat of @std/fs

- `@std/fs` only has few APIs such `ensureFile`, `walk`, `move`, etc
- Basic FS APIs are in Deno namespace
- What APIs to include in @std/fs is not obvious
- How to implement is also not obvious
- Currently community seems confused by this direction.

---

# When to migrate to JSR?

- Currently we use conversion script
- That prevents us to do independent versioning of each module
- That prevents us to publish v1 of each module
- When to migrate? in a month? in 3 months? in 6 months?

---

# Versioning of /std after JSR migration

- Do we keep publishing the same thing to `/std`?
- How to version `/std` in that case?
- Maybe we don't publish to `/std` anymore except security fixes?

---
class: middle center

Thanks
