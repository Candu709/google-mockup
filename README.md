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
I avoided using a CSS reset sheet becouse while I realize it could speed up the development in a small project like this, I also felt it could fix something that I didnt know or fully understand yet without teaching me much about it.

### CSS Naming Conventions
Early in the project i was pointed out to Modular CSS by one of the maintener of the [TOP Discord](). After some brief research, I tried to implement a naming convention following the guidelines from OOCSS, BEM and SMACSS. I later added comments on top of each section both as a reminder and for easier navigation through the list.

### Localization
By default I am redirected from google.com to google.it, I decided to recreate this localized version as it has some additional elements (the "Google Store" links and the [Carbon free banner](#carbon-free-banner) in the footer) that are interesting to place, but translating the texts into English for easier understanding when requesting feedback.\
Later on i might build two different localized pages to practice using alternates versions of a page.

### Font sizes 
The original page uses absolute sizes for most things, I chose to instead use mostly relative units since i noticed i had to keep zooming to properly read text in the original. 
This has the additional advantage of respecting the user browser settings and at "normal" size on Google Chrome things should be really close to their original size.

### Colors
Most of the colors are eyeballed and not 100% accurate, while i could have gone around and pick them with the browser developer tool, it didnt feel like a useful investment of time relative to their importance in the exercise. I might correct them in the future but its not a priority.

### Footer Color 
I experimented giving the footer elements colors that are mostly transparent but sligtly dark, this should make possible to have a different background but still retain the difference in color of the footer.\
I am aware that it could also present a possible visibility issue if a dark bagkround is selected, but since right now its only possible trough editing css  I left it in and i might expand upon it after learning more ways to dynamically edit a webpage.

### Carbon free banner
On large viewports this element is horizontally centered relative to the page and  its siblings are supposed to go either side of the viewport.\
My first tought was to give the parent element the `justify-content: space-between;` property, but since the siblings elements have different widths the remaining space, along with the banner, ends up being offeset to the center of the page.\
To fix this i then set both the sibling elements to a fixed width that is >= of the widest of the two, ensuring that the leftover space is always centered to the page and the banner is placed at the center of that.\
On smaller viewports the banner its displayed above its sibling, wich in turn have a gap between them and the edges of the viewport.\
To reproduce this I added a media query that
modifies the `order` property of the elements to place it before its siblings, 
and then
sets the width of the banner to the same as the viewport, exploiting the `flex-wrap` property of the parent element to place itself in its own row.

### Searchbar border radius
