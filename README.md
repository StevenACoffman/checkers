# checkers - create a checksum of an entire directory and its contents.

I wanted to generate a checksum of an entire directory and its contents. For this, there's two approaches, one hashes the files in a directory, the other hashes a zip while ignoring non-deterministic information like file date.

Extra metadata isn't necessarily meaningful for file contents and should probably be ignored.

The [Parallel digestion](https://blog.golang.org/pipelines) example from the https://blog.golang.org/pipelines, starting from the Digesting a tree section, gave me this code, but I intend to modify it to suit my needs.

Specifically, the parallel version: https://blog.golang.org/pipelines/parallel.go

For `go mod` Russ Cox wrote [dirhash](https://github.com/golang/mod/blob/ce943fd02449f621243c9ea6e64098e84752b92b/sumdb/dirhash/hash.go).

