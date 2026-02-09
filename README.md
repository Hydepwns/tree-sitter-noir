# tree-sitter-noir

Tree-sitter grammar for the [Noir](https://noir-lang.org/) zero-knowledge programming language.

## Features

- Full syntax support for Noir language constructs
- Zero-knowledge specific syntax (`constrain`, `assert`, `assert_eq`)
- Comptime and unconstrained functions
- Structs, enums, traits, and impl blocks
- Generic types and turbofish syntax
- Format strings and interpolation
- Comprehensive syntax highlighting queries

## Installation

### npm

```bash
npm install tree-sitter-noir
```

### Cargo

```bash
cargo add tree-sitter-noir
```

## Usage

### With tree-sitter CLI

```bash
# Parse a file
tree-sitter parse example.nr

# Run tests
tree-sitter test
```

### Node.js

```javascript
const Parser = require("tree-sitter");
const Noir = require("tree-sitter-noir");

const parser = new Parser();
parser.setLanguage(Noir);

const tree = parser.parse(`
fn main() {
    let x: Field = 5;
    assert(x == 5);
}
`);
```

## File Types

- `.nr` - Noir source files

## Queries

The grammar includes the following query files:

- `queries/highlights.scm` - Syntax highlighting
- `queries/locals.scm` - Local variable scoping
- `queries/injections.scm` - Language injections

## Development

```bash
# Install dependencies
npm install

# Generate parser from grammar
npm run build

# Run tests
npm test

# Build WASM version
npm run build-wasm
```

## License

MIT
