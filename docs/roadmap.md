# Roadmap

This roadmap describes the intended development direction of Mosaic. It is a planning document, not a claim that the listed work has already been completed.

## Phase 1 — Architectural Foundation

**Status: Documented**

- [x] Define the multi-repository architecture.
- [x] Define the Module Manifest.
- [x] Define the Navigation Contract.
- [x] Define Event Communication.
- [x] Define Shared Context.
- [x] Define Error Handling.
- [x] Define Versioning and Compatibility.
- [x] Consolidate the initial architecture review.
- [x] Validate the initial JSON Schema examples.

See `mosaic-contracts` for formal specifications and ADRs.

## Phase 2 — Android Host Foundation

**Status: Planned**

- Establish the Android project foundation.
- Define Gradle modules and dependency boundaries.
- Establish build conventions and quality checks.
- Implement the initial Host composition.
- Define and implement the first version of the Module Registry.
- Establish the initial navigation and module lifecycle foundations.

## Phase 3 — Native Module Integration

**Status: Planned**

- Implement the Profile module with Kotlin and Jetpack Compose.
- Integrate Profile into the Host.
- Exercise navigation and shared context contracts.
- Establish module-level testing and build workflows.

## Phase 4 — React Native Integration

**Status: Planned**

- Establish the React Native Dashboard project.
- Integrate the React Native runtime with the Android Host.
- Implement the Dashboard module entry point.
- Exercise Host-mediated navigation and communication.
- Evaluate initialization, lifecycle, and runtime performance.

## Phase 5 — Flutter Integration

**Status: Planned**

- Establish the Flutter Goals project.
- Integrate the Flutter runtime with the Android Host.
- Implement the Goals module entry point.
- Exercise cross-module navigation and communication.
- Evaluate initialization, lifecycle, and runtime performance.

## Phase 6 — Integration, Reliability, and Evaluation

**Status: Planned**

- Complete integration scenarios across all modules.
- Formalize remaining contracts as implementation requires.
- Improve error handling and compatibility validation.
- Evaluate startup time, memory usage, and runtime overhead.
- Document technical trade-offs and lessons learned.
- Review the architecture based on implementation evidence.

## Roadmap Principles

The roadmap is intentionally iterative. Implementation findings may lead to changes in priorities, architecture, or scope.

Completed items represent documented or validated work only. Planned items will be marked complete as their implementation or validation is actually finished.
