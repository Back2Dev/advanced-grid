---
sidebar_position: 1
---

# Design brief

Computer systems contain data. Lots of it. There is a need to list, search, sort and filter. Typically each table in the database has views which are hand crafted to look at the data. This is expensive to build, and pulls developer resources away from doing higher value work. Different users want different views of the data, so it's hard to meet everyone's preferences.

So our objective is to provide a general purpose tool which:

- Can display data in a table
- Allow a user to edit and save their own view of the data
- Provide options to filter and sort
- Provide a page to edit existing records
- Provide a page to add new records
- Be able to select records and
  - Delete them
  - Modify them (bulk modify)
  - Archive them
  - Export to csv

All this appears fairly straight forward. Let's have a look at what we have so far, and look at other systems for ideas on how to tackle this.

## Existing templated views

The code for this view was generated from a template. It is relatively easily customised/edited, and it ticks most of the boxes, apart from user configurability.

![Forms - templated view](/captures/forms-templated.png)

## Another approach - editable views

The code for this view begins to solve for the user configurable views, but much of the functionality of the templated view is not present yet. (2 steps forward, one step back?)
![Forms - half way view](/captures/forms-halfway.png)

So let's have a close look. The user can now select a named view.

![Forms - templated view](/captures/forms-select-view.png)

If you look at the page, you will notice that only 2 records are shown, because the view includes a filter on the `slug` for `nsw`

![Forms - templated view](/captures/forms-nsw-view.png)

Let's have a closer look at how we edit a view. We click on the red pencil to edit the currently selected view

![Forms - templated view](/captures/forms-edit-view.png)

Notes

1. Name of the view
1. The view can be set to read only (as can individual columns)
1. Drag handle allows re-ordering of columns
1. Column filter, in this case `nsw`
1. Selectable sort column

Clicking the "Add columns" button shows a dialogue, where you can select additional columns

![Forms - templated view](/captures/forms-add-columns.png)

## Filtering - an example that could be better

Let's have a look at a page which is functional, but has a few things that could be improved.

![Forms - templated view](/captures/filtering-bad-example.png)

1. The filter controls take up too much space - on a small laptop screen you will not see any data without scrolling
2. Filters are not clear as to their purpose
3. The All/Engagement/Contract/Settlement filter shows all options selected

## Other approaches

So let's have a look for inspiration from ebay:

![Forms - templated view](/captures/ebay-filters.png)

You'll notice that the filtering options are on the side. This is good, because modern laptops have wide screens.

It also provides numbers in each filter value (eg Release year)

It doesn't show all possible values, just the most frequent, but it does allow you to see them.

### Ebay view customiser

eBay allows you to customise the view - we could adopt some of these options

![Forms - templated view](/captures/ebay-customise.png)

## Kickstarter search

Kickstarter does the searching in a conversational manner

![Forms - templated view](/captures/kickstarter-search.png)
