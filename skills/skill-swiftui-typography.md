## Typography

- Always use Dynamic Type text styles (`.font(.body)`, `.font(.headline)`, `.font(.caption)`, etc.). Never hardcode font sizes.
- If a custom size is required, use `@ScaledMetric` so it scales with the user's type size preference.
- Use `.bold()` to make text bold. Never use `.fontWeight(.bold)` unless you need a specific weight other than bold.
- Do not apply `.fontWeight()` without a clear reason. Let the text style carry the appropriate weight.
- Use `.fontDesign()` (`.rounded`, `.serif`, `.monospaced`) to vary the font design within the system font family rather than loading a custom font unnecessarily.
- Avoid truncating text in a way that hides critical information. Use `.lineLimit()` only where layout demands it, and always allow the minimum number of lines needed to read the content.
- When displaying numbers or measurements, use formatted text (`Text(value, format:)`) rather than building strings manually with `String(format:)`.
