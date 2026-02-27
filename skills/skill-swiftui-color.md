## Color

- Always use semantic system colors (`Color.primary`, `Color.secondary`, `Color.accentColor`) over hardcoded color values. They automatically adapt to dark mode and accessibility settings.
- Never use hardcoded UIKit colors such as `UIColor.systemBlue` in SwiftUI code. Use `Color.accentColor` or `.tint()` instead.
- Use `.tint()` to apply an accent color to a hierarchy of controls rather than setting colors on individual views.
- Never rely on color alone to convey information. Always pair color with a shape, label, or icon.
- When bridging from UIKit is unavoidable, use `Color(uiColor:)` rather than manually converting values.
- Support dark mode by using adaptive colors from the asset catalog or system semantic colors. Never assume a light background.
- Use `.foregroundStyle()` with a `ShapeStyle` (e.g. `.primary`, `.secondary`, `.tertiary`, gradients) for rich, adaptive styling. Never use `foregroundColor()`.
