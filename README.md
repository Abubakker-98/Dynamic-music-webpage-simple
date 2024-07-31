# Dynamic-music-webpage-simple
Dynamic music website with artist profiles, album shop, blog, and contact form. Features responsive design, social media links, and easy navigation.
The HTML and CSS you provided seem to represent a music-themed website. The structure includes various sections such as a homepage, an about section, a showcase of artists, a shop, a gallery, a blog section, and a contact form. Here's a breakdown of the key parts:

HTML Structure:
Header: Includes the site logo and a navigation bar with links to different sections of the page.
Home Section: Features a large background image with a heading and a button.
About Section: Contains information about the singer with a list of highlights and an image.
Artist Section: Displays multiple artists, each with an image and social media icons for sharing.
Shop Section: Lists music albums available for purchase, each with an image, price, and action buttons.
Gallery Section: Includes a filterable gallery with images categorized under music, party, performance, and stage show.
Blog Section: Displays blog posts with images, titles, dates, and a brief description.
Contact Section: Provides a form for users to send messages, along with a related image.
Subscribe Section: A call-to-action to subscribe to the newsletter.
Footer: Contains social media links and a credit section.

CSS Styles:
Global Styles: Defined custom colors and box shadows using CSS variables (--main-color, --primary-color, etc.). General styles for text, buttons, and scrolling behavior are also included.
Header Styling: Fixed at the top, with space between the logo and navigation links. The logo is styled with a font icon and color settings.
Section Styling: Each section (home, about, artist, shop, gallery, blog, contact, subscribe, footer) has specific styling for layout, font sizes, colors, and responsive design.
Buttons: Styled with hover effects using ::before and ::after pseudo-elements for smooth transitions.
Responsive Layout: The CSS uses media queries and grid layouts to ensure the design adapts to various screen sizes, especially in the artist and shop sections.
Potential Adjustments:
Content Duplication: The "Artist" and "Shop" sections have repeating content (e.g., artist names and album prices). This could be varied for better user experience.
Missing Images/Links: The <img src> attributes and the form action in the contact section seem to be placeholders. Replace these with actual image paths and form processing scripts.
Accessibility and SEO: Consider adding alt text to images and using semantic HTML tags to improve accessibility and search engine optimization.

# Responsive Navbar and Filterable Gallery

This project demonstrates a responsive navigation bar and a filterable image gallery using HTML, CSS, JavaScript, and jQuery. It includes functionality to toggle the navigation bar on smaller screens, filter images based on categories, and display images in a popup gallery.

## Features

- *Responsive Navbar*: The navigation bar adapts to different screen sizes. On smaller screens, a menu icon is used to toggle the visibility of the navbar.
- *Filterable Gallery*: The gallery allows users to filter images by category using buttons. The gallery is animated with jQuery to show and hide images smoothly.
- *Magnific Popup Integration*: Images in the gallery can be viewed in a popup modal with navigation controls, powered by the Magnific Popup plugin.

## Demo

A live demo of the project is available [here](#).

## Installation

1. Clone the repository:
    bash
    
    
2. Navigate to the project directory:
    bash
    

## Usage

Open index.html in your browser to view the project locally.

### JavaScript Functionality

- *Navbar Toggle*: The navbar visibility is toggled by clicking the menu icon. When the user scrolls, the navbar is hidden automatically.
    javascript
    let navbar = document.querySelector('.navbar');

    document.querySelector('#menu').onclick = () => {
        navbar.classList.toggle('active');
    }

    window.onscroll = () => {
        navbar.classList.remove('active');
    }
    

- *Gallery Filter and Magnific Popup*: The gallery uses jQuery for filtering and displaying images in a popup modal.
    javascript
    $(document).ready(function(){
        $('.button').click(function(){
            $(this).addClass('active').siblings().removeClass('active');
            var filter = $(this).attr('data-filter');
            if(filter == 'all'){
                $('.gallery .image').show(400);
            } else {
                $('.gallery .image').not('.' +filter).hide(200);
                $('.gallery .image').filter('.' +filter).show(200);
            }
        });

        $('.gallery').magnificPopup({
            delegate:'a',
            type:'image',
            gallery: { enabled:true }
        });
    });
    

## Dependencies

- *jQuery*: Used for DOM manipulation and event handling.
- *Magnific Popup*: A jQuery plugin for creating responsive, touch-friendly modal windows.

You can include the dependencies via CDN in your index.html:

```html
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/magnific-popup.js/1.1.0/jquery.magnific-popup.min.js"></script>
