# Rust vendored sources

The Zephyr project requires that all sources needed to build within
the Rust project are mirrored by the project, and downloaded by west
before the build starts.

When building Zephyr applications in Rust, the following crates are
needed, at build time:

- aho-corasick
  - version: 1.1.3
  - repo: https://github.com/BurntSushi/aho-corasick
  - license: Unlicense OR MIT
- memchr
  - version: 2.7.4
  - repo: https://github.com/BurntSushi/memchr
  - license: Unlicense OR MIT
- regex
  - version: 1.10.5
  - repo: https://github.com/rust-lang/regex
  - license: Apache-2.0 OR MIT
- regex-automata
  - version: 0.4.7
  - repo: https://github.com/rust-lang/regex/tree/master/regex-automata
  - license: Apache-2.0 OR MIT
  - Note: This is a subtree of regex
- regex-syntax
  - version: 0.8.4
  - repo: https://github.com/rust-lang/regex/tree/master/regex-syntax
  - license: Apache-2.0 OR MIT
  - Note: This is a subtree of regex

# Maintaining trees

This repository tracks the upstream trees using the `git subtree`
command.  Versions are pulled in with commands similar to:

    git subtree add --prefix=memchr https://github.com/BurntSushi/memchr 2.7.4

Newer versios can be brought in with a similar command, but using
`pull` instead of `add`.

This command brings in the upstream history, and creates a merge
commit from the original.  It is important to not rebase these changes
when bringing them into github.
