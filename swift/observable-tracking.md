# `@Observable` only tracks what you read

With the Observation framework, a SwiftUI view only re-renders when a property
it actually *read* during `body` changes. Properties you never touch in `body`
can change freely without invalidating the view, which is a big difference from
`ObservableObject`, where any `@Published` change fires `objectWillChange`.
