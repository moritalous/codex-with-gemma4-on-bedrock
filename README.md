# Codex with Gemma 4 on Berock

This project provides a development environment for using Codex (powered by Gemma 4 on Amazon Bedrock).

## 🛠 Tooling & Setup

This project uses **mise** for tool version management to ensure a consistent development environment across different machines.

### Prerequisites

Install [mise](https://mise.jdx.dev/) first.

### Installation

Once mise is installed, trust the configuration and install all required tools (Bun, Gitleaks, etc.):

```bash
mise trust
mise install
```

## 🚀 Getting Started

To run the codex environment:

```bash
bun run codex
```

Note: Ensure your AWS credentials are configured for the specified region (us-east-1).

## 🛡 Security & Quality

To prevent accidental leakage of secrets, this project integrates **Gitleaks**.

### Pre-commit Hook

A git pre-commit hook is configured to automatically scan staged files for secrets before every commit. If a secret is detected, the commit will be aborted.

### Manual Scanning

You can also run secret scans manually using the provided scripts:

- Scan staged files:
  ```bash
  bun run lint:secrets
  ```
- Scan entire repository history:
  ```bash
  bun run lint:secrets:all
  ```

## 📜 License

This project is licensed under the terms specified in the [LICENSE](LICENSE) file.
