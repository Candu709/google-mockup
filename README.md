# Google Mockup
**A small project based on [this assignment](https://www.theodinproject.com/paths/foundations/courses/foundations/lessons/html-css#assignment "Project: Google Homepage") in the foundations path of [The Odin Project](https://www.theodinproject.com) course.**

This is an exercise in deconstructing and rebuilding an existing web page.

## Assignments

- [ ] Build the Google.com homepage
- [ ] Build the Google search result page

## Objectives

The main objectives are to practice:
- Building a page in HTML
- Styling a page using CSS
- Using Git as the local version control manager
- Using GitHub as the remote version control manager

## Development Notes

### No CSS reset/normalize
I avoided using a CSS reset sheet becouse I felt it could fix something that I didnt know or fully understand yet without teaching me much about it.

### Localization
By default I am redirected from google.com to google.it, I decided to recreate this localized version as it has some additional elements (the google store links and the [carbon free banner](#carbon-free-banner) in the footer) that are interesting to place, but translating the texts into English for easier understanding when requesting feedback.  
Later on i might build two different localized pages to practice using altenates version of a page.

### Carbon free banner
On large viewports this element is centered relative to the page and  its siblings are supposed to go either side of the viewport.\
My first tought was to give the parent element the ```justify-content: space-between;``` property, but since the siblings elements have different widths the banner gets centered in the remaining space and that ends up being offeset to the center of the page.\
To fix this i then set both the sibling elements to a fixed width that is >= of the widest of the two, ensuring that the leftover space is always centered to the page and the banner is placed at the center of that.\
On smaller viewports the banner its displayed above its sibling, wich in turn have a gap between them and the edges of the viewport.\
To reproduce this I added a media query that
modifies the `order` property of the elements to move it before its siblings, 
and then
sets the width of the banner to the same as the viewport, exploiting the `flex-wrap` property of the parent element to place itself in its own row.