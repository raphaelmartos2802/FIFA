# FIFA RED Component Framework — Architecture

## Core architecture

Each interactive component is divided into three layers:

1. **HTML** — structure, content, IDs and `data-*` configuration.
2. **`<style>`** — presentation and visual states.
3. **Inline JavaScript event handlers** — interaction and behavior.

## Compatibility rules

- CSS should be defined in a `<style>` block and applied through classes.
- Avoid inline `style="..."` attributes for component presentation.
- Do not rely on `<script>...</script>` blocks.
- Use HTML5 drag-and-drop events for drag-and-drop interactions.
- Use stable `id` values for DOM references.
- Use `data-*` attributes to store relationships and configuration.
- Avoid external JavaScript dependencies unless separately validated in FIFA RED.

## Naming conventions

Use the `fifa-` prefix for component-specific classes and IDs.

Examples:

```html
<div class="fifa-association">
<div id="fifa-association-zone-1">
```

Use `data-*` for relationships/configuration:

```html
<div data-answer="answer-1">
```

## State-driven styling

JavaScript should preferably change classes rather than CSS properties directly.

```javascript
zone.classList.add('correct');
```

```css
.fifa-association-drop-zone.correct {
    background:#edf9eb;
    border-color:#34b500;
}
```

This keeps behavior and presentation separate.

## Component lifecycle

For each new component:

1. Analyze the Easylearn object.
2. Identify structure, interactions, states, validation and feedback.
3. Map those concepts to a FIFA RED component.
4. Keep content/configuration separate from the generic interaction engine.
5. Test initial rendering.
6. Test FIFA RED post-processing.
7. Test all interaction states.
8. Test reset and responsive behavior.

## Validation status

### Validated in FIFA RED

- `<style>` persistence after post-processing.
- CSS classes used for presentation.
- Standard HTML elements.
- HTML5 drag-and-drop events used by `FIFA-ASSOCIATION v1.0`.
- DOM manipulation with `getElementById`, `querySelector`, `appendChild` and `classList` in the validated component.
- Dynamic feedback via inline event handlers.

### Not yet generally validated

- CSS custom properties/variables.
- Complex CSS animations.
- Persistent client-side storage.
- Touch-specific drag-and-drop behavior.
- External JavaScript libraries.
- Cross-component communication.

These should be tested before being treated as framework guarantees.
