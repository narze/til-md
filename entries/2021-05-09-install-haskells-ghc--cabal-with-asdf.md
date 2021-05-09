---
title: Install Haskell's GHC & Cabal with asdf
date: 2021-05-09
tags: haskell, asdf
---

```shell
asdf plugin-add haskell
asdf install haskell 8.10.4
asdf global haskell 8.10.4
asdf reshim haskell 8.10.4
```

However, Cabal installation is failing on my machine

```shell
$ stack install cabal-install

...

Error: While constructing the build plan, the following exceptions were encountered:

In the dependencies for cabal-install-3.4.0.0:
    Cabal-3.2.1.0 from stack configuration does not match ==3.4.*  (latest matching version is 3.4.0.0)
    random-1.1 from stack configuration does not match >=1.2 && <1.3  (latest matching version is 1.2.0)
needed since cabal-install is a build target.

Some different approaches to resolving this:

  * Set 'allow-newer: true' in /Users/narze/.asdf/installs/haskell/8.10.4/stack/config.yaml to ignore all version constraints and build anyway.

  * Recommended action: try adding the following to your extra-deps in /Users/narze/.asdf/installs/haskell/8.10.4/stack/global-project/stack.yaml:

- Cabal-3.4.0.0@sha256:74ca2bc93297dc20b291c8dc721055278aa4a7942b0b5aca86766d407e3cbe5f,30533
- random-1.2.0@sha256:30d72df4cc1d2fe2d445c88f0ee9d21965af7ce86660c43a6c32a6a1d90d51c9,6094

Plan construction failed.
```

Follow the recommended action and Cabal can now be installed, edit stack.yaml and add `extra-deps`

```yaml
packages: ...
resolver: ...

extra-deps:
- Cabal-3.4.0.0@sha256:74ca2bc93297dc20b291c8dc721055278aa4a7942b0b5aca86766d407e3cbe5f,30533  
- random-1.2.0@sha256:30d72df4cc1d2fe2d445c88f0ee9d21965af7ce86660c43a6c32a6a1d90d51c9,6094
```

