Back to [[CSS]]
### What is it?
A more interesting and powerful layout technology compared to Flexbox.

[Complete GRID Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
[Responsive GRID with no @media](https://css-tricks.com/look-ma-no-media-queries-responsive-layouts-using-css-grid/)

### Useful Grid Properties (CONTAINERS):
| PROPERTY                 | DESCRIPTION                                                                             | VALUES                                                                         |
| ------------------------ | --------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| `display`               | Initialize the grid.                                                                    | `grid` `inline-grid`                                                           |
| `grid-template-columns` | Define amount of columns and their size.                                                |                                                                                |
| `grid-template-rows`    | Define amount of rows and their size.                                                   |                                                                                |
| `grid-template-areas`   | Define the grid layout by the `grid-area:` of the children.                             |                                                                                |
| **=>** `grid-template`:  | **SHORTHAND**: `grid-template-areas` `grid-template-rows` / `grid-template-columns`     |                                                                                |
| `gap`                   | Gap between columns and rows.                                                           |                                                                                |
| `justify-items`          | Aligns items horizontally.                                                              | `start` `end` `center` `stretch`                                               |
| `align-items`            | Align items vertically.                                                                 | `stretch` `start` `end` `center` `baseline`                                    |
| **=>** `place-items`     | **SHORTHAND**: `align-items` / `justify-items`                                          |                                                                                |
| `justify-content`        | When grid is smaller than its container. Horizontal justify.                            | `start` `center` `end` `stretch` `space-around` `space-between` `space-evenly` |
| `align-content`          | When grid is smaller than its container. Vertical justify.                              | `start` `center` `end` `stretch` `space-around` `space-between` `space-evenly` |
| **=>** `place-content`   | **SHORTHAND**: `align-content` `justify-content`                                        |                                                                                |
| `grid-auto-columns`      | Sets the size of implicit grid-columns.                                                 |                                                                                |
| `grid-auto-rows`         | Sets the size of implicit grid-rows.                                                    |                                                                                |
| `grid-auto-flow`         | Sets the auto-placement algorithm for items that are not explicitly placed on the grid. | `row` Fill rows first.                                                         |
|                          |                                                                                         | `column` Fill columns first.                                                   |
|                          |                                                                                         | `dense` Try to fill holes in the grid if small items come up later.            |
|                          |                                                                                         |                                                                                |


### Useful Grid Properties (CHILDREN):
| PROPERTY            | DESCRIPTION                                                                                                                                                                  | VALUE |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----- |
| **=>**`grid-row`    | **SHORTHAND**: `grid-row-start` `grid-row-end`                                                                                                                               |       |
| **=>**`grid-column` | **SHORTHAND**: `grid-column-start` `grid-column-end`                                                                                                                         |       |
| `grid-area`         | Gives and item a name for reference by `grid-template-areas`. Can also be used as **SHORTHAND**: `grid-row-start` + `grid-column-start` + `grid-row-end` + `grid-column-end` |       |
| `justify-self`      | Aligns a grid item inside its grid cell horizontally.                                                                                                                        | `start` `end` `center` `stretch`      |
| `align-self`        | Aligns a grid item inside its grid cell vertically.                                                                                                                                                                             | `start` `end` `center` `stretch`      |
| **=>**`place-self`        | **SHORTHAND**: `align-self` `justify-self`                                                                                                                                                                             |       |
|                     |                                                                                                                                                                              |       |

### Special Stuff
| STUFF               | DESCRIPTION                                                                                                      | VALUE |
| ------------------- | ---------------------------------------------------------------------------------------------------------------- | ----- |
| `min-content`       | Sizing rows and columns. Sets size by the smallest portion of the content.                                       |       |
| `max-content`       | Sizing rows and columns. Sets size by the largest portion of the content.                                        |       |
| `repeat(4, 1fr)`    | Instead of typing `1fr 1fr 1fr 1fr` etc.                                                                         |       |
| `minmax(10px, 1fr)` | Item will be at minimum 10px and at max a fraction.                                                              |       |
| `auto-fill`         | Fit as many columns as possible on a row even if they are empty.                                                 |       |
| `auto-fit`          | Fit whatever columns there are into the space. Prefer expanding columns to fill space rather than empty columns. |       |
|                     |                                                                                                                  |       |
