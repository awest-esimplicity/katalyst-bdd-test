# testconvergence

Internal monorepo for Playwright BDD testing utilities and scaffolding.

## Packages

| Package | Description |
|---------|-------------|
| **@kata/stack-tests** (`stack-tests/`) | Reusable fixtures, ports, adapters, and step definitions for API/UI/TUI testing |
| **@kata/create-stack-tests** (`create-stack-tests/`) | CLI to scaffold a new Playwright-BDD test project |

## Quick Start

```bash
# Install dependencies
npm install

# Build the library
npm run build -w @kata/stack-tests

# Scaffold a new test project
npx @kata/create-stack-tests my-tests
```

## Documentation

Full documentation is available in the [`docs/`](./docs/) folder:

- **[Getting Started](./docs/getting-started/)** - Installation, quick start, project setup
- **[Concepts](./docs/concepts/)** - Architecture, world state, test lifecycle, tag system
- **[Guides](./docs/guides/)** - API, UI, TUI, and hybrid testing guides
- **[Reference](./docs/reference/)** - API reference for ports, adapters, fixtures, and steps
- **[Contributing](./docs/contributing/)** - How to contribute to the project

## Examples

Runnable example projects are in the [`examples/`](./examples/) folder:

| Example | Description |
|---------|-------------|
| [api-example](./examples/api-example/) | REST API testing with JSONPlaceholder |
| [ui-example](./examples/ui-example/) | Browser UI testing with The Internet |
| [tui-example](./examples/tui-example/) | Terminal UI testing |
| [full-stack-example](./examples/full-stack-example/) | Combined API + UI + TUI testing |

## Architecture

The framework uses a **Ports and Adapters** pattern:

```
Feature Files (.feature)
        |
        v
  Step Definitions
        |
        v
     Ports (interfaces)
        |
        v
   Adapters (implementations)
        |
        v
  Playwright / tui-tester
```

### Available Ports

- **ApiPort** - HTTP API testing
- **UiPort** - Browser UI testing
- **TuiPort** - Terminal UI testing
- **AuthPort** - Authentication handling
- **CleanupPort** - Test data cleanup

### Tag System

| Tag | Description |
|-----|-------------|
| `@api` | API-only scenarios |
| `@ui` | Browser UI scenarios |
| `@tui` | Terminal UI scenarios |
| `@hybrid` | Cross-layer scenarios |

## Development

```bash
# Build all packages
npm run build --workspaces

# Run tests
npm test --workspaces

# Lint code
npm run lint --workspaces
```

## Requirements

- Node.js >= 18.0.0
- npm >= 9.0.0
- Playwright >= 1.49.0
- playwright-bdd >= 8.3.0

## Notes

- Packages are intended for internal use via GitHub Packages
- Keep `@playwright/test` and `playwright-bdd` versions aligned with peer requirements
- TUI testing requires `tui-tester` (optional peer dependency)

## License

SEE LICENSE IN LICENSE
