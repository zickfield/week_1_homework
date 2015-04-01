# Week 1 Homework

The goal of this homework is to get comfortable with editing code using Sublime Text 3, and to get our feet wet with HTML.

We'll be recreating our course syllabus starting from plain old content. The first step will be to add semantic structure with HTML. Later, we'll add styling with CSS.

## Setup

 - **Fork** this repository to your own account (button in the top right).
 - **Clone** your fork in Desktop (button in the bottom right).
 - In the folder you just downloaded, there is a file called `syllabus.html`. Open it up in both Sublime and in Chrome.
 - Right now, in Chrome, your version should look like a big wall of text with no formatting. Your goal is to edit the source code until it looks something like this: http://boothappdev-s15.github.io/week_1_homework/
 - As you work, don't forget to Sync often in your GitHub Desktop App. Usually I commit and sync every time I complete a useful chunk of work, or before I start doing something experimental that I might want to throw away.

## Add Basic Tags

Right now, `syllabus.html` contains only raw content, without any HTML structure at all. Your first job will be to go through and add some.

**The Wrap Selection With Tag (Ctrl-Shift-W on Mac, Alt-Shift-W on Windows) keyboard shortcut is your friend.** Highlight the content you want to put opening and closing tags around, then use the shortcut, then type the tag name that you want and it will modify both the opening and closing tags.

All of the content up until the schedule is pretty straightforward; some tags you might find suitable to describe the content are

 - a
 - blockquote
 - dl, dt, dd
 - h1
 - h2
 - ol, li
 - p
 - section

Here is a good reference to learn about what these, and all other, tags are meant for:

https://developer.mozilla.org/en-US/docs/Web/HTML/Element

It's pretty remarkable to me that the entire web is built with such a relatively small number of elements. And of that small number, we use even fewer on a daily basis.

Anyway, I usually find it best to head straight for the examples when dealing with programming language documentation:

https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dl#Examples

## The Schedule

Now, the tricky part: the schedule. First, let's talk about HTML tables.

### HTML Tables

An important element in HTML is `<table>`. We're going to use our schedule to get some practice with it.

`<table>`s in HTML are used to represent two dimensional data. A simple table looks like this:

    <table>
      <tr>
        <th>First</th>
        <th>Last</th>
      </tr>
      <tr>
        <td>John</td>
        <td>Doe</td>
      </tr>
      <tr>
        <td>Jane</td>
        <td>Doe</td>
      </tr>
    </table>

which would produce this:

<table>
  <tr>
    <th>First</th>
    <th>Last</th>
  </tr>
  <tr>
    <td>John</td>
    <td>Doe</td>
  </tr>
  <tr>
    <td>Jane</td>
    <td>Doe</td>
  </tr>
</table>

The things to keep in mind about tables are:

 - Every piece of data must reside within a cell, a `<td>` element (or maybe a `<th>` element if it's a heading).
 - Every `<td>` or `<th>` element must reside within a row, a `<tr>` element.
 - Every `<tr>` must have the same number of cells, or things get out of whack.

Despite this last rule, you can, however, "merge" cells using the `colspan` and `rowspan` attributes:

    <table>
      <tr>
        <th colspan="2">People</th>
      </tr>
      <tr>
        <td>John</td>
        <td>Doe</td>
      </tr>
      <tr>
        <td>Jane</td>
        <td>Doe</td>
      </tr>
    </table>

produces:

<table>
  <tr>
    <th colspan="2">People</th>
  </tr>
  <tr>
    <td>John</td>
    <td>Doe</td>
  </tr>
  <tr>
    <td>Jane</td>
    <td>Doe</td>
  </tr>
</table>

You can see that we've merged two cells in the first row together; the `colspan="2"` on the first cell ensures that we don't violate the "every `<tr>` must have the same number of cells" rule.

Similarly, you can merge cells vertically:

    <table>
      <tr>
        <th rowspan="2">People</th>
        <td>John</td>
        <td>Doe</td>
      </tr>
      <tr>
        <td>Jane</td>
        <td>Doe</td>
      </tr>
    </table>

produces:

<table>
  <tr>
    <th rowspan="2">People</th>
    <td>John</td>
    <td>Doe</td>
  </tr>
  <tr>
    <td>Jane</td>
    <td>Doe</td>
  </tr>
</table>

Now, each row has three cells. The second row doesn't look like it at first glance, but the first cell in the first row is spanning down across two rows, so the second row really does have three cells.

### The Schedule: Phase 1

You should now have all the information you need to tackle the schedule, but here are a few suggestions on how to go about it.

I would do it in two phases. First, let's build a simple one-column table and get that working (and not worry about the week headings being over on the left for now).

Add your `<table>` and `</table>` tags above and below all of the content, first of all. Next, we need to put each line of text within a `<td>` and within a `<tr>`. That would produce a single-column table for us to start with.

Multiple cursors will come in handy for this: https://www.sublimetext.com/docs/3/column_selection.html

On Mac, hold Option while left-click dragging; Windows, hold Shift while right-click dragging. [Here's a short video I recorded to demonstrate](http://htmlpreview.github.io/?https://github.com/boothappdev-s15/week_1_homework/blob/master/vertical_selection.html).

### The Schedule: Phase 2

Now that you have a decent looking single-column table, let's get it to look exactly how we wanted it: the week headings should span down across topics on the left.

In other words, we want a two column table, with the week headings occupying the left column, and spanning however many cells they need to.

## Good luck!



