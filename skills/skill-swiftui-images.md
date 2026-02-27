## Images

- Purely decorative images that add no information should use `Image(decorative:)` or be hidden from VoiceOver with `.accessibilityHidden(true)`.
- Informative images must have a descriptive `.accessibilityLabel()`.
- Always apply `.resizable()` before scaling modifiers. Use `.scaledToFit()` to preserve aspect ratio within a frame, and `.scaledToFill()` when filling a space (combined with `.clipped()` to prevent overflow).
- Avoid fixed pixel sizes for images. Use `.frame()` constraints and let the image scale to fit.
- Prefer vector assets (PDF or SVG) over raster images in the asset catalog to ensure sharp rendering at all sizes and resolutions.
- When rendering a SwiftUI view to an image, always use `ImageRenderer` instead of `UIGraphicsImageRenderer`.
- Use `AsyncImage` for remote images. Always provide a placeholder and handle the failure state explicitly.
