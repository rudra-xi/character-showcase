**HTML Structure:**

-    **DOCTYPE declaration**: Defines the document type as HTML.
-    `<html>` tag: The root element of the HTML document.
     -    `<head>` section: Contains meta information about the webpage.
          -    `<meta charset="UTF-8" />`: Defines the character encoding.
          -    `<meta name="viewport" content="width=device-width, initial-scale=1.0" />`: Sets the viewport for mobile devices.
          -    `<title>Character Showcase</title>`: Sets the title of the webpage to "Character Showcase".
          -    `<link rel="stylesheet" href="style.css" />`: Links an external stylesheet named "style.css" for styling the webpage (not shown here).
     -    `<body>` section: Contains the visible content of the webpage.
          -    `<div class="container">`: Creates a container element with the class "container" that likely holds all the character boxes.
               -    Multiple instances of `<div class="box box-N" style="--img: url(image.jpeg)" data-text="character_name">`: Creates individual character boxes with the following details:
                    -    Class: "box" with a unique identifier (box-1, box-2, etc.) for potential individual styling.
                    -    Inline style using CSS variables:
                         -    `--img: url(image.jpeg)`: Sets the background image for the box using a URL from the "images" folder.
                    -    `data-text` attribute: Stores the character name associated with the box (not displayed directly on the page).

```

```

**CSS Styling:**

**Import & Global Styles:**

-    Imports the Oswald font family from Google Fonts with various weights (200 to 700).

-    Sets general styles for all elements:
     -    No padding or margin.
     -    Uses "box-sizing: border-box" for consistent box model.
     -    Font family set to "Oswald", fallback to sans-serif.

**Body Styles:**

-    Uses a grid layout for the body.
-    Positions content in the center using "place-content: center".
-    Sets minimum height to 100vh (viewport height).
-    Background is a linear gradient with two dark grey tones at a 450-degree angle.

**Container Styles:**

-    Uses relative positioning for layering elements within the container.
-    Uses a grid layout with five columns of equal width (1fr each).
-    Gap between columns is 1em.
-    Container width is 900px and height is 500px.
-    Smooth transitions for all styles with a duration of 400ms.
-    Applies a grayscale filter and reduces opacity on hover for all boxes within the container.

**Box Styles:**

-    Uses relative positioning for layering content within the box.
-    Background image is set using a variable `var(--img)`. The image is centered and sized to cover the box.
-    Smooth transitions for all styles with a duration of 400ms.
-    Uses flexbox for layout, with items centered horizontally and vertically.
-    Removes grayscale filter and increases opacity to 100% on hover.

**Box Hover Effects based on Class:**

-    When hovering over a specific box with class `box-1` to `box-5`, the grid layout dynamically changes the column widths to visually enlarge the hovered box while maintaining a 5-column structure.

**Box Animation for Odd and Even Elements:**

-    Applies a slight vertical transform on hover:
     -    Odd numbered boxes move up 20px.
     -    Even numbered boxes move down 10px.

**Box Text Overlay:**

-    Uses the pseudo-element `::after` to create text overlays within each box.
-    Content for the overlay is fetched from the `data-text` attribute of the box element.
-    Styles the text overlay:
     -    Absolute positioning at the bottom with 20px padding.
     -    Black background with white text.
     -    Text formatting (uppercase, letter spacing).
     -    Initially hidden with transform and opacity set to 0.
     -    Fades in and moves up on hover with a slight delay.
