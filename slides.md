class: middle, center

# Story of<br />STD stabilization

Yoshi @ Warsaw Offsite

---

class: middle, center

Yoshiya Hinosawa @kt3k

Call me Yoshi

<img src="./assets/hinosawa.jpg" width="180" />

---

# Summary

- We have stabilized 30 of the 38 packages in the Deno Standard Library over a period of about 3 month (May - Aug)

---

# STD stabilization

- The motivation
- The methods
- The outcome

---

class: middle, center

# The motivation

---

# The motivation

- Deno Standard Library has a good reputation for its quality, broad scope, and maintainance

---

# A weakness of STD

One weakness of the Deno Standard Library is that it is still in version 0.x.

---

# 0.x STD

- Deno Community was relatively tolerant to version being 0.x
- We gradually found out it's larger problem for entreprise users
- We set the stabilization as a requirement for Deno 2.0

<!---

# Timeline

- 2/6 Dual publish to deno.land/x/ and JSR started https://github.com/denoland/std/pull/4281
- 4/17 RC plan announced https://github.com/denoland/std/pull/4600
- 4/29 JSR migration https://github.com/denoland/std/pull/4650
- 5/7 The first RC (std/bytes)
- 6/6 The first stabilization (std/bytes)
- 7/10 The last RC landed (std/fmt)
- 8/5 The last stabilization (std/csv)

-->

---
class: middle, center

# The methods (How)

---

# The blocker for stabilization

- It has too broad scope
- We can't stabilize it as a whole as we are too unsure about some parts
- Some parts are used widely, battle-tested, very mature
- Some parts are recently invented by some contributors, and not used enough widely

---

# The blocker for stabilization

=> It's impossible to stabilize the entire Standard Library

---

# Split STD

- We gave up to stablize the entire STD
- We split STD into 38 packages
- We can now stabilize packages one by one
- We can even choose not to stabilize some

---

# Split STD

- This idea was unpopular among some community members
--

  - No prior example
  - Managing each version of every package is cumbersome

--

We might revisit the idea of single versioned STD in the future

---

# RC process

We decided to publish RC a month prior to 1.0.0

- This is to give the community an opportunity to check it.
- Deno owns STD, but the development is more driven by community
- It feels wrong to stabilize things without listening to them

---

# Quality Bar

We also set quality bars for a package to be stabilized

- A package need to be documented 100%
- A package need to be tested reasonably

--

These are mostly thanks to Asher 👍

---

class: middle, center

# The outcome

---

# Timeline of RC process

- 5/7 The first RC - std/bytes@1.0.0-rc.1
- 6/6 The first 1.0.0 - std/bytes@1.0.0
- 7/10 The last RC - std/fmt@1.0.0-rc.1
- 8/5 The last 1.0.0 - std/csv1.0.0

---

# Stabilization Result

- 30 packages stabilized 🎉
- 8 packages remain unstable

---

# 30 stable packages

<table align="center">
<tr>
<td>bytes&nbsp;&nbsp;&nbsp;</td>
<td>collections&nbsp;&nbsp;&nbsp;</td>
<td>media-types&nbsp;&nbsp;&nbsp;</td>
</tr>
<tr>
<td>crypto&nbsp;&nbsp;&nbsp;</td>
<td>encoding&nbsp;&nbsp;&nbsp;</td>
<td>uuid&nbsp;&nbsp;&nbsp;</td>
</tr>
<tr>
<td>assert&nbsp;&nbsp;&nbsp;</td>
<td>data-structures&nbsp;&nbsp;&nbsp;</td>
<td>html&nbsp;&nbsp;&nbsp;</td>
</tr>
<tr>
<td>msgpack&nbsp;&nbsp;&nbsp;</td>
<td>path&nbsp;&nbsp;&nbsp;</td>
<td>regexp&nbsp;&nbsp;&nbsp;</td>
</tr>
<tr>
<td>toml&nbsp;&nbsp;&nbsp;</td>
<td>async&nbsp;&nbsp;&nbsp;</td>
<td>cli&nbsp;&nbsp;&nbsp;</td>
</tr>
<tr>
<td>text&nbsp;&nbsp;&nbsp;</td>
<td>ulid&nbsp;&nbsp;&nbsp;</td>
<td>expect&nbsp;&nbsp;&nbsp;</td>
</tr>
<tr>
<td>front-matter&nbsp;&nbsp;&nbsp;</td>
<td>fs&nbsp;&nbsp;&nbsp;</td>
<td>json&nbsp;&nbsp;&nbsp;</td>
</tr>
<tr>
<td>jsonc&nbsp;&nbsp;&nbsp;</td>
<td>streams&nbsp;&nbsp;&nbsp;</td>
<td>yaml&nbsp;&nbsp;&nbsp;</td>
</tr>
<tr>
<td>fmt&nbsp;&nbsp;&nbsp;</td>
<td>http&nbsp;&nbsp;&nbsp;</td>
<td>net&nbsp;&nbsp;&nbsp;</td>
</tr>
<tr>
<td>semver&nbsp;&nbsp;&nbsp;</td>
<td>testing&nbsp;&nbsp;&nbsp;</td>
<td>csv&nbsp;&nbsp;&nbsp;</td>
</tr>
</table>

---

# Stable 30 package

- Most major important packages have been stabilized
  - e.g. path, async, assert, fs, streams, testing
- It's safe to say STD is (mostly) stabilized

---
# 8 Unstable packages

- archive
- log
- webgpu
- datetime
- ini
- io
- url
- dotenv

---
# The quality improvements

- Stable packages are now 100% documented including function parameters, parameter options
- Test coverage is largely improved
  - 91% -> 96.4% (less than half uncovered lines)

--

Kudos to Asher

---
class: middle, center

# Thanks!



