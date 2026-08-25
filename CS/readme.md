# Blazor — Create Primitive CSS Classes Using Public CSS Variables

This example demonstrates two different ways to build a simple layout using primitive blocks. The application includes two pages that render an employee card:

- The home page ([Index.razor](/CS/Components/Pages/Index.razor)) uses custom classes with the `dx` prefix (for example, `dx-card`, `dx-row`, or `dx-badge`). These classes rely on DevExpress Blazor [public CSS variables](https://docs.devexpress.com/Blazor/405705/styling-and-themes/fluent-theme-customization/fluent-css-variables) to specify spacing, color, border, opacity, shadow, and typography styles.
- The Bootstrap page ([BootstrapClasses.razor](/CS/Components/Pages/BootstrapClasses.razor)) references Bootstrap utility classes.

Both pages use the same DevExpress Blazor components, which helps you focus on the CSS approach rather than component behavior.

## Custom CSS Classes

The [primitives.css](/CS/wwwroot/css/primitives.css) stylesheet in the `wwwroot` folder defines custom CSS primitive classes using [Design System CSS variables](https://docs.devexpress.com/DesignSystem/405636/foundation) (for example, `--dxds-spacing-40`). The example assigns these classes to layout elements in the [Index.razor](/CS/Components/Pages/Index.razor) file to replicate a simple employee card.

To add the stylesheet to a theme, call the [AddFilePaths](https://docs.devexpress.com/Blazor/DevExpress.Blazor.ThemeProperties.AddFilePaths(System.String--)) method during theme registration (see the [App.razor](/CS/Components/App.razor) file).

DevExpress Design system-based approach allows you to define any style you need, change variable values at runtime, and keep the UI consistent across the entire application. However, it requires custom CSS.

## Bootstrap Classes

The [BootstrapClasses.razor](/CS/Components/Pages/BootstrapClasses.razor) page creates similar layout using Bootstrap classes (for example, `card-header` or `flex-column`). The [BootstrapClasses.razor.css](/CS/Components/Pages/BootstrapClasses.razor.css) stylesheet contains the CSS rule that limits the card size.

To render a Bootstrap-based layout in Fluent themes, enable the [UseBootstrapStyles](https://docs.devexpress.com/Blazor/DevExpress.Blazor.ThemeFluentProperties.UseBootstrapStyles) option in theme settings (see the [App.razor](/CS/Components/App.razor) file).

Bootstrap approach allows you to build the UI using predefined classes without additional CSS. However, its fixed scale of spacing, size, and color styles is fixed: you cannot use arbitrary or intermediate values. Dynamic styling scenarios may require additional classes or custom CSS/inline styles. This approach has a lower barrier to entry and requires less code upfront, but offers less flexibility for advanced customization.

## Files to Review

- [Components/Pages/Index.razor](Components/Pages/Index.razor)
- [Components/Pages/BootstrapClasses.razor](Components/Pages/BootstrapClasses.razor)
- [Components/Pages/BootstrapClasses.razor.css](Components/Pages/BootstrapClasses.razor.css)
- [Components/App.razor](Components/App.razor)
- [wwwroot/css/primitives.css](wwwroot/css/primitives.css)
- [wwwroot/css/theme-fluent.css](wwwroot/css/theme-fluent.css)

## Documentation

- [DevExpress Blazor Themes](https://docs.devexpress.com/Blazor/401523/common-concepts/themes)
- [CSS Variables in Fluent Themes](https://docs.devexpress.com/Blazor/405705/styling-and-themes/fluent-theme-customization/fluent-css-variables)
- [DxResourceManager](https://docs.devexpress.com/Blazor/DevExpress.Blazor.DxResourceManager)
