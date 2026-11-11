# Accessibility and UI Policies of This Application

This application's primary UI design philosophy is to respect **Microsoft’s native, organized UI guidelines**. 
To ensure a consistent user experience and maintainability, customizations to the default UI should be kept to a minimum.

## 1. UI Development Policy

### Controls and Themes
* **Use Default Themes:** Always rely on WinUI's built-in default themes and styling rather than applying heavy custom styles.
* **Community Toolkits:** If specialized controls are required for specific features, prioritize using official packages such as the **Community Toolkit for WinUI** over building bespoke custom controls from scratch.

### Internationalization (i18n)
* **Resource Separation:** To enable the community to easily contribute translations, all user-facing text displayed in the UI must be referenced from external resource files (`.resw`) suited for each locale. Hardcoding strings in XAML or code-behind is strictly prohibited.

## 2. Accessibility Standards (WinUI & UIA)

To ensure that the application is fully usable for all users, including those relying on assistive technologies, contributions must adhere to the following accessibility standards:

* **Screen Reader Support (UIA):** All interactive elements must provide clear and descriptive accessibility names and help texts using `AutomationProperties.Name` and `AutomationProperties.HelpText` where default semantics are insufficient.
* **Keyboard Navigation:** The application must be fully operable using only a keyboard. Ensure logical tab orders (`TabIndex`), visible focus visuals, and proper handling of shortcut keys.
* **Visual Accessibility & High Contrast:** UI elements must correctly adapt to Windows High Contrast themes and maintain sufficient color contrast ratios between text and background elements.

## 3. Code Transparency & Open-Source Guidelines

As an open-source project, transparency in implementation is vital for community audits and contributions:

* **Open Implementation of Accessibility:** Accessibility logic, such as custom `AutomationPeer` implementations or keyboard handling handlers, must be clearly written, well-documented, and easy for contributors to inspect and test.
* **Avoid Obfuscated Workarounds:** Avoid complex or undocumented reflection-based UI hacks. If a non-standard workaround is necessary due to WinUI framework limitations, it must be thoroughly documented in the code comments with a clear rationale.
* **Contribution Transparency:** All UI components and state logic should be structured cleanly to allow contributors to easily verify how UI states map to underlying data models.