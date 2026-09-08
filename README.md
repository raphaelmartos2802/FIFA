# FIFA RED Component Framework

Framework for recreating interactive Easylearn learning objects inside FIFA RED.

## Architecture

The framework uses three layers:

1. **HTML** for structure and content.
2. **`<style>`** for presentation and component states.
3. **Inline JavaScript event handlers** such as `onclick`, `ondragstart`, `ondragover`, `ondragleave` and `ondrop` for interaction.

### FIFA RED compatibility rules

- Prefer CSS in a `<style>` block and CSS classes.
- Avoid `style="..."` attributes for component presentation.
- Do not rely on `<script>...</script>` blocks.
- Use standard HTML5 drag-and-drop events for drag-and-drop components.
- Use `id` for stable element references.
- Use `data-*` attributes for component data and configuration.
- Keep components self-contained and free of external JavaScript dependencies unless explicitly required and tested.

## Components

### FIFA-ASSOCIATION v1.0

Generic drag-and-drop association component. The component supports:

- configurable association zones;
- configurable draggable answers;
- replacement of an answer already placed in a zone;
- generic validation based on `data-answer`;
- correct/incorrect visual states;
- reset;
- optional image/content blocks;
- responsive layout.

See [`components/fifa-association/v1.0.html`](components/fifa-association/v1.0.html).

## Naming convention

- Component classes and IDs: `fifa-...`
- Configuration/data: `data-*`
- CSS: `<style>` block at the beginning of the component
- JavaScript: inline event handlers

## Status

**FIFA-ASSOCIATION v1.0 — validated in FIFA RED.**
