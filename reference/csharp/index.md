---
uid: Virtufin.Dotnet.Reference
title: C# API Reference
---

# C# API Reference

Auto-generated API documentation for the Virtufin .NET lib.

## Projects

### Virtufin.Core

- [Virtufin.Core](../api/Virtufin.Core.html) — EAV abstractions, `DecimalAmount`
- [Virtufin.Core.Execution](../api/Virtufin.Core.Execution.html) — `IExecutor<TState, TAction, TEvent>`, `IExecutionState`
- [Virtufin.Core.Events.Trade](../api/Virtufin.Core.Events.Trade.html) — `ITradeAction`, `ITradeEvent<A>`
- [Virtufin.Core.Position](../api/Virtufin.Core.Position.html) — `DecimalAmount`, `IQuantity<A, U>`
- [Virtufin.Core.Contracts](../api/Virtufin.Core.Contracts.html) — `ITransaction`, `IContract`
- [Virtufin.Core.Identifiers](../api/Virtufin.Core.Identifiers.html) — identifier traits
- [Virtufin.Core.Predicates](../api/Virtufin.Core.Predicates.html) — contract predicate types

### Virtufin.Base

- [Virtufin.Base](../api/Virtufin.Base.html) — `Currency`, `Cash`, `Position`, `StochasticState`
- [Virtufin.Base.Execution](../api/Virtufin.Base.Execution.html) — `DeterministicExecutorBase<TState, TAction, TEvent>`, `SlippageExecutorBase<TState, TAction, TEvent>`, `LiveExecutorBase<TState, TAction, TEvent>`, `ObserveOnlyExecutor<TState, TAction, TEvent>`
- [Virtufin.Base.Events.Trade](../api/Virtufin.Base.Events.Trade.html) — `RichTradeAction`, `TradeAction`, `TradeEvent`
- [Virtufin.Base.Events.Position](../api/Virtufin.Base.Events.Position.html) — `PositionEvent`
- [Virtufin.Base.Events.Risk](../api/Virtufin.Base.Events.Risk.html) — `RiskEvent`, `RichRiskEvent`
- [Virtufin.Base.Events.Market](../api/Virtufin.Base.Events.Market.html) — market data events

### Virtufin.Data

- [Virtufin.Data](../api/Virtufin.Data.html) — `Variant` discriminated union, serialization
- [Virtufin.Data.FlatBuffers](../api/Virtufin.Data.FlatBuffers.html) — FlatBuffers schema types
- [Virtufin.Data.NatsObservable<T>](../api/Virtufin.Data.NatsObservable.html) — NATS reactive adapter
- [Virtufin.Data.WebSocketObservable<T>](../api/Virtufin.Data.WebSocketObservable.html) — WebSocket reactive adapter

### Virtufin.Util

- [Virtufin.Util](../api/Virtufin.Util.html) — Utility helpers

> **Tip**: Use the search bar (top right) to find any type by name. Each namespace page lists types in that namespace only. Sub-namespaces (e.g. `Virtufin.Core.Execution`) have their own pages — use the links above to reach them.

## See also

  - [Concept docs](../../v1/) — hand-written guides (architecture, EAV, Variant, etc.)
