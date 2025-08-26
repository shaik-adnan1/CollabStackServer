# OpenAPI Contract Tooling

## This project uses modern tools to develop, lint, bundle, document, and mock OpenAPI contracts. Below are details on the main tooling: **Redocly CLI** and **Stoplight Prism CLI**.

## Redocly CLI

Redocly CLI is a versatile command-line tool designed to work with OpenAPI specs throughout the API lifecycle. It helps you enforce quality, bundle multi-file specs, generate documentation, and integrate governance rules into your workflow[web:1][web:2][web:5].

### Features

- **Linting:** Check your API spec for correctness, style, and best practices
- **Bundling/Splitting:** Combine and modularize specs for clarity and reuse
- **Documentation:** Instantly generate beautiful API docs from YAML/JSON
- **Governance:** Enforce your own or recommended rulesets via `redocly.yaml`
- **CI/CD Integration:** Automate checks and docs generation in your pipelines

### Installation and Example Commands

```

# Install globally

pnpm add -g @redocly/cli

# Lint API spec

redocly lint openapi.yaml

# Bundle multi-file spec into one

redocly bundle docs/openapi.yaml -o dist/openapi-bundle.yaml

# Generate HTML documentation

redocly build-docs docs/openapi.yaml -o dist/openapi-docs.html

# Preview docs locally

redocly preview-docs openapi.yaml

```

---

## Stoplight Prism CLI

Stoplight Prism CLI is an open-source tool for mocking and proxying REST APIs based directly on OpenAPI specs. It makes local development and contract testing much faster by allowing front-end and integration developers to work before the backend is ready[web:6][web:9][web:12].

### Features

- **Mock Server:** Return realistic or static responses from your OpenAPI contract
- **Proxy:** Forward requests to a live server, validating requests with your spec
- **Custom Behavior:** Dynamically customize responses, status codes, and errors
- **Quick Start for CI/CD:** Works with Docker, Node, and CLI in your pipelines

### Installation and Example Commands

```

# Install globally

pnpm add -g @stoplight/prism-cli

# In this project installed as a dev dependency

pnpm

# Start mock server from OpenAPI file

prism mock openapi.yaml

# Start proxy server for backend

prism proxy openapi.yaml https://api.backend.local

```

---

## Typical Workflow

1. **Define or edit OpenAPI specs** (YAML/JSON)
2. **Lint and validate** with Redocly CLI, using enforceable rulesets
3. **Bundle and split specs** as needed for modularity and distribution
4. **Preview and publish documentation** via Redocly CLI or hosted portal
5. **Mock endpoints** locally with Prism for development/testing
6. **Integrate checks and docs generation in CI pipelines**

---
