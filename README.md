# Simple Web Server

A small, dependency-free HTTP web server written in C. It uses POSIX sockets and
one thread per request (pthreads) to serve static files from a web root directory.

## Features

- Serves static files (HTML, CSS, images, plain text, and more)
- Handles GET and POST requests
- Detects MIME types by file extension
- Basic directory-traversal protection
- Multi-threaded: a new thread handles each incoming request
- Configured through a simple `.serverConfig` file

## Requirements

- A C compiler (`gcc` or `clang`)
- A POSIX system (Linux / macOS)

## Build

```bash
make
```

This produces the `serverd` binary.

## Run

```bash
./serverd
```

Then open http://localhost:8080 in your browser.

## Configuration

Settings live in `.serverConfig`. The order of the values matters — do not
rearrange them:

```
./www          # web root directory
index.html     # default file served for "/"
8080           # port to listen on
```

## Project layout

```
server.c        # server source
Makefile        # build rules
.serverConfig   # runtime configuration
www/            # web root (the site files)
```

## License

Released under the MIT License — see [LICENSE](LICENSE).

## Author

Pavneet Singh — https://github.com/pavnxet
