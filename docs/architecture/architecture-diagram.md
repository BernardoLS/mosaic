# Architecture Diagram

This document presents a high-level view of Mosaic's architecture and repository boundaries.

## System Context

The Android Host is the application integration layer. It coordinates the native and cross-platform modules, while the contracts repository defines shared integration specifications.

```mermaid
flowchart TB
    subgraph Host["Android Host — Kotlin"]
        App["Android Application"]
        Navigation["Navigation"]
        Context["Shared Context"]
        Events["Event Bus"]
        Registry["Module Registry"]
        Lifecycle["Lifecycle Management"]
        Profile["Profile Module<br/>Jetpack Compose"]
    end

    Dashboard["Dashboard Module<br/>React Native / TypeScript"]
    Goals["Goals Module<br/>Flutter / Dart"]
    Contracts[("Mosaic Contracts<br/>Schemas / ADRs / Specifications")]

    App --> Navigation
    App --> Context
    App --> Events
    App --> Registry
    App --> Lifecycle
    App --> Profile

    Host --> Dashboard
    Host --> Goals

    Contracts -. "defines shared contracts" .-> Host
    Contracts -. "defines shared contracts" .-> Dashboard
    Contracts -. "defines shared contracts" .-> Goals
```

## Repository Boundaries

```mermaid
flowchart LR
    Contracts["mosaic-contracts"]
    Host["mosaic-android-host<br/>Host + Profile"]
    RN["mosaic-react-native-dashboard"]
    Flutter["mosaic-flutter-goals"]

    Contracts -. "shared specifications" .-> Host
    Contracts -. "shared specifications" .-> RN
    Contracts -. "shared specifications" .-> Flutter
```

## Communication Model

The Host mediates cross-module integration. Modules use explicit contracts rather than calling one another's internal APIs directly.

The architectural communication capabilities include navigation requests handled by the Host, shared context distributed by the Host, events delivered through Host-managed infrastructure, standardized error envelopes, and compatibility checks before module initialization.

These diagrams describe intended architectural boundaries. They do not imply that every runtime adapter or communication flow has already been implemented.

## Related Documentation

- [Architecture Overview](overview.md)
- [Mosaic Contracts](https://github.com/YOUR_USERNAME/mosaic-contracts)
