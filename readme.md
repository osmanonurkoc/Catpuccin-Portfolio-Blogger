
# Catppuccin Portfolio Theme for Blogger

[![Live Demo](https://img.shields.io/badge/Live%20Demo-View%20Website-success?style=for-the-badge&color=8839ef)](https://catpuccin.blogspot.com)

A zero-code, modern, responsive, and single-page portfolio theme for Blogger, inspired by the soothing Catppuccin color palette. 

This theme allows you to customize your entire site without needing to know HTML or CSS. By simply changing a few boolean values (`true`/`false`) and CSS variables, you can make it truly yours.

## 🚀 Features
* **Dark / Light Mode:** Seamless one-click transition (User preference is saved in browser local storage).
* **Catppuccin Palette:** Fully integrates official Latte (Vibrant) and Mocha (Pastel) color palettes.
* **Magic Variables:** Change the global accent color (buttons, highlights, shadows, text gradients) instantly by changing a single variable name.
* **Wide Mode:** Easily adjust the maximum width of your website.
* **Boolean Toggle System:** Turn social media buttons, personal info, or project cards ON or OFF simply by changing a `false` to `true` in the HTML. No structural coding required!

---

## 🛠️ Installation

1. Copy the contents of the `theme.xml` file.
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
        
    -   Fluid / Full Screen: `95%`
        
-   **Card Columns:** By increasing the `260px` value (e.g., `350px`) inside `--services-columns` and `--projects-columns`, you can fit fewer cards per row. By decreasing it (e.g., `200px`), you can fit more cards side-by-side.
    

----------

## 📝 Creating Sub-Pages (Important!)

This theme is specifically designed to function as a **single-page portfolio** on the homepage.

If you want to create separate, standalone sub-pages (like a dedicated About page, Resume, or Contact page), **DO NOT use the Blogger "Posts" feature**.

Instead, use Blogger's built-in **"Pages"** feature from the left sidebar. The theme includes a dedicated, clean layout specifically designed for Static Pages, complete with a "Back to Portfolio" navigation button.

----------

## 🎛️ Content Management (Boolean Toggles)

**You do not need to delete any HTML elements!** The theme uses Blogger's native `<b:if cond='...'>` structure to show or hide content.

To **SHOW** an element on your screen, change its value to `true`. To **HIDE** an element, change its value to `false`.

### Profile Image

The theme offers two modes for the profile area: "Icon Mode" and "Photo Mode". You can find these at the top of the HTML inside the `<div class='profile-img'>` tag.

-   **To use an Icon:** Set Icon Mode to `cond='true'` and Photo Mode to `cond='false'`.
    
-   **To use your own Photo:** Set Icon Mode to `cond='false'` and Photo Mode to `cond='true'`. Replace the `YOUR_IMAGE_URL_HERE` placeholder with your direct image link. Clicking the photo will automatically redirect visitors to your homepage.
    

### Social Media Links

Find the `<div class='social-links'>` section. There are 9 different pre-built social media buttons waiting for you.

-   **Currently Active (`cond='true'`):** GitHub, Instagram, LinkedIn, Twitter/X.
    
-   **Currently Hidden (`cond='false'`):** YouTube, Dribbble, Behance, Facebook, Medium, Deviantart, Telegram, Google Play, Spotify.
    

Just toggle the ones you need and replace the `#` inside the `<a href='#'>` tag with your actual profile URL.

### Personal Information

You can find the Email, Phone, Location, Date of Birth, and Website info rows inside the `<div class='sidebar-info'>` tag. Hide the ones you don't want to display by changing them to `false`, and update the placeholder texts (like `osmanonurkoc`) with your own info for the active ones.

### "Reach Me" Call to Action

If you want to completely remove the gradient contact box at the bottom of the sidebar, simply change the `<b:if cond='true'>` right above it to `false`. If you decide to keep it, update the `mailto:your.email@example.com` string with your real email address. Also you can insert custom "Contacts page" url.

### Service and Project Cards

There are **8 pre-built cards** (16 in total) under both the "What I'm Doing" (Services) and "Portfolio & Projects" sections.

-   The first 4 cards are active by default (`cond='true'`).
    
-   The remaining 4 cards are hidden as backups (`cond='false'`).
    

When you need to add a new project, you don't need to copy/paste any code. Just find a hidden card, set it to `true`, and fill in the title, description, and the `<a class='btn' href='#'>` link with your project details!

### Skill Pills (Tags)

You can add "Skill Pills" (small tag bubbles) inside any Service or Project card to highlight specific tools, skills, or technologies. 

Thanks to the zero-code design, you **do not** need to assign manual color classes to each pill. The theme automatically applies a repeating sequence of 6 beautiful Catppuccin gradients based on the pill's order. These gradients dynamically adapt to look perfect in both Dark (Mocha) and Light (Latte) modes.

To add or remove a skill, simply insert a `<span class='skill-pill'>` inside the `<div class='card-tags'>` container of any card:

```html
<div class='card-tags'>
  <span class='skill-pill'>UI / UX</span>
  <span class='skill-pill'>Android</span>
  <span class='skill-pill'>Figma</span>
</div>

## 📄 License

This project is licensed under the [MIT License](LICENSE).

----------

_Created by [@osmanonurkoc](https://github.com/osmanonurkoc)_ | _Powered by Catppuccin | Designed for Blogger_
