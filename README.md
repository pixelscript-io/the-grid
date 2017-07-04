# The Grid

A 12x12 customizable grid built with CSS Grid and LESS.

![Grid System](http://i.imgur.com/4hh436c.png)

## Installation

Simply just clone this repo to get started! View [docs/index.html](https://joeberthelot88.github.io/the-grid/) for a variety of different possibilities.

## Usage

1. Initialize the grid:

```html
<div class="grid"></div>
```

2. Add your sections:

```html
<div class="grid">
  <div id="header"></div>
  <div id="article"></div>
  <div id="sidebar"></div>
  <div id="footer"></div>
</div>
```

3. Position your sections:

```html
<div class="grid">
  <div class="col-1-12 row-1-1"   id="header"></div>
  <div class="col-1-8  row-2-11"  id="article"></div>
  <div class="col-9-12 row-2-11"  id="sidebar"></div>
  <div class="col-1-12 row-12-12" id="footer"></div>
</div>
```

**Note:** The order of your sections *do not matter*!  This markup will appear exactly the same:

```html
<div class="grid">
  <div class="col-1-8  row-2-11"  id="article"></div>
  <div class="col-1-12 row-12-12" id="footer"></div>
  <div class="col-9-12 row-2-11"  id="sidebar"></div>
  <div class="col-1-12 row-1-1"   id="header"></div>
</div>
```

4. Configure your grid settings in `config.less`.  As of now the only configuration options are:

- Set column gap size.
- Set row gap size.
- Set grid width.


## The Classes

This is a 12x12 grid meaning there are 12 columns and 12 rows.  There are **over 150 generated classes**.  The classes are structured as follows:

```
(col or row)-(starting block)-(ending block)
```

Parameters:

```
[col]-[1-12]-[1-12]
[row]-[1-12]-[1-12]
```

Examples:

```
.col-1-12 (This section will start at column 1 and span all 12 columns)
.col-6-12 (This section will start at column 6 and span 6 additional columns)

.row-4-12 (This section will start at row 4 and span 8 additional rows)
.row-12-12 (This section will start at row 12 and only span 1 row)
```

**Note:** Sections cannot span backwards.  For example, the following is not possible:

```
.col-12-6
.row-2-1
```

**Note:** You do not need to specify both .col and .row classes on a section.  If two sequential sections span more than 12 blocks, the second section will automatically break onto the next row/column however specifying both is recommended.


## Helper Classes

#### Content Alignment

Aligning content is easy.  The following classes will align your content vertically and horizontally, as you wish:

1. .content-center-v (Vertically center content)
2. .content-center-h (Horizontally center content)
3. .content-end-v (Vertically align content to bottom)
4. .content-end-h (Horizontally align content to right)

Example markup:

```html
<div class="grid">
  <div class="col-1-12 row-1-1 content-center-h">This text is horizontally centered.</div>
</div>
```


#### Nested Grids

Nesting grids is also extremely easy.  Just add the `.grid` class to your section!

Example markup:

```html
<div class="grid">
  <div class="grid col-1-12 row-1-6">
    <div class="col-1-12 row-1-1"></div>
    <div class="col-1-12 row-2-12"></div>
  </div>
</div>
```


#### Responsiveness

*Coming soon...*


#### Other Helper Classes

1. .fill-height - Sets the min-height of the grid to 100vh.  This is an extremely easy way to get a sticky footer.

Example markup:

```html
<div class="grid fill-height">
  <div class="col-1-12 row-1-1"   id="header">This header is at the top of the viewport.</div>
  <div class="col-1-8  row-2-11"  id="article">I span the remaining height of the leftover space.</div>
  <div class="col-9-12 row-2-11"  id="sidebar">I span the remaining height of the leftover space.</div>
  <div class="col-1-12 row-12-12" id="footer">This footer as at the bottom of the viewport.</div>
</div>
```

2. .fixed-width - Sets a fixed width to the grid.
3. .center-grid - Centers the grid on the page.  This must be used with `.fixed-width`.

Example markup:

```html
<div class="grid fixed-width center-grid">
  <div class="col-1-12 row-1-1"   id="header">This header is at the top of the viewport.</div>
  <div class="col-1-8  row-2-11"  id="article">I span the remaining height of the leftover space.</div>
  <div class="col-9-12 row-2-11"  id="sidebar">I span the remaining height of the leftover space.</div>
  <div class="col-1-12 row-12-12" id="footer">This footer as at the bottom of the viewport.</div>
</div>
```


## Contributing

1. Fork it!
2. Create your new branch: `git checkout -b my-new-branch`
3. Commit your changes: `git commit -am 'Add some stuff'`
4. Push to the branch: `git push origin my-new-branch`
5. Submit a pull request :D

## Credits

Grid system built by Joe Berthelot.
