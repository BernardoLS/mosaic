# Getting Started

## Project Overview

Mosaic is organized as a multi-repository project. Each repository contains an independent part of the application or its shared architectural specifications.

Before attempting to build the application, review the repository responsibilities and current project status.

## Repositories

Clone the repositories you need:

```bash
git clone https://github.com/YOUR_USERNAME/mosaic.git
git clone https://github.com/YOUR_USERNAME/mosaic-android-host.git
git clone https://github.com/YOUR_USERNAME/mosaic-react-native-dashboard.git
git clone https://github.com/YOUR_USERNAME/mosaic-flutter-goals.git
git clone https://github.com/YOUR_USERNAME/mosaic-contracts.git
```

Replace `YOUR_USERNAME` with the GitHub account or organization that owns the repositories.

## Recommended Reading Order

1. Read the main [README](../README.md).
2. Review the [Architecture Overview](architecture/overview.md).
3. Explore the [Architecture Diagram](architecture/architecture-diagram.md).
4. Review the ADRs, schemas, and examples in `mosaic-contracts`.
5. Follow setup instructions in each implementation repository.

## Build and Execution

Build and execution instructions will be documented in the corresponding implementation repositories once their project foundations are available.

This document intentionally does not prescribe build commands or environment versions that have not yet been established.

## Contributing and Feedback

Mosaic is an evolving engineering project. Questions, architectural feedback, and discussions are welcome.

For changes to shared integration contracts and architectural decisions, use `mosaic-contracts` as the reference point.
