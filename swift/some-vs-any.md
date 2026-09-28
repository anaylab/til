# `some` vs `any`

- `some View` is an *opaque* type: one concrete type, fixed at compile time, just
  hidden from the caller. No boxing, full static dispatch.
- `any Shape` is an *existential*: a box that can hold a different conforming type
  at runtime, at the cost of dynamic dispatch.

Rule of thumb: reach for `some` first, use `any` when you actually need a
heterogeneous collection like `[any Shape]`.
