## Icons and SF Symbols

- Prefer SF Symbols over custom images wherever a suitable symbol exists.
- Use `Image(systemName:)` to render SF Symbols.
- Match symbol weight to surrounding text weight using `.symbolWeight()` rather than `fontWeight()`.
- Use `.symbolRenderingMode()` to control rendering: `.monochrome`, `.hierarchical`, `.palette`, or `.multicolor` depending on the context.
- Use the `variableValue:` parameter for variable symbols that represent a continuous value (e.g. Wi-Fi signal strength, volume).
- Standalone symbols used without a visible text label must have an `.accessibilityLabel()`. If the symbol is truly decorative and adds no meaning, use `Image(systemName:).accessibilityHidden(true)` instead.
- Scale symbols alongside text using `.imageScale()` (`.small`, `.medium`, `.large`) rather than applying a fixed frame size.
- When using a symbol in a `Button`, always include a text label: `Button("Add", systemImage: "plus", action: myAction)`.
