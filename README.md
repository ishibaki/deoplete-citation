# deoplete-citation

`deoplete-citation` is the deoplete source, which enables the completion of citation-keys.

![sample movie](./mov/sample.gif)

Inserted citation-keys can be used to generate a reference list through [`pandoc`](https://pandoc.org/MANUAL.html#citations).

## Requirements

- [`deoplete`](https://github.com/Shougo/deoplete.nvim)
- [`pybtex`](https://pybtex.org)
- `$HOME/.pandoc/library.bib` file

## How to Use

1. Make `library.bib` file in the `~/.pandoc` directory.
  - You can modify the filepath, but if you use `pandoc`, the default setting is the best.
2. Copy `deoplete-citation.py` in `$XDG_CONFIG_HOME/nvim/rplugin/python3/deoplete/sources/`.
3. The prefix, `@`, will start the completion.
