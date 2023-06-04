Building a DNS server in Rust
=============================

The internet has a rich conceptual foundation, with many exciting ideas that
enable it to function as we know it. One of the really cool ones is DNS. Before
it was invented, everyone on the internet - which admittedly（不可否认地） wasn't that many at
that stage - relied (依赖｜依靠) on a shared file called HOSTS.TXT, maintained by the Stanford
Research Institute. This file was synchronized manually through FTP, and as the
number of hosts grew, so did the rate of change and the unfeasibility (不可行) of the
system. In 1983, Paul Mockapetris set out to find a long term solution to the
problem and went on to design and implement DNS. It's a testament (证据｜证明) to his
genius that his creation has been able to scale from a few thousand
computers to the Internet as we know it today.

With the combined (共同的) goal of gaining a deep understanding of DNS, of doing
something interesting with Rust, and of scratching some of my own itches (痒),
I originally set out to implement my own DNS server. This document is not
a truthful chronicle (编年史) of that journey, but rather an idealized (理想化的) version of it,
without all the detours (绕道，绕行)  I ended up taking. We'll gradually implement a full
DNS server, starting from first principles.

 * [Chapter 1 - The DNS protocol](/chapter1.md)
 * [Chapter 2 - Building a stub resolver](/chapter2.md)
 * [Chapter 3 - Adding more Record Types](/chapter3.md)
 * [Chapter 4 - Baby's first DNS server](/chapter4.md)
 * [Chapter 5 - Recursive Resolve](/chapter5.md)

Samples
-------

Each chapter has a corresponding (相应的) sample which contains the full code up to
that point in the guide, named `sample1.rs` through `sample5.rs`. These can be
run using, for first chapter, `cargo run --example sample1`.

Revision History
----------------

 * June 2020 - Fixed a security vulnerability (弱点) in `read_qname` which allowed for
   a malicious packet to trigger an infinite loop. Modernized the code to
   conform to current rust practices, and fixed various ugly inefficiencies (效率低).
 * July 2016 - Initial version
