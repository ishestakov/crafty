# Installation

This project is organized with Lerna to manage multiple modules in a single project.

```bash
npm install
npm run bootstrap
```

Those two commands install all dependencies in each package.

## Using the experiment project

There is a small example project within Crafty to experiment with features outside of integration tests.
You can tweak the configuration in any way you like in this project.

```bash
cd experiment
npm install
```

Then you can run one of 
- `npm run build` to build the project once
- `npm run test` to execute the tests
- `npm run watch` to run the compilation in watch mode

# Development

## Running tests

```bash
npm run jest
```

Tests are currently mainly integration tests in the `packages/integration` directory.

Those tests do a run of the configuration with various configuration of presets and register the results in snapshots.

# Release

## Releasing

Update the version number in `package.json`

```bash
export NODE_TLS_REJECT_UNAUTHORIZED=0

# Do a proper install
node_modules/.bin/lerna clean
node_modules/.bin/lerna bootstrap

# Release a canary version to test in a prokect
node_modules/.bin/lerna publish --canary

# -> Test inside one or more projects

node_modules/.bin/lerna publish --exact
```