# Tailwind CSS - Separation of Concerns
- Last Updated: 2025-08-30
- Tags: tailwind css
- Version: 1.0


The fundamental principle is the strict separation of a component's layout responsibilities from its styling responsibilities.

- **Layout Components**: Arrange other components on the page using `flex`, `grid`, and `gap`. They handle all responsive logic. They are ignorant of the visual styling of the components they are arranging.

- **UI Components**: Define their own appearance (colors, fonts, borders, etc.). They are ignorant of their position on the page and must remain marginless.
