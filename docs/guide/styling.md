# Styling Documentation

Alugard-Drop provides a native-like drag and drop experience by cloning the element you are dragging and hiding the original. You can easily customize the appearance of these elements using plain CSS.

## The Mirror Element (`.ad-mirror`)

When an item is dragged, `alugard-drop` creates a clone of the original element, appends it to the `mirrorContainer` (which defaults to `document.body`), and adds the `ad-mirror` CSS class to it.

You can use this class to style the element that follows the user's cursor:

```css
/* Change the styling of the element actively being dragged */
.ad-mirror {
  opacity: 0.8;
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
  cursor: grabbing !important;
  /* Add any other custom styles you want */
}
```

## The Transit Element (`.ad-transit`)

The original element remains in the DOM list but is visually modified to show where the item will be dropped. Alugard-Drop adds the `ad-transit` CSS class to this original element.

You can use this class to style the "ghost" placeholder element:

```css
/* Change the styling of the original element left in the list */
.ad-transit {
  opacity: 0.2;
  border: 2px dashed #ccc;
}
```

## Disabling Pointer Events

By default, the `.ad-mirror` class includes `pointer-events: none`. This is required so that mouse events can pass through the mirror element and hit the drop zones underneath. 

```css
/* Included in alugard-drop/style.css */
.ad-mirror {
  pointer-events: none;
}
```

Unless you are building a custom drag implementation that requires pointer events on the mirror, you should avoid overriding this property.
