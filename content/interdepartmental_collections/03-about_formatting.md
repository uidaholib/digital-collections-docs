---
section: Interdepartmental Collections
nav_order: 3
title: About Pages and Formatting
---

## About Pages

Collection About Pages are written in Markdown.
Below are notes on formatting your page.
For more basic information on how Markdown works and general formatting see the [Learn-Static Intro to Markdown](https://www.markdownguide.org/cheat-sheet/) and [Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/).

## Citations

You'll need to cite the sources for your multimedia essay just as you would for any academic essay.
Whenever possible, use [Turabian Style](https://www.chicagomanualofstyle.org/turabian/turabian-notes-and-bibliography-citation-quick-guide.html) to add your citations as footnotes.

To add a footnote in Markdown, directly after the sentence you'd like to cite, add a left square bracket (`[`), followed by a caret symbol (`^`), followed by a footnote number (i.e. `1`, `2`, `3`, etc.), followed by a left square bracket (`]`). See below for an example:

`Example text to be cited.[^1]`

`Yet more text to cite.[^2]`

Then, at the very bottom of the page, you'll create a section with the heading `Sources`, and add the bracketed footnote numbers (i.e. `[^1]`, `[^2]`, `[^3]`, etc.), followed by a colon (`:`) and citation, like this:

`[^1]: Katie Kitamura, *A Separation* (New York: Riverhead Books, 2017), 25.`

`[^2]: Sharon Sassler and Amanda Jayne Miller, *Cohabitation Nation: Gender, Class, and the Remaking of Relationships* (Oakland: University of California Press, 2017), 114.`

On the front end, your footnote number will automatically link down to its corresponding citation, which will reside at the "foot" of your essay.
To see this in action, look at the cited text below, and click on the blue `1` and `2` footnotes at the end of each line.

---

## Hyperlinks

You can create hyperlinks in Markdown like this:

`[GitHub Help](https://help.github.com/)`

When linking to pages within the same collection, use Jekyll's `relative_url` feature. 
Instead of writing out https://www.lib.uidaho.edu on an About page you should use the liquid relative_url formula:

**Don't** do this:

`[family](https://www.lib.uidaho.edu/digital/priestlake/browse.html#families)`

**Do** this:

`[family]({{ '/browse.html#families' | relative_url }})`

Here's another example:

**Don't** do this:

`[stage](https://www.lib.uidaho.edu/digital/priestlake/items/priestlake244.html)`

**Do** this:

`[stage]({{ '/items/priestlake244.html' | relative_url }})`

### Open a link in a new browser tab

You've probably noticed that hyperlinks created this way cause a new website to open in your browser's *current tab*.
Sometimes this is what you want to happen, but there will be other times where you'd like a link to open in a *new browser tab* when a user clicks on it.
To make this happen, you'll need to copy and paste the snippet of text below to the *end* of your hyperlink parentheses:

Copy this: `{:target="_blank" rel="noopener"}`

And paste it *after* the parentheses in your hyperlink: 

`[GitHub Help](https://help.github.com/){:target="_blank" rel="noopener"}`

This will ensure that your link opens in a new tab, like this: [GitHub Help](https://help.github.com/)

---

## Perma.cc

Use Perma.cc, a web archiving service, to capture archive copies of web pages that we cite in About pages. This is done to prevent ink rot--broken and incorrect links.

If using Perma.cc for the first time, please refer to this documentation to initially set up a Perma.cc account: [https://evanwill.github.io/web-cites/content/3-perma.html](https://evanwill.github.io/web-cites/content/3-perma.html).

Once logged in, navigate to UI Library DDS > Digital Collection About pages. Select the collection folder you are working on or create a new folder. Then, add your link.

Add the archived Perma.cc link to your citations like this: 

`Becky Kramer, "Pre-Dam Photos May Be Glimpse of Future," The Spokesman-Review, March 30, 2009, https://www.spokesman.com/stories/2009/mar/30/pre-dam-photos-may-be-glimpse-of-future/. (Archived: https://perma.cc/LN7F-Q2CW)`

---

## Horizontal Line Breaks

Sometimes you may want to add greater distinction between sections of your essay.
You can do this by adding a "horizontal line break," which is a horizontal line that stretches across the width of the page.

Horizontal line breaks are easy to do in Markdown.
Simply add three hyphens in a row to a new line, and make sure the line with the hyphens is preceded and followed by blank lines, like this:

```

---
```

On the front end, a horizontal line break will look like this:

---

## Table of contents

If you break the About page into sections you can title each of those sections using headings.
To do this, use the various heading sizes:

`# Heading 1` should only be used once, for title

`## Heading 2` should be used for sections of your page

`### Heading 3` should be used for sub-sections of your page

You can have multiple headings of the same type throughout your essay, and nest headings hierarchically just as you would an outline, like this: 

```
# First Heading 1

## First Heading 2

### First Heading 3

## Second Heading 2
```

...which looks like this on the front end:

# First Heading 1

## First Heading 2

### First Heading 3

## Second Heading 2

**Remember, always separate a heading from the text below it with a blank line.** 

If you do incorporate headings, you'll probably find it convenient to make use of the table of contents feature at the top of the essay.

The table of contents is generated from the include that looks like this:

{% raw %}{% include feature/nav-menu.html sections="About CollectionBuilder SA;About the About Page" %}{% endraw %}

"sections" is followed by an equals sign (`=`) and values separated by semicolons and encased with quotation marks.

The two values inside the quotation marks correspond to headings in the default about.md file:

`## About CollectionBuilder SA`

`## About the About Page`

**In order for the contents box to work correctly, the word in the Table of Contents Include needs to match a heading somewhere in your essay.**
When you click on the links in the table of contents, and your page will automatically scroll down to the corresponding section.

---

## Block Quotes

Add a block quote to your About page using the block quote include:

`{% raw %}{% include feature/blockquote.html quote="Knowledge comes, but wisdom lingers" speaker="Alfred Lord Tennyson" source="Locksley Hall" %}{% endraw %}`

Options:
- "quote" = quote text, can use Markdown
- "speaker" = name of the person who said the quote
- "source" = title of the quote's source
- "source-link" = link to source

See additional instructions and example at the top of the `/_includes/feature/blockquote.html` file.
