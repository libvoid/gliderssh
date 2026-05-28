# libvoid/gliderssh

[![Go Reference](https://pkg.go.dev/badge/github.com/libvoid/gliderssh.svg)](https://pkg.go.dev/github.com/libvoid/gliderssh)
[![Go Report Card](https://goreportcard.com/badge/github.com/libvoid/gliderssh)](https://goreportcard.com/report/github.com/libvoid/gliderssh)

This is a [libvoid](https://libvoid.com) fork of [gliderlabs/ssh](https://github.com/gliderlabs/ssh).

This Go package wraps the [crypto/ssh
package](https://pkg.go.dev/golang.org/x/crypto/ssh) with a higher-level API for
building SSH servers. The goal of the API was to make it as simple as using
[net/http](https://golang.org/pkg/net/http/), so the API is very similar:

```go
package main

import (
    "io"
    "log"

    ssh "github.com/libvoid/gliderssh"
)

func main() {
    ssh.Handle(func(s ssh.Session) {
        io.WriteString(s, "Hello world\n")
    })

    log.Fatal(ssh.ListenAndServe(":2222", nil))
}
```

## Examples

A bunch of great examples are in the `_examples` directory.

## Usage

[See Go reference.](https://pkg.go.dev/github.com/libvoid/gliderssh)

## Contributing

Pull requests are welcome! However, since this project is very much about API
design, please submit API changes as issues to discuss before submitting PRs.

## License

[BSD](LICENSE)
