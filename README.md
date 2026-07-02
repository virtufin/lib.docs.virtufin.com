# Virtufin .NET Library

[![Build Status](https://git.haenerconsulting.com/virtufin/virtufin-dotnet/actions/workflows/ci/badge.svg?branch=master)](https://git.haenerconsulting.com/virtufin/virtufin-dotnet/actions)
[![Docs](https://git.haenerconsulting.com/virtufin/lib-docs/commits/gh-pages/badge.svg)](https://lib.docs.virtufin.com/)

📖 Documentation: [lib.docs.virtufin.com](https://lib.docs.virtufin.com)

The foundational .NET 10 library for the Virtufin trading platform — provides the **Entity-Attribute-Value (EAV)** data model, the **`Variant`** discriminated union, **FlatBuffers** binary serialization, and **reactive observables** for NATS / WebSocket / Valkey data sources.

## Purpose

The lib is consumed by every other Virtufin service (`WorkManager`, `WebSocketManager`, `API Gateway`) and by external workers. It defines the cross-language wire format — a `Variant` produced in C# round-trips byte-identical in Python and TypeScript via the shared FlatBuffers schema.

### What's in the box

- **`Virtufin.Core`** — EAV abstractions (`IEntity<V, I>`, `IAttribute<V>`, `IValueProvider<V, I>`, `IRegistry`), financial contract traits, `DecimalAmount` arbitrary-precision decimal
- **`Virtufin.Base`** — concrete domain types (`Currency`, `Cash`, `Position`, `PositionSize`, `Transaction`, `Scenario`, ...), the **`IExecutor<TState, TAction, TEvent>`** template-method algebra, `RichTradeAction` / `TradeEvent` ADTs
- **`Virtufin.Data`** — the `Variant` discriminated union (sealed abstract record), FlatBuffers schema + codegen, `IObservable<T>` adapters for NATS / WebSocket / Valkey
- **`Virtufin.Util`** — utility helpers (time, formatting)

The dependency direction is strict: `Base → Core`, `Data → Base → Core`, `Util → Core + Base`. `Core` never imports `Base`.

## Quick start

```bash
# Build
dotnet build Virtufin.slnx

# Run all tests
dotnet test Virtufin.slnx

# Run a single test project
dotnet test tests/Virtufin.Core.Test/Virtufin.Core.Test.csproj
```

## Install (as a NuGet consumer)

```bash
dotnet nuget add source https://nuget.haenerconsulting.com/api/packages/virtufin/nuget/ \
    --name virtufin
dotnet add package Virtufin.Core
dotnet add package Virtufin.Base     # depends on Core
dotnet add package Virtufin.Data     # depends on Core + Base
```

## Conventions

- **C# 14 preview** features (e.g., `extension` syntax) are used where they reduce noise.
- **Nullable reference types** are enabled — respect the annotations.
- **Generic type parameters**: `V` for value types, `I` for identifier types, `A` for attribute types.
- **`I` prefix** for interfaces, PascalCase for classes, `_camelCase` for private fields, `UPPER_SNAKE_CASE` for constants.
- **`sealed`** on classes that aren't designed for inheritance (e.g., `Variant`).
- Line width 80 characters, Allman braces, 4-space indent, file-scoped namespaces.

## See also

- [lib.docs.virtufin.com](https://lib.docs.virtufin.com) — full reference
- [`virtufin-openspec/openspec/specs/core-data-types`](https://git.haenerconsulting.com/virtufin/virtufin-openspec) — the canonical spec for the lib
- [`virtufin-openspec/openspec/specs/sync-async-audit`](https://git.haenerconsulting.com/virtufin/virtufin-openspec) — sync/async correctness audit

## License

&copy; 2026 Häner Consulting. All Rights Reserved.
