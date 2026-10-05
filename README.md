# contract-connection-fsm

A Lean 4 model of the client and server connection lifecycle, property-tested with Plausible.

## What it is for

It pins one bug: a client the server drops for silence keeps its stale identity, believes it is still connected, and never re-announces. The model shows that a client which re-joins once it stops hearing the server never disagrees with the server once settled and always recovers within the transaction time limit, and that the protocol without the re-join does not recover.

## Build and run

    lake build
    lake exe fsm_demo

## Licence

MIT; see `LICENSE`.
