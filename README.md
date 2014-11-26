fsweb
=====

A literate programming tool written in Forth.

Inspired by [aweb](https://github.com/agl/aweb),
and originally intended for use with my Kestrel project,
`fsweb` aims to make writing literate software easier and quicker.
To facilitate maintenance and portability to the Kestrel platform,
I wrote `fsweb` in Forth.
Forth is far simpler to port than C,
and especially easier than languages dependent upon or themselves written in C.

Other literate programming tools suffer from problems ranging from inconvenient to blocking.
For example,
`aweb` is written in Haskell,
which pretty much guarantees that
I'll never be able to run it under Kestrel's operating system, STS.
Porting GHC to over to STS will be way too hard,
with virtually no real benefit.
Meanwhile, a tool like `CWEB` might be more easily ported because it's written in C;
however, we still need to port a C compiler, its supporting libraries, _and_
its supporting toolchain (a not insignificant amount of work on my part).
`noweb`, despite its minimalism, might actually be the hardest to port,
for it requires porting _several_ different languages to STS
(all of which written in C)
just to get its dependencies working.
The nice thing about Forth is how easy it can be migrated from platform to platform.

I currently use `aweb` to bootstrap `fsweb`.
Eventually, `fsweb` will be used to write itself.
This implies that `fsweb` shares markup syntax with `aweb`.
Ideally, switching between `aweb` and `fsweb` should be entirely transparent;
they both should produce compatible output for the same input.
