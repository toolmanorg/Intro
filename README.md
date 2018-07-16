# Intro

toolman.org publishes a significant number of Go libraries (or, soon will) and we use a peculiar naming scheme for our repos on github.com.  Since GitHub chooses to enforce a flat namespace on their users, toolman.org employs a custom `go get` redirector that translates GitHub repository names into a hierarchical package structure for Go libraries.

Here's an example: the GitHub repo `toolmanorg/security-tools-passwd` is the home for the Go library `toolman.org/security/tools/passwd`.  In fact, since this package uses an import path override, that's the only name you can use to reference this package. You install it with `go get toolman.org/security/tools/passwd` and you use it in your code with `import "toolman.org/security/tools/passwd"`.

The translation rules (from GitHub repo name to Go package name) are quite simple:

1. `toolmanorg` becomes `toolman.org`
1. all `-` characters become `/` characters
1. except, double-dashes (e.g. `--`) translate to single dashes (`-`) in the Go package name

Enjoy!
