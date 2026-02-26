# CLAUDE.md - Tiffany's Dairy Farm Website

## Project Overview

This is a **static HTML/CSS website** for Tiffany's Dairy Farm, an artisanal cheese and dairy farm business. The site showcases farm products (cheeses, butter, yogurt, cream), farm activities, blog posts, an online store, testimonials, and contact information. The theme is inspired by Terry Pratchett's Discworld (the character Tiffany Aching).

**License:** MIT

## Tech Stack

- **Pure HTML5 and CSS** — no JavaScript, no frameworks, no build tools
- No package manager (`package.json` does not exist)
- No bundler, linter, test framework, or CI/CD pipeline
- Pages are served as static `.html` files

## Repository Structure

```
/
├── index.html              # Homepage — about, products, activities, farm overview
├── about.html              # About Us — farm story, meet Tiffany, philosophy
├── products.html           # Products — cheese selection, dairy products, product images
├── farm-activities.html    # Farm Activities — tours, workshops, seasonal events
├── our-farm.html           # Our Farm — animal welfare, sustainability, animal gallery
├── contact.html            # Contact — email, phone, location, farmers' markets
├── blog.html               # Blog/News — articles and posts
├── online-store.html       # Online Store — featured products with prices
├── testimonials.html       # Testimonials — customer reviews, press/media
├── styles.css              # Shared stylesheet (all pages link to this)
├── images/                 # All image assets (JPG files)
├── LICENSE                 # MIT License
└── CLAUDE.md               # This file
```

## Development Workflow

### No Build or Test Steps

There are **no build commands, no test suites, and no linting tools** configured. The site is purely static HTML/CSS. To preview changes, open any `.html` file directly in a browser.

### Making Changes

1. Edit HTML files directly — there is no templating system
2. Shared styles go in `styles.css`; page-specific styles use inline `<style>` blocks in the `<head>`
3. Images go in the `images/` directory as `.jpg` files
4. There is no hot-reload or dev server — refresh the browser manually after edits

## Code Conventions

### HTML Structure

Every page follows this layout pattern:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>[Page Title] - Tiffany's Dairy Farm</title>
  <link rel="stylesheet" href="styles.css">
  <meta name="description" content="...">
  <meta name="author" content="Tiffany's Dairy Farm">
  <!-- Optional: page-specific <style> block -->
</head>
<body>
  <header>
    <h1>Welcome to Tiffany's Dairy Farm</h1>
    <img src="images/horse.jpg" alt="Tiffany's Dairy Farm Logo">
    <nav><!-- 8-item navigation --></nav>
  </header>
  <main>
    <!-- Page content in <section> elements -->
  </main>
  <footer>
    <p>&copy; 2023 Tiffany's Dairy Farm. All rights reserved.</p>
  </footer>
</body>
</html>
```

### Navigation

All pages share an identical 8-link navigation bar:

- Home (`index.html`), About Us (`about.html`), Products (`products.html`), Farm Activities (`farm-activities.html`), Our Farm (`our-farm.html`), Contact (`contact.html`), Blog/News (`blog.html`), Online Store (`online-store.html`)

When adding a new page, update the `<nav>` in **every** HTML file to include it.

### Styling

- **`styles.css`** — shared base styles (reset, header, nav, main, footer, typography)
- Max content width: `960px` (set on `main`)
- Font: Arial, sans-serif
- Color scheme: dark text (`#333`, `#666`) on white/light gray (`#f5f5f5`) backgrounds; dark nav/footer (`#333`) with white text
- The `.animal-image` class is used for fixed-size animal photos (300x200px, `object-fit: cover`)
- Page-specific styles (e.g., banner sizing, product image grids) are defined in inline `<style>` blocks within individual pages

### Links and Paths

- All internal links use **relative paths** (e.g., `href="about.html"`, `src="images/cow.jpg"`)
- All pages sit at the root level — there are no subdirectories for pages
- Image references use the `images/` prefix

## Known Issues

These exist in the current codebase and should be addressed when modifying affected files:

- **Duplicate section IDs**: `index.html` has two `<section id="farm">` blocks; `contact.html` has two `<section id="contact">` blocks
- **Unclosed sections**: `contact.html` has an unclosed first `<section>` before the second begins
- **Missing footer**: `blog.html` is missing the standard `<footer>` element
- **Missing closing tags**: `about.html` is missing closing `</main>`, `</body>`, and `</html>` tags
- **HTML lang inconsistency**: Most pages use `lang="en"` but `products.html` and `testimonials.html` use `lang="en-US"`
- **CSS comment syntax error**: `products.html` has `width: 200px; /` (stray `/` instead of proper comment)
- **Broken image references**: `blog.html` references images that don't exist in the `images/` directory (e.g., `cheese-making.jpg`, `fall-recipes.jpg`, `night-watch.jpg`, `creativity.jpg`, `cats.jpg`)
- **Broken page links**: `online-store.html` links to `product-details.html` which does not exist
- **Unclosed `<main>` tag in `online-store.html`**: `</section>` appears before the product list is properly wrapped
- **`testimonials.html`**: `customer-reviews` section is not properly closed before `customer-testimonials` begins
