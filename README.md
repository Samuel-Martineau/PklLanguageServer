<div align="center">

[![Discord][discord badge]][discord]

# PklLanguageServer

Language server for Apple Pkl language written in Swift.

</div>

## Overview

This language server is still in a **very early development stage**.

The goal of this project is to make a fully functional Language Server for Pkl language and have lots of fun.

## Contributing

I would really love to make it a community driven project, so don't hesitate to contribute or help in any way possible.

The [Discord Server][discord] is there for any question, help, advice or just casual chatting.

Also check out [Unofficial Pkl Community Discord Server][community discord], lots of great people there discussing Pkl. They also have a channel about LSPs!

And don't forget to check [Code of Conduct](CODE_OF_CONDUCT.md).

## Feature Status

| Feature               | Status |
| --------------------- | :----: |
| Completion            |   🟢   |
| Definition            |   🟢   |
| Diagnostics           |   🟢   |
| Document Symbols      |   🟢   |
| Renaming              |   🟠   |
| Semantic Highlighting |  TBA   |

- **🟢** -- Feature is working
- **🟠** -- Feature is working, however due to early development stage may be incomplete or not working as intended (disabled by default, can be enabled with `--enable-experimental-features`)
- **🔴** -- Not planned
- **TBA** -- Work on the feature is not yet in progress, but it's being looked into
- **WIP** -- Development work on the feature is actively progressing

### State of features and details

- Module imports are indexed for completion only with relative paths or standard pkl library. `import*` expression also does not work yet.

- Diagnostics are working on a basic level. Type checking isn't a thing yet.

## Installing and running from source

Install [libjemalloc][libjemalloc]:

(Alternatively, you can comment out benchmarking target in `Package.swift` and skip this step)

```
# macOS (Homebrew)
brew install jemalloc

# Linux
sudo apt install libjemalloc-dev
```

Clone repository and build the project:

```
git clone https://github.com/jayadamsmorgan/PklLanguageServer --recurse-submodules
cd PklLanguageServer
make install
```

Now you can run the server with:

```
pkl-lsp-server
```

Check help for more options:

```
pkl-lsp-server -h
```

## Editor support

- [Neovim](Editors/Neovim/README.md)
- [VSCode](Editors/VSCode/README.md)

## Debugging

`pkl-lsp-server` will use standard output and JSONRPC connection with `error` log level to print logs.

`pkl-lsp-server -log debug` will print out logs with debug log level.

Use your client's LSP log or standard output to check the logs.

## Honorable mentions

Huge shoutout to Mattie, creator of [LanguageServerProtocol][lsplib] and [SwiftTreeSitter][tslib] libraries.

This project could not have been possible without his great work and huge help. Check out his awesome [blog][matts blog].

[discord]: https://discord.gg/GTe5JvcT
[community discord]: https://discord.gg/3PufS9Jn
[discord badge]: https://img.shields.io/badge/Discord-purple?logo=Discord&label=Chat&color=%235A64EC
[libjemalloc]: https://github.com/jemalloc/jemalloc
[lsplib]: https://github.com/ChimeHQ/LanguageServerProtocol
[tslib]: https://github.com/ChimeHQ/SwiftTreeSitter
[matts blog]: https://www.massicotte.org/
