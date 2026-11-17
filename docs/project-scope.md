# Project Scope

## Project Objective

Mosaic explores the architecture and implementation challenges of integrating native Android, React Native, and Flutter modules within a single mobile application.

The goal is to build a practical technical case demonstrating modular architecture, cross-framework interoperability, contract-driven integration, and independent module evolution.

## Initial Scope

- An Android application acting as the central Host.
- A native Profile feature implemented with Kotlin and Jetpack Compose.
- A Dashboard feature implemented with React Native and TypeScript.
- A Goals feature implemented with Flutter and Dart.
- A shared contract repository defining integration structures and architectural decisions.
- Host-mediated navigation, context, event communication, lifecycle coordination, and compatibility validation.

## Repository Organization

| Repository | Scope |
|---|---|
| `mosaic-android-host` | Android Host infrastructure and native Profile feature |
| `mosaic-react-native-dashboard` | React Native Dashboard feature |
| `mosaic-flutter-goals` | Flutter Goals feature |
| `mosaic-contracts` | Shared schemas, examples, ADRs, and architecture specifications |

Profile is part of the Android Host repository, not a separate repository.

## Engineering Focus

### Architecture and Modularity
Clear module boundaries, responsibility ownership, dependency management, and independent development workflows.

### Cross-Framework Integration
The practical integration of native Android, React Native, and Flutter within one application.

### Communication and Context
Contract-driven navigation, event communication, and shared context across module boundaries.

### Lifecycle and Runtime Management
Module registration, initialization, loading, unloading, resource cleanup, and runtime-specific integration concerns.

### Compatibility and Reliability
Version compatibility, capability requirements, error normalization, and failure handling across integration boundaries.

### Performance and Developer Experience
Runtime overhead, startup behavior, memory usage, build workflows, debugging, and the experience of developing modules independently.

## Out of Scope for the Initial Phase

The initial implementation is Android-focused. The following are not part of the initial scope unless explicitly added through a future scope revision:

- iOS Host implementation.
- Production-scale backend services.
- A public plugin marketplace or third-party module ecosystem.
- A generalized framework intended to support every mobile runtime.
- Premature optimization before baseline behavior and measurements exist.

## Scope Evolution

Mosaic is an evolving engineering project. Changes to scope should be documented as the architecture and implementation reveal new requirements.

Architectural decisions and formal integration specifications belong in `mosaic-contracts`.
