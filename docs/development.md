# Development

## Setup

Install Bun 1.4.2 or newer.

```sh
bun ci
```

## Tests

`make test` runs the typecheck, unit tests, and HTTP integration tests. The integration tests use local servers and do not require a Brave API key.

## GitHub Actions

The [test workflow](../.github/workflows/test.yml) runs `make test` on pull requests and pushes to `main`.

## Dependencies

`make upgrade-dependencies` updates `package.json` to the latest exact versions and refreshes `bun.lock`. Run `make test` afterward.

## Publishing

Change the version in `package.json`, authenticate with npm, and run `make publish`. It runs the tests, previews the package with `bun pm pack --dry-run`, then publishes to npm.
