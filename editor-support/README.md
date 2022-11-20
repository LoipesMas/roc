# Language Server

I put up a language server in this fork. It's not complete, and includes support for

- Inline diagnostics
- Hover support for get types of values

## Building

Build a local binary via

```bash
cargo build -p roc_lang_srv --release
```

which will give you a language server binary at

```bash
target/release/roc_ls
```

You can then configure your editor's LSP implementation to please point at the
build `roc_ls`. For example, in my [coc.nvim](https://github.com/neoclide/coc.nvim)
configuration, I have

```json
{
  "languageserver": {
    "roc": {
      "command": "<path to roc>/target/release/roc_ls",
      "filetypes": ["roc"]
    }
  }
}
```