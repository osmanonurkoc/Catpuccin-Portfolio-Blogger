# Catppuccin Portfolio Theme for Blogger

[![Live Demo](https://img.shields.io/badge/Live%20Demo-View%20Website-success?style=for-the-badge&color=8839ef)](https://osmanonurkoc.com)
![Downloads](https://img.shields.io/github/downloads/osmanonurkoc/Catpuccin-Portfolio-Blogger/total)
![License](https://img.shields.io/github/license/osmanonurkoc/Catpuccin-Portfolio-Blogger)
![Release](https://img.shields.io/github/v/release/osmanonurkoc/Catpuccin-Portfolio-Blogger)

A zero-code, modern, responsive, and single-page portfolio theme for Blogger, inspired by the soothing Catppuccin color palette. 

This theme allows you to customize your entire site without needing to know HTML or CSS. By simply changing a few boolean values (`true`/`false`) and CSS variables, you can make it truly yours.

## 🚀 Features
* **Modular Blog Architecture:** Seamlessly enable or disable the built-in blog system with a single boolean toggle. When disabled, blog links redirect to the homepage, but your static pages remain perfectly accessible.
* **Dark / Light Mode:** Seamless one-click transition (User preference is saved in browser local storage).
* **Catppuccin Palette:** Fully integrates official Latte (Vibrant) and Mocha (Pastel) color palettes.
* **Magic Variables:** Change the global accent color (buttons, highlights, shadows, text gradients) instantly by changing a single variable name.
* **Wide Mode & Lazy Grid:** Easily adjust the maximum width of your website and let the CSS `auto-fit` grid handle the responsive layout automatically.
* **Smart Lightbox:** Standard images inside your posts automatically feature a sleek, zoomable lightbox modal with a blurred Catppuccin crust overlay.
* **Interactive Image Compare:** Zero-code before/after image sliders to showcase your design iterations or restoration projects.
* **Boolean Toggle System:** Turn social media buttons, personal info, or project cards ON or OFF simply by changing a `false` to `true` in the HTML. No structural coding required!

---

## 🛠️ Installation

1. Download the `Catpuccin-Portfolio-Blogger-Template.xml` file.
2. Go to your Blogger Dashboard.
3. Click on the **Theme** tab on the left sidebar.
4. Click the down arrow next to the "Customize" button and select **Restore**.
5. Click upload, and select **Catpuccin-Portfolio-Blogger-Template.xml**.

---

## 🎨 How to Configure

Customizing the theme is incredibly easy. You can configure colors and layouts from the CSS section at the top, and manage your content from the HTML section below it.

### 1. Changing Accent Colors
Find the `/* 1. THEME CONFIGURATION (MAGIC VARIABLES) */` section at the very top of the CSS. You can change the primary and secondary accent colors here.

```css
:root {
  /* Dark Mode Accents (Mocha) - Pastel and Soothing */
  --dark-accent-primary: var(--mocha-mauve);
  --dark-accent-secondary: var(--mocha-blue);

  /* Light Mode Accents (Latte) - Vibrant and Saturated */
  --light-accent-primary: var(--latte-mauve);
  --light-accent-secondary: var(--latte-blue);
}
```
_Tip: Replace `mauve` and `blue` with other official Catppuccin colors like `peach`, `green`, `red`, `yellow`, `teal`, or `sapphire` to instantly change the entire look of your theme._

### 2. Layout Width & Grid Settings

Find the `/* 3. LAYOUT & GRID CONFIGURATION */` section in the CSS.

-   **Wide Mode:** Change the `--layout-max-width` value.
    
    -   Standard View: `1200px`
        
    -   Wide Mode: `1400px`
        
    -   Ultra Wide: `1600px`
        
    -   Fluid / Full Screen: `95%`
        
-   **Card Columns:** The theme uses a lazy responsive grid (`auto-fit`). By increasing the `300px` or `260px` minimum values inside `--services-columns` and `--projects-columns`, you can fit fewer cards per row. By decreasing it (e.g., `200px`), you can fit more cards side-by-side.
    

----------

## 📝 Creating Sub-Pages & The Modular Blog

### The Blog Toggle

Find `<b:with expr:value='true' var='enableBlog'>` at the top of the HTML.

-   Set it to `true` to use the theme as a hybrid Portfolio + Blog.
    
-   Set it to `false` to use it as a strict single-page portfolio (direct hits to /search or /archive will redirect to the homepage).
    

### Static Pages

Whether the blog is enabled or disabled, **Static Pages** (created from the "Pages" tab in Blogger) are permanently whitelisted. The theme includes a dedicated, clean layout specifically designed for these pages, complete with a "Back to Portfolio" navigation button.

----------

## 🎛️ Content Management (Boolean Toggles)

**You do not need to delete any HTML elements!** The theme uses Blogger's native `<b:if cond='...'>` structure to show or hide content.

To **SHOW** an element on your screen, change its value to `true`. To **HIDE** an element, change its value to `false`.

### Profile Image

The theme offers two modes for the profile area: "Icon Mode" and "Photo Mode". You can find these at the top of the HTML inside the `<div class='profile-img'>` tag.

-   **To use an Icon:** Set Icon Mode to `cond='true'` and Photo Mode to `cond='false'`. You can explore available icons at [Tabler Icons](https://tabler.io/icons)
    
-   **To use your own Photo:** Set Icon Mode to `cond='false'` and Photo Mode to `cond='true'`. Replace the `YOUR_IMAGE_URL_HERE` placeholder with your direct image link. Clicking the photo will automatically redirect visitors to your homepage.
    

### Social Media Links

Find the `<div class='social-links'>` section. There are **13 different pre-built social media buttons** waiting for you.

-   **Currently Active (`cond='true'`):** GitHub, Instagram, LinkedIn, Twitter/X.
    
-   **Currently Hidden (`cond='false'`):** YouTube, Dribbble, Behance, Facebook, Medium, Deviantart, Telegram, Google Play, Spotify.
    

Just toggle the ones you need and replace the `#` inside the `<a href='#'>` tag with your actual profile URL.

### Personal Information

You can find the Email, Phone, Location, Date of Birth, and Website info rows inside the `<div class='sidebar-info'>` tag. Hide the ones you don't want to display by changing them to `false`, and update the placeholder texts (like `osmanonurkoc`) with your own info for the active ones.

### "Reach Me" Call to Action

If you want to completely remove the gradient contact box at the bottom of the sidebar, simply change the `<b:if cond='true'>` right above it to `false`. If you decide to keep it, update the `mailto:your.email@example.com` string with your real email address. Also you can insert custom "Contacts page" url.

### Service and Project Cards

The theme is packed with pre-built card slots under both the "What I'm Doing" (Services) and "Portfolio & Projects" sections.

-   **Services:** Features up to 12 slots.
    
-   **Projects:** Features up to 12 slots for your extensive portfolio.
    

When you need to add a new project, you don't need to copy/paste any code. Just find a hidden card, set it to `true`, and fill in the title, description, and the `<a class='btn' href='#'>` link with your project details!

### Skill Pills (Tags)

You can add "Skill Pills" (small tag bubbles) inside any Service or Project card to highlight specific tools, skills, or technologies.

Thanks to the zero-code design, you **do not** need to assign manual color classes to each pill. The theme automatically applies a repeating sequence of 6 beautiful Catppuccin gradients based on the pill's order. These gradients dynamically adapt to look perfect in both Dark (Mocha) and Light (Latte) modes.

To add or remove a skill, simply insert a `<span class='skill-pill'>` inside the `<div class='card-tags'>` container of any card:
```
<div class='card-tags'>
  <span class='skill-pill'>UI / UX</span>
  <span class='skill-pill'>Android</span>
  <span class='skill-pill'>Figma</span>
</div>
```
### 🖼️ Dynamic Slideshows (Zero-Code)

Create beautiful, touch-friendly image carousels without writing any HTML! The theme uses a smart parser that converts standard Blogger editor elements into a fully functional slideshow with captions.

**How to use:** Wrap your images inside `[slideshow]` tags in Blogger's standard **Compose mode**.

-   **Titles:** Simply apply **Underline** (`U`) to any text under an image.
    
-   **Descriptions:** Apply **Strikethrough** (`S`) to any text under the title.
    

**Dynamic Sizing:** You can control the exact width of the slideshow by adding a number from 1 to 4 to the tag:

-   `[slideshow=1]` ➔ 60% Width (Small)
    
-   `[slideshow=2]` ➔ 75% Width (Medium)
    
-   `[slideshow=3]` ➔ 90% Width (Large)
    
-   `[slideshow=4]` or just `[slideshow]` ➔ 100% Width (Extra Large)
    

**Example in Compose View:**


```
[slideshow=3]

(Insert Image 1 using Blogger's image tool)
Underline this text for Title
Strikethrough this text for Description

(Insert Image 2)
Underline this text for the second slide's Title

[/slideshow]

```

_Note: Any standard image you add outside of a slideshow will automatically get a sleek, zoomable Lightbox feature. No extra steps needed!_

### 🔄 Interactive Image Compare (Before/After)

Perfect for showcasing design iterations, photo editing, or system customizations. The theme includes a custom before/after image slider that requires absolutely no coding.

**How to use:** Wrap exactly two images inside `[compare]` and `[/compare]` tags in Blogger's standard **Compose mode**. The first image will be the "After" (background/right side) and the second will be the "Before" (overlapping/left side) based on the sliding logic.

**Adding a Caption:** To add a beautiful, right-aligned caption under the slider, simply type your text below the images and apply **Italic** (`I`) formatting to it. The theme will automatically append a sleek Polaroid camera icon (`📸`) to the end of your caption!

**Example in Compose View:**
```
[compare]

(Insert Image 1)
(Insert Image 2)
[Italic] Restoring an old classic photo [/Italic]

[/compare]

```

### 🧱 Masonry Image Gallery (Zero-Code)

Display your photos, digital art, or screenshots in a beautiful, Pinterest-style Masonry grid! The theme automatically handles the complex grid calculations, provides a smooth "skeleton loading" pulse animation while high-resolution images download, and wraps them in a fully interactive slideshow modal.

**How to use:**
Simply upload your images using Blogger's standard image tool in **Compose mode** and wrap them inside `[gallery]` and `[/gallery]` tags. 

**Dynamic Columns:** By default, the gallery displays **3 columns** on desktop screens. You can customize this by adding a number to the tag (e.g., `[gallery=4]`). 
*Note: To ensure perfect responsiveness, the theme will automatically override your choice and force 2 columns on tablets and 1 column on mobile devices.*

**Interactive Modal:**
Clicking any image in the gallery opens a dedicated, full-screen Catppuccin modal equipped with:
* ▶️ **Slideshow Autoplay:** Play/Pause controls to automatically cycle through the gallery.
* 🔍 **Zoom & Pan:** Use your mouse wheel to zoom in (up to 400%) and click-and-drag to pan around the image.

**Example in Compose View:**
```text
Here is my latest digital art collection:

[gallery=4]
(Insert Image 1)
(Insert Image 2)
(Insert Image 3)
(Insert Image 4)
[/gallery]
```

### 💻 Code Blocks (Syntax Box)

As a developer, sharing code snippets should look beautiful. This theme includes a custom, zero-code syntax box parser. You **do not** need to switch to HTML view to add code blocks!

Simply wrap your code with `[code]` and `[/code]` tags directly in Blogger's standard Compose mode.

**Example:**
```
Here is my awesome script:

[code]
function sayHello() {
  console.log("Hello, World!");
}
[/code]

```

The theme will automatically parse these tags and render a sleek, Mac-window style code block that perfectly adapts to both Dark (Mocha) and Light (Latte) modes, complete with horizontal scrolling and a one-click copy button!

### 🐱 Themed Custom Link Widget

Highlight important links with a beautiful, theme-adaptive Catppuccin mascot separator! This zero-code feature automatically generates a sleek separator line featuring a sleeping cat SVG right above your link. The SVG color dynamically adapts to your Light/Dark mode and accent colors with a smooth hover effect.

**How to use:**
Simply wrap your link inside `[link]` and `[/link]` tags in Blogger's standard **Compose mode**. The parser is smart enough to handle two different methods:

**Method 1: Raw URL**
Just paste the web address directly. The theme will automatically wrap it in an anchor tag and make it clickable.
```text
[link]
Check out the repo: https://github.com/osmanonurkoc/WSL2Scripts
[/link]
```

### 💬 Disqus Comments Integration

The theme includes built-in support for Disqus comments. Because Disqus is embedded via an iframe, it is designed to be smart enough to detect the theme's background colors. It will automatically switch to its native **Dark Variant** to perfectly complement the Catppuccin Mocha aesthetic!

The comments are configured to **only** appear at the bottom of dedicated Blog Post pages (they will remain completely hidden on your static pages and homepage).

**How to set it up:**
1. Go to [Disqus](https://disqus.com/) and create a free account.
2. Click on "Get Started" and choose "I want to install Disqus on my site".
3. Create a new site profile. You will be asked to create a **Shortname** (e.g., `osmanonurkoc`). Copy this exact shortname.
4. Open the `Catpuccin-Portfolio-Blogger-Template.xml` file in your editor (or the Blogger HTML editor).
5. Press `CTRL + F` and search for `YOUR_DISQUS_SHORTNAME`.
6. Replace `YOUR_DISQUS_SHORTNAME` with the shortname you created in Step 3.
7. Save the theme. 

*Example Code:*
```javascript
/* INSERT YOUR DISQUS SHORTNAME BELOW: */
s.src = 'https://osmanonurkoc.disqus.com/embed.js';
```

### 📑 Advanced AJAX Pagination Engine

This theme utilizes a seamless, zero-delay Advanced AJAX Pagination Engine. It automatically bypasses Blogger's native server-side post limits by fetching older posts in the background while your visitors are browsing the first page.

**No Dashboard Hacks Required!**
Unlike older themes, you **do not** need to change your Blogger Dashboard's "Max posts shown on main page" limit to a huge number. You can safely leave your Blogger limit to its default (e.g., 7 or 10). The theme will intelligently and invisibly fetch all the remaining posts behind the scenes!

**How to Change Posts Per Page:**
You can easily control exactly how many posts appear on a single page directly from the theme's code.
1. Open the theme HTML editor (`Catpuccin-Portfolio-Blogger-Template.xml`).
2. Search (`CTRL + F`) for `ADVANCED AJAX PAGINATION ENGINE`.
3. Find the line: `var postsPerPage = 6;`
4. Change the number `6` to whatever limit you prefer (e.g., `4`, `8`, `12`).
5. Save the theme. The pagination buttons will automatically adapt to your new limit as soon as the background fetch is complete!

---

## 🪄 Supercharge Your Workflow: The Official Chrome Extension

Tired of manually typing `[slideshow]`, `[gallery]`, or `[code]` tags in the Blogger editor? We've built a custom Chrome Extension that integrates perfectly into Blogger's native Compose toolbar!

👉 **[Download the Catppuccin Blogger Editor Tools here!](https://github.com/osmanonurkoc/Catpuccin-Blogger-Extension)**

**Why should you use the extension?**
* 🖱️ **One-Click Formatting:** Inject galleries, image sliders, code boxes, and custom links with a single click—no brackets required.
* 🧠 **Smart Toggle Engine:** Highlight an existing gallery and click the button again to safely unwrap the tags without harming your images.
* 🎨 **Inline Code Highlighting:** The *only* way to apply inline `<code...>` styling inside paragraphs easily. Select a word, click the `</>` button, and it highlights perfectly.

*We highly recommend installing this companion extension before exploring the shortcode features above!*

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

----------

_Created by [@osmanonurkoc](https://github.com/osmanonurkoc)_ | _Powered by Catppuccin | Designed for Blogger_
