# Blazor — Create Primitive CSS Classes Using Public CSS Variables

This example creates simple layouts using primitive building blocks. The application includes two pages that display an employee card using two CSS approaches.

Both pages display the same DevExpress Blazor components to help you focus on the CSS approach rather than component behavior.

## Custom CSS Classes

The home page ([Index.razor](/CS/Components/Pages/Index.razor)) uses custom CSS primitive classes defined in the [wwwroot/css/primitives.css](/CS/wwwroot/css/primitives.css) stylesheet. These classes rely on DevExpress Blazor [public CSS variables](https://docs.devexpress.com/Blazor/405705/styling-and-themes/fluent-theme-customization/fluent-css-variables) to specify spacing, color, border, opacity, shadow, and typography styles.

To add the stylesheet to a theme, call the [AddFilePaths](https://docs.devexpress.com/Blazor/DevExpress.Blazor.ThemeProperties.AddFilePaths(System.String--)) method during theme registration (refer to the [App.razor](/CS/Components/App.razor) file).

The DevExpress Design System-based approach allows you to define any style you need, change variable values at runtime, and keep the UI consistent across the entire application; however, it requires writing custom CSS.

## Bootstrap Classes

The [BootstrapClasses.razor](/CS/Components/Pages/BootstrapClasses.razor) page creates a similar layout using Bootstrap classes shipped within DevExpress Blazor Fluent themes. These classes are integrated with our Design System and automatically adapt to size modes and other UI settings.

The [BootstrapClasses.razor.css](/CS/Components/Pages/BootstrapClasses.razor.css) stylesheet contains a CSS rule that limits the card size.

To render a Bootstrap-based layout in Fluent themes, enable the [UseBootstrapStyles](https://docs.devexpress.com/Blazor/DevExpress.Blazor.ThemeFluentProperties.UseBootstrapStyles) option in theme settings (refer to the [App.razor](/CS/Components/App.razor) file).

The Bootstrap approach allows you to build the UI using predefined classes without additional CSS, but its spacing, size, and color scales are fixed (you cannot use arbitrary or intermediate values). Dynamic styling scenarios may require additional classes or custom CSS/inline styles.

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
