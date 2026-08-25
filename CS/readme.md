# DevExpress Blazor Design System Primitives

## Purpose

This example shows how to compose a layout from primitive building blocks using an employee profile card with a task list as a sample scenario. The same composition is implemented in two different ways so you can compare CSS approaches.

## Two Pages

1. **Custom CSS classes** built on top of the DevExpress design system variables.
2. **Plain Bootstrap** classes only, without any custom styles (except for fixing the card's exact dimensions).

## Files

- **`CS\Components\Pages\Index.razor`** — the `/` page. The layout is composed from custom primitives (`dx-card`, `dx-row`, `dx-stack`, `dx-badge`, etc.).
- **`CS\wwwroot\css\primitives.css`** — a set of reusable CSS primitives (layout, avatar, badge, card, text styles) built on top of DevExpress design system tokens (`--dxds-*`: colors, spacing, radii, shadows).
- **`CS\Components\Pages\BootstrapClasses.razor`** — the `/bootstrap-classes` page. Same layout, but composed entirely from Bootstrap classes (`d-flex`, `card`, `badge`, `gap-*`, `p-3`, etc.).
- **`CS\Components\Pages\BootstrapClasses.razor.css`** — a minimal scoped CSS file used only to fix the card's width/height, since Bootstrap has no utility classes for arbitrary rem values.
- Both pages use the same DevExpress components (`DxButton`, `DxSplitButton`, `DxDropDownButton`, `DxTabs`, `DxProgressBar`), so the only difference between the pages is the CSS approach, not the component layer.

## Pros and Cons

**Custom CSS primitives based on design tokens**
- Values (spacing, colors, radii, shadows) come from design system variables, so they can be changed centrally, including implementing **dynamic/interactive customization** (for example, a slider that updates a spacing CSS variable is instantly reflected in every class that uses it).
- The value scale isn't limited to a fixed set — any arbitrary value can be defined.
- Requires writing and maintaining your own CSS code.
- Easier to keep values consistent across the UI, since they are tied to shared variables rather than scattered atomic classes.

**Bootstrap**
- A ready-made set of classes speeds up building a typical UI without writing CSS.
- Spacing, sizing, and color values are **static** — defined by the framework's fixed scale. This makes dynamic styling scenarios harder to support (for example, a user-facing density toggle or arbitrary spacing adjustment), since every new value requires either an additional class or falling back to custom CSS/inline styles anyway.
- The limited value scale may not cover every required level of precision (the step between classes is fixed, with no in-between values).
- Lower barrier to entry and less code upfront, but less flexible when customization needs go beyond the predefined options.
