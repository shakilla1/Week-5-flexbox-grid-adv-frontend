# Reflection: Flexbox vs. CSS Grid (Level 4)

For Level 4 we built the same Holy Grail layout twice, once with Flexbox and once with CSS Grid, and the two approaches felt different from the start.

## Which was easier to implement?

Flexbox was quicker to get something on screen. A flex column for the page, a flex row for the sidebars and main content, and `margin-left: auto` to push the user menu right all came together fast. Grid took a bit more planning, because we had to decide on rows and columns first. After that it was easier to maintain. Collapsing a sidebar meant changing one column width, while in Flexbox we also had to manage `flex-basis` and `overflow`.

## Which required less code?

Neither was dramatically shorter. Grid needed less code for the card reflow, where `repeat(auto-fill, minmax(250px, 1fr))` replaced several flex properties. Flexbox needed more workarounds, such as `order` to move the main content above the sidebars on tablet and mobile. In Grid we just rearranged `grid-template-areas`.

## Which was more intuitive?

Flexbox felt more natural for one-dimensional things like the navigation bar and the header, where items sit in a single line. Grid felt more natural for the page as a whole, because we could see the layout in the code. The footer showed this best: with subgrid, the headings and link lists line up across all three columns without any extra effort.

## What differences did we notice?

The two versions don't look quite identical. When the last row of cards is short, Flexbox stretches the cards to fill the row, while Grid keeps them all the same width. Getting Flexbox to match would need extra work, and this was the clearest example for us of the two systems thinking differently. Flexbox sizes items based on their content, and Grid sizes them based on the grid.

## When would we use each one?

We would use Flexbox for components: navigation menus, toolbars, buttons, and anything that sits in a row or column. We would use Grid for page structure and for anything that needs rows and columns to line up, like card galleries and footers. In practice they work best together. Our Grid page still uses flexible alignment inside the smaller components, and the best layouts probably mix both.

Overall, Level 4 taught us that this isn't really a choice between one or the other. Flexbox is better at distributing items along one direction, and Grid is better at defining the whole structure. Knowing which question we're asking (content first or layout first) tells us which tool to use.
