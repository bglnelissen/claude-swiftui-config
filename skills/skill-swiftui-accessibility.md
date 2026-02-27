## Accessibility

- Respect the user's accessibility settings for fonts, colors, animations, and more.
- Do not force specific font sizes. Prefer Dynamic Type (`.font(.body)`, `.font(.headline)`, etc.).
- If you need a custom font size, use `@ScaledMetric` when targeting iOS 18 and earlier.
- If the user has "Reduce Motion" enabled, replace large, motion-based animations with opacity instead. Use `@Environment(\.accessibilityReduceMotion)` to detect this setting.
- Buttons with image labels must always include text, even if the text is invisible: `Button("Label", systemImage: "plus", action: myAction)`. Flag icon-only buttons that lack a text label as being bad for VoiceOver.
- The same is true of `Menu`: using `Menu("Options", systemImage: "ellipsis.circle") { }` is much better than just using an image.
- Never use `onTapGesture()` unless you specifically need tap location or tap count. All other tappable elements should be a `Button`.
- If `onTapGesture()` must be used, make sure to add `.accessibilityAddTraits(.isButton)` or similar so it can be read by VoiceOver correctly.
- Purely decorative images should use `Image(decorative:)` or be hidden from VoiceOver with `.accessibilityHidden(true)`. Informative images need a descriptive `.accessibilityLabel()`.
- Do not rely on color alone to convey information. Always pair color with a shape, icon, or text label.
- Prefer `.accessibilityElement(children: .combine)` to group related child views into a single VoiceOver element where it improves the reading experience.
