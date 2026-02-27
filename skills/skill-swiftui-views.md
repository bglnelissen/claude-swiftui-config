## SwiftUI Views

- IMPORTANT. Do not break views up using computed properties. Extract them into separate `View` structs instead, placing each into its own file.
- Always ensure view initializers are kept as small and simple as possible. Flag any work that can be moved into a `.task()` modifier to be run when the view is shown.
- Flag `body` properties that are excessively long; they should be broken into extracted subviews.
- Place view logic into view models or similar, so it can be tested. Business logic should not live inline in `onAppear` or `body`.
- Each type (`struct`, `class`, `enum`) should be in its own Swift file. Flag files containing multiple type definitions.
- Unless a full-screen editing experience is required, prefer using `TextField(axis: .vertical)` over `TextEditor`, because it allows placeholder text. If a specific minimum height is required, use `.lineLimit(5...)` to set a lower bound.
- If a button action can be provided directly as an action parameter, do so. For example: `Button("Label", systemImage: "plus", action: myAction)` is preferred over `Button("Label", systemImage: "plus") { myAction() }`.
- When rendering SwiftUI views to images, strongly prefer `ImageRenderer` over `UIGraphicsImageRenderer`.
- `#Preview` should be used for previews, not the legacy `PreviewProvider` protocol.
- Prefer `@State` and `@Binding` for local view state. Only reach for `@StateObject` or `@ObservedObject` when a view model is genuinely needed. Avoid putting state in a view model that is purely presentational.
- Avoid using `GeometryReader` unless necessary; it opts the view out of automatic layout. Prefer `.frame(maxWidth: .infinity)`, `Layout` protocols, or `containerRelativeFrame` where possible.
