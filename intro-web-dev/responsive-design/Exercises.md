# Exercises

## Exercise 1

Create an HTML page with a `<div class="box">` element. Use CSS to:

1. Make the box 300px wide with a blue background on desktop (bigger than 768px)
1. Make the box 100% width with a red background on screens smaller than 768px

## Exercise 2

Create a page with a heading and paragraph. Implement the following responsive typography:

- Desktop (>900px): Heading 48px, Paragraph 18px
- Tablet (600px-900px): Heading 36px, Paragraph 16px
- Mobile (<600px): Heading 24px, Paragraph 14px

_style it overall to look nice_

## Exercise 3

Create a responsive image gallery that changes layout based on screen size use CSS calc() and/or percentages.

Build an image gallery with 6 placeholder images that displays:

- Desktop: 3 images per row 
- Tablet: 2 images per row 
- Mobile: 1 image per row

Other requirements:
1. Add text on the bottom-left corner of each image in the gallery (the text should be slightly transparent over the image)
1. Change the size of the text for each screen size
1. Choose images with different aspect ratio but in the image gallery the are all cropped appropriately to fit the same container
1. Clicking on the image in the gallery will open the image fullscreen in a new tab
1. Stlye the page and the gallery to look nice (e.g. rounded border to each image in the gallery, nice background, etc.)

Example for a nice gallery (but make a design of your own):

![](./img/image-gallery.png ':size=75%')

## Exercise 4
Clone and then update the ["holy grail" layout exercise](https://elevationacademy.github.io/fullstack-selfpaced/#/intro-web-dev/flexbox/Layout-Ex?id=exercise-1) to be responsive. 

1. Under 600px
1. Layout stacked in the following order: header &rarr; nav &rarr; main content &rarr; sidebar &rarr; footer
1. The navbar menu items should be horizontal

## Exercise 5
In this exercise you will be creating a responsive product card component. Note the responsiveness in the layout and in the typography.

**Large screens (bigger than 900px)** \
![](./img/product-card-large.png ':size=75%')

**Medium screens (600px to 900px)** \
![](./img/product-card-medium.png ':size=75%')

**Small screens (less than 600px)** \
![](./img/product-card-small.png ':size=50%')

## Exercise 6 - Bonus
Repeat the previuos exercise (responsive product card component) but this time using [tailwindcss](https://tailwindcss.com/) and zero css of your own.

Learn tailwindcss by yourself. Enable it in your website using the [Play CDN](https://tailwindcss.com/docs/installation/play-cdn) installation option.