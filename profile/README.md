Lots of server need to get the "real" client IP[^1] from `X-Forwarded-For`, `Forwarded`, and other HTTP headers. It seems like it should easy to do so and lots of developers assume it is, but... it's not, and it [gets done incorrectly far too often](https://adam-p.ca/blog/2022/03/x-forwarded-for/). This can and will lead to bugs and vulnerabilities.

This organization is an attempt to create gold-standard implementations of the strategies for handling those headers. The first implementation is in Go, and will helpful be the reference for all others.

Feel free to use this code however you want. And it would be great if implementations in other languages can be contributed.

[^1]: The "real" is always quoted, because a) if a leftmost strategy is used, the IP can be spoofed, and b) if a rightmost strategy is used, the IP could belong to an intermediate proxy. But this is the best that can be done.
