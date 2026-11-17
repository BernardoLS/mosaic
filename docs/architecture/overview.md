# Architecture Overview

## Purpose

Mosaic explores a modular mobile architecture in which independently developed modules, built with different technologies, coexist within a single Android application.

The initial implementation brings together native Android using Kotlin, a native Profile module using Jetpack Compose, a Dashboard module using React Native and TypeScript, and a Goals module using Flutter and Dart.

## High-Level Architecture

Mosaic uses a multi-repository approach. Each implementation repository owns its code, dependencies, tests, and development workflow.

The Android Host is the central integration layer. It provides cross-cutting capabilities and coordinates module integration without taking ownership of module-specific business logic.

The `mosaic-contracts` repository defines shared contracts, schemas, examples, and architectural decisions.

## Repositories and Responsibilities

| Repository | Responsibility |
|---|---|
| `mosaic-android-host` | Android application, Host infrastructure, and native Profile module |
| `mosaic-react-native-dashboard` | Dashboard module implementation |
| `mosaic-flutter-goals` | Goals module implementation |
| `mosaic-contracts` | Shared contracts and architectural specifications |

Profile belongs to `mosaic-android-host`. It is a native feature module, not an independent Git repository.

## Android Host Responsibilities

The Host is responsible for application-level and cross-cutting concerns, including:

- Global navigation coordination.
- Shared context distribution.
- Event communication infrastructure.
- Module registry and discovery.
- Module lifecycle coordination.
- Runtime integration and adapters.
- Compatibility validation.
- Consistent error handling at integration boundaries.

The exact implementation and boundaries of these components will evolve as the project moves from architectural specification to implementation.

## Module Responsibilities

Modules own their business capabilities and internal implementation.

Each module is responsible for its domain logic and business rules, internal state, data access and persistence, UI implementation, and module-specific tests and dependencies.

Modules should not depend directly on the internal implementation of other modules. Cross-module integration is mediated by the Host and governed by explicit contracts.

## Contract-Driven Integration

The `mosaic-contracts` repository is the source of truth for shared integration specifications.

The initial foundation covers multi-repository architecture, module manifest, navigation contract, event communication, shared context, error handling, versioning and compatibility, and architecture review.

These specifications define integration structures and responsibilities without requiring every module to use the same framework.

## Architectural Principles

### Host-mediated integration
The Host coordinates cross-module capabilities and provides a controlled integration boundary.

### Module autonomy
Modules own their domain logic, state, and persistence. The Host should not become the owner of module business data.

### Technology independence
Shared contracts describe integration behavior without coupling contract definitions to Kotlin, React Native, or Flutter implementation details.

### Explicit compatibility
Modules declare compatibility requirements, including minimum Host version, contract version, and required capabilities.

### Lifecycle awareness
Module subscriptions and runtime resources must respect module lifecycle. The Host coordinates cleanup when a module is unloaded.

## Current Boundaries and Open Specifications

Some integration details remain open and should be formalized before implementation, including:

- Shared context update event.
- Host-mediated module request/response communication.
- Module Registry discovery metadata.
- Module lifecycle state machine.
- Event publication authorization registry.
- Capability registry and contract adapter policy.

See the ADRs and architecture documents in `mosaic-contracts` for authoritative decisions and current status.

## Related Documentation

- [Architecture Diagram](architecture-diagram.md)
- [Project Scope](../project-scope.md)
- [Mosaic Contracts](https://github.com/YOUR_USERNAME/mosaic-contracts)
