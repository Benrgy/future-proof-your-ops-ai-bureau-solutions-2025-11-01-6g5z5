# AI Bureau Solutions Landing Page - Maintenance & Customization Guide

Welcome! This comprehensive guide will help you maintain and customize your AI Bureau Solutions landing page. Whether you're updating text, fixing links, or adding new pages, this documentation provides step-by-step instructions tailored to your specific HTML structure.

---

## Table of Contents

1. [Getting Started](#getting-started)
2. [Understanding Your Page Structure](#understanding-your-page-structure)
3. [Updating Text and Content](#updating-text-and-content)
4. [Modifying Tailwind CSS Classes](#modifying-tailwind-css-classes)
5. [Fixing and Managing Links](#fixing-and-managing-links)
6. [Adding Privacy and Terms Pages](#adding-privacy-and-terms-pages)
7. [Troubleshooting Common Issues](#troubleshooting-common-issues)
8. [Best Practices](#best-practices)

---

## Getting Started

### What You'll Need

- A text editor (we recommend **Visual Studio Code**, which is free)
- A web browser for testing (Chrome, Firefox, or Safari)
- Your HTML file (`index.html`)
- Basic understanding of HTML tags (explained below)

### How to Open Your File

1. Open your text editor
2. Click **File** → **Open** (or press `Ctrl+O` on Windows / `Cmd+O` on Mac)
3. Navigate to your `index.html` file and open it
4. You're ready to edit!

### Viewing Your Changes

After making edits:
1. Save your file (press `Ctrl+S` on Windows / `Cmd+S` on Mac)
2. Open your `index.html` in a web browser
3. Refresh the page (press `F5` or `Ctrl+R`)
4. Your changes should appear

---

## Understanding Your Page Structure

Your landing page is organized into distinct sections. Understanding this structure will help you navigate and make changes confidently.

### Page Sections Overview

```
Header Navigation (Top of page - always visible)
    ↓
Hero Section (Large welcome message with call-to-action buttons)
    ↓
Features Section (3 feature cards describing services)
    ↓
Benefits Section (3 benefit cards with statistics)
    ↓
About Us Section (Company information)
    ↓
Testimonials Section (4 customer testimonials)
    ↓
FAQ Section (5 frequently asked questions)
    ↓
CTA Section (Call-to-action for consultations)
    ↓
Contact Section (Contact form and information)
    ↓
Footer (Links, social media, copyright)
```

### Finding Specific Sections

Each section has an **ID** (identifier) that makes it easy to find. Look for lines like:

```html
<section id="features" class="py-24 bg-gray-50">
```

The `id="features"` tells you this is the Features section. You can use your text editor's search function:
- **Windows/Linux**: Press `Ctrl+F`
- **Mac**: Press `Cmd+F`

Then type the section name (like "features") to jump directly to it.

---

## Updating Text and Content

### Principle: Find the Text, Replace It

The most common task is updating the text content on your page. Here's how:

### 1. Updating the Header Navigation

**Location**: Near the top of the file, look for:

```html
<header class="sticky top-0 z-50 bg-white shadow-md">
```

**What you'll find inside:**
- Logo text: `<span class="text-xl font-bold text-gray-900">AI Bureau</span>`
- Navigation links under `<!-- Desktop Menu -->` and `<!-- Mobile Menu -->`

**How to update the logo text:**

Find this line:
```html
<span class="text-xl font-bold text-gray-900">AI Bureau</span>
```

Replace `AI Bureau` with your company name. For example:
```html
<span class="text-xl font-bold text-gray-900">Your Company Name</span>
```

**How to update navigation links:**

Find the Desktop Menu section:
```html
<div class="hidden md:flex items-center space-x-8">
    <a href="#features" class="text-gray-700 hover:text-gray-900 font-medium transition-colors duration-300">Features</a>
    <a href="#benefits" class="text-gray-700 hover:text-gray-900 font-medium transition-colors duration-300">Benefits</a>
    <!-- More links here -->
</div>
```

To change "Features" to something else, simply replace the text:
```html
<a href="#features" class="text-gray-700 hover:text-gray-900 font-medium transition-colors duration-300">Our Features</a>
```

**Important**: Don't change the `href="#features"` part—this tells the page where to scroll to. Only change the visible text.

---

### 2. Updating the Hero Section (Main Welcome Message)

**Location**: Search for `<!-- Hero Section -->` using Ctrl+F

**What you'll find:**

```html
<h1 class="text-5xl md:text-6xl lg:text-7xl font-bold text-gray-900 leading-tight tracking-tight">
    Future-Proof Your Ops: <span class="text-transparent bg-clip-text bg-gradient-to-r from-gray-900 to-gray-700">AI Bureau Solutions</span>
</h1>
```

This is your main headline. To update it:

1. Find the text between `<h1>` and `</h1>`
2. Replace it with your new headline
3. Keep the `<span>` tags around the gradient text if you want that special colored effect

**Example:**
```html
<h1 class="text-5xl md:text-6xl lg:text-7xl font-bold text-gray-900 leading-tight tracking-tight">
    Transform Your Business: <span class="text-transparent bg-clip-text bg-gradient-to-r from-gray-900 to-gray-700">Smart Solutions</span>
</h1>
```

**Updating the hero description:**

Find this text:
```html
<p class="text-xl md:text-2xl text-gray-600 leading-relaxed max-w-2xl">
    Navigate the complexities of modern business with our cutting-edge AI automation services...
</p>
```

Simply replace the paragraph text with your own. For example:
```html
<p class="text-xl md:text-2xl text-gray-600 leading-relaxed max-w-2xl">
    Your new description goes here. Make it compelling and clear about your value proposition.
</p>
```

**Updating trust indicators (500+, 99.9%, 40%):**

Find this section:
```html
<!-- Trust Indicators -->
<div class="flex items-center gap-8 pt-8 border-t border-gray-200">
    <div>
        <p class="text-3xl font-bold text-gray-900">500+</p>
        <p class="text-gray-600">Enterprise Clients</p>
    </div>
    <!-- More indicators here -->
</div>
```

To update the numbers and labels:
```html
<div>
    <p class="text-3xl font-bold text-gray-900">1000+</p>
    <p class="text-gray-600">Happy Customers</p>
</div>
```

---

### 3. Updating Feature Cards

**Location**: Search for `<!-- Features Section -->` and then `<!-- Feature 1: Predictive Maintenance -->`

Each feature card has this structure:

```html
<div class="feature-card bg-white p-8 rounded-xl shadow-md hover:shadow-xl transition-all duration-300">
    <h3 class="text-2xl font-bold text-gray-900 mb-4">Predictive Maintenance</h3>
    <p class="text-gray-600 leading-relaxed mb-4">
        Harness the power of advanced machine learning...
    </p>
    <ul class="space-y-2 text-gray-600">
        <li class="flex items-start">
            <i class="fas fa-check text-gray-900 mr-3 mt-1 flex-shrink-0"></i>
            <span>Real-time equipment monitoring and diagnostics</span>
        </li>
        <!-- More bullet points -->
    </ul>
</div>
```

**To update a feature card:**

1. **Change the title**: Replace `Predictive Maintenance` with your feature name
2. **Change the description**: Replace the paragraph text
3. **Update bullet points**: Each `<li>` contains one bullet point. Add, remove, or modify as needed

**Example of updating a bullet point:**

Original:
```html
<li class="flex items-start">
    <i class="fas fa-check text-gray-900 mr-3 mt-1 flex-shrink-0"></i>
    <span>Real-time equipment monitoring and diagnostics</span>
</li>
```

Updated:
```html
<li class="flex items-start">
    <i class="fas fa-check text-gray-900 mr-3 mt-1 flex-shrink-0"></i>
    <span>24/7 system monitoring with instant alerts</span>
</li>
```

**Don't touch**: The `<i class="fas fa-check...">` part—this creates the checkmark icon.

---

### 4. Updating Benefit Cards

**Location**: Search for `<!-- Benefits Section -->`

Benefit cards are similar to feature cards but include statistics:

```html
<div class="benefit-item bg-gradient-to-br from-white to-gray-50 border border-gray-200 p-8 rounded-xl">
    <div class="flex items-center justify-between mb-6">
        <div class="w-16 h-16 bg-gradient-to-br from-gray-900 to-gray-700 rounded-lg flex items-center justify-center">
            <i class="fas fa-clock text-white text-2xl"></i>
        </div>
        <span class="text-4xl font-bold text-gray-900">99.9%</span>
    </div>
    <h3 class="text-2xl font-bold text-gray-900 mb-4">Minimize Downtime</h3>
    <p class="text-gray-600 leading-relaxed mb-6">
        Achieve industry-leading uptime...
    </p>
</div>
```

**To update a benefit card:**

1. **Change the statistic**: Replace `99.9%` with your number
2. **Change the title**: Replace `Minimize Downtime`
3. **Change the description**: Update the paragraph
4. **Update bullet points**: Same as feature cards

---

### 5. Updating Testimonials

**Location**: Search for `<!-- Testimonials Section -->`

Each testimonial has this structure:

```html
<div class="testimonial-card bg-white border border-gray-200 p-8 rounded-xl shadow-md">
    <div class="flex items-center justify-between mb-4">
        <div>
            <h4 class="text-lg font-bold text-gray-900">Sarah Chen</h4>
            <p class="text-gray-600">VP Operations, TechCorp Industries</p>
        </div>
    </div>
    <div class="flex items-center mb-4">
        <i class="fas fa-star text-yellow-400"></i>
        <i class="fas fa-star text-yellow-400"></i>
        <i class="fas fa-star text-yellow-400"></i>
        <i class="fas fa-star text-yellow-400"></i>
        <i class="fas fa-star text-yellow-400"></i>
    </div>
    <p class="text-gray-600 leading-relaxed">
        "AI Bureau's predictive maintenance solution has been transformative..."
    </p>
</div>
```

**To update a testimonial:**

1. **Change the name**: Replace `Sarah Chen`
2. **Change the title/company**: Replace `VP Operations, TechCorp Industries`
3. **Change the quote**: Replace the text in quotes
4. **Adjust stars**: Each `<i class="fas fa-star...">` is one star. Remove or add lines to change the rating

**Example - Changing to 4 stars:**

Remove one star line:
```html
<div class="flex items-center mb-4">
    <i class="fas fa-star text-yellow-400"></i>
    <i class="fas fa-star text-yellow-400"></i>
    <i class="fas fa-star text-yellow-400"></i>
    <i class="fas fa-star text-yellow-400"></i>
</div>
```

---

### 6. Updating FAQ Questions and Answers

**Location**: Search for `<!-- FAQ Section -->`

Each FAQ item has this structure:

```html
<div class="faq-item bg-white rounded-lg shadow-md overflow-hidden">
    <button class="faq-question w-full px-8 py-6 flex items-center justify-between hover:bg-gray-50 transition-colors duration-300 cursor-pointer">
        <span class="text-lg font-bold text-gray-900 text-left">How does your AI maintain data security and compliance?</span>
        <i class="faq-icon fas fa-chevron-down text-gray-600 transition-transform duration-300"></i>
    </button>
    <div class="faq-answer hidden px-8 pb-6 bg-gray-50">
        <p class="text-gray-600 leading-relaxed">
            Data security is our highest priority...
        </p>
    </div>
</div>
```

**To update an FAQ:**

1. **Change the question**: Replace the text in the `<span>` tag
2. **Change the answer**: Replace the paragraph text in the `faq-answer` div

**Example:**

```html
<span class="text-lg font-bold text-gray-900 text-left">What is your pricing model?</span>
```

```html
<p class="text-gray-600 leading-relaxed">
    We offer flexible pricing based on your company size and needs...
</p>
```

---

### 7. Updating Contact Information

**Location**: Search for `<!-- Contact Section -->`

Find the contact details:

```html
<a href="mailto:bengrauwde@hotmail.com" class="text-gray-600 hover:text-gray-900 transition-colors duration-300">
    bengrauwde@hotmail.com
</a>
```

**To update the email:**

Replace `bengrauwde@hotmail.com` with your email address (change it in both places—in the `href` and in the visible text):

```html
<a href="mailto:your@email.com" class="text-gray-600 hover:text-gray-900 transition-colors duration-300">
    your@email.com
</a>
```

**To update the phone number:**

Find:
```html
<p class="text-gray-600">+1 (555) 123-4567</p>
```

Replace with:
```html
<p class="text-gray-600">+1 (555) 987-6543</p>
```

**To update office locations:**

Find:
```html
<p class="text-gray-600">San Francisco, CA | New York, NY | London, UK</p>
```

Replace with your locations:
```html
<p class="text-gray-600">Los Angeles, CA | Chicago, IL | Boston, MA</p>
```

---

### 8. Updating Footer Links and Text

**Location**: Search for `<!-- Footer -->`

The footer contains multiple sections:

**Company name in footer:**
```html
<span class="text-xl font-bold text-white">AI Bureau</span>
```

Replace with:
```html
<span class="text-xl font-bold text-white">Your Company</span>
```

**Footer column links:**

Find sections like:
```html
<h4 class="text-lg font-bold text-white mb-6">Solutions</h4>
<ul class="space-y-3">
    <li><a href="#features" class="text-gray-400 hover:text-white transition-colors duration-300">Predictive Maintenance</a></li>
    <li><a href="#features" class="text-gray-400 hover:text-white transition-colors duration-300">Autonomous Processes</a></li>
</ul>
```

Update the link text as needed (but keep the `href` values the same unless you're changing page structure).

**Copyright text:**

Find:
```html
&copy; 2025 AI Bureau Solutions. All rights reserved.
```

Update the year and company name:
```html
&copy; 2025 Your Company Name. All rights reserved.
```

---

## Modifying Tailwind CSS Classes

### What Are Tailwind Classes?

Tailwind CSS is a system of pre-made styling rules. Instead of writing custom CSS, you add class names to HTML elements. For example:

```html
<h1 class="text-5xl md:text-6xl lg:text-7xl font-bold text-gray-900">
```

Each class name controls one aspect of styling:
- `text-5xl` = font size (large)
- `md:text-6xl` = font size on medium screens (larger)
- `lg:text-7xl` = font size on large screens (largest)
- `font-bold` = bold text
- `text-gray-900` = dark gray color

### Understanding Responsive Design

Your page looks good on phones, tablets, and desktops because of **responsive classes**:

- `md:` prefix = applies on medium screens and up (tablets)
- `lg:` prefix = applies on large screens and up (desktops)
- No prefix = applies on all screen sizes

**Example:**
```html
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
```

This means:
- On phones: 1 column (`grid-cols-1`)
- On tablets: 2 columns (`md:grid-cols-2`)
- On desktops: 3 columns (`lg:grid-cols-3`)

### Common Tailwind Classes in Your Page

| Class | What It Does | Examples |
|-------|-------------|----------|
| `text-[size]` | Font size | `text-lg`, `text-2xl`, `text-5xl` |
| `text-[color]` | Text color | `text-gray-900`, `text-white`, `text-gray-600` |
| `bg-[color]` | Background color | `bg-white`, `bg-gray-50`, `bg-gray-900` |
| `p-[number]` | Padding (space inside) | `p-4`, `p-8` |
| `m-[number]` | Margin (space outside) | `m-4`, `m-8` |
| `rounded-[size]` | Rounded corners | `rounded-lg`, `rounded-xl` |
| `shadow-[size]` | Drop shadow | `shadow-md`, `shadow-xl` |
| `flex` | Flexible layout | Used with `items-center`, `justify-between` |
| `grid` | Grid layout | Used with `grid-cols-1`, `gap-8` |

### How to Change Colors

**Finding color classes:**

Most color classes follow this pattern: `[property]-[color]-[shade]`

Examples in your page:
- `text-gray-900` = dark gray text
- `bg-white` = white background
- `border-gray-200` = light gray border

**Color options available:**

Tailwind includes these color families: gray, red, blue, green, yellow, purple, pink, and more.

Shades range from 50 (very light) to 900 (very dark):
- 50 = lightest
- 100, 200, 300 = light
- 400, 500, 600 = medium
- 700, 800, 900 = dark

**Example: Changing button color**

Find:
```html
<a href="https://test.com" class="cta-button inline-flex items-center justify-center px-8 py-4 bg-gray-900 text-white font-bold text-lg rounded-lg hover:bg-gray-800 transition-all duration-300">
```

To change from dark gray to dark blue:
```html
<a href="https://test.com" class="cta-button inline-flex items-center justify-center px-8 py-4 bg-blue-900 text-white font-bold text-lg rounded-lg hover:bg-blue-800 transition-all duration-300">
```

Notice we changed:
- `bg-gray-900` → `bg-blue-900` (background color)
- `hover:bg-gray-800` → `hover:bg-blue-800` (hover state color)

### How to Change Spacing

Spacing in Tailwind uses a number system:
- `p-4` = 1 unit of padding
- `p-8` = 2 units of padding
- `p-16` = 4 units of padding

**Example: Making a card have more internal space**

Find:
```html
<div class="feature-card bg-white p-8 rounded-xl shadow-md">
```

To add more padding:
```html
<div class="feature-card bg-white p-12 rounded-xl shadow-md">
```

Changed `p-8` to `p-12` (more internal space).

### How to Change Font Sizes

Font size classes: `text-xs`, `text-sm`, `text-base`, `text-lg`, `text-xl`, `text-2xl`, `text-3xl`, `text-4xl`, `text-5xl`, `text-6xl`, `text-7xl`

**Example: Making a heading smaller**

Find:
```html
<h2 class="text-4xl md:text-5xl font-bold text-gray-900 tracking-tight">
```

To make it smaller:
```html
<h2 class="text-3xl md:text-4xl font-bold text-gray-900 tracking-tight">
```

Changed:
- `text-4xl` → `text-3xl` (on phones)
- `md:text-5xl` → `md:text-4xl` (on tablets and up)

### How to Change Shadows

Shadow classes: `shadow-sm`, `shadow-md`, `shadow-lg`, `shadow-xl`, `shadow-2xl`

**Example: Making a card have a stronger shadow**

Find:
```html
<div class="testimonial-card bg-white border border-gray-200 p-8 rounded-xl shadow-md transition-all duration-300">
```

To make it more prominent:
```html
<div class="testimonial-card bg-white border border-gray-200 p-8 rounded-xl shadow-lg transition-all duration-300">
```

Changed `shadow-md` → `shadow-lg`.

### How to Change Rounded Corners

Rounded corner classes: `rounded-none`, `rounded-sm`, `rounded-md`, `rounded-lg`, `rounded-xl`, `rounded-2xl`, `rounded-full`

**Example: Making a button have sharper corners**

Find:
```html
<a href="https://test.com" class="cta-button inline-flex items-center justify-center px-8 py-4 bg-gray-900 text-white font-bold text-lg rounded-lg hover:bg-gray-800">
```

To make corners sharper:
```html
<a href="https://test.com" class="cta-button inline-flex items-center justify-center px-8 py-4 bg-gray-900 text-white font-bold text-lg rounded-md hover:bg-gray-800">
```

Changed `rounded-lg` → `rounded-md`.

### Maintaining Responsive Design When Editing

**Important**: When you change a class, make sure to maintain the responsive prefixes.

❌ **Wrong** - breaks tablet/desktop views:
```html
<h1 class="text-5xl font-bold">  <!-- Only shows this size on all screens -->
```

✅ **Correct** - maintains responsive design:
```html
<h1 class="text-5xl md:text-6xl lg:text-7xl font-bold">  <!-- Different sizes per device -->
```

**Rule of thumb**: If you see `md:` or `lg:` prefixes in a class list, keep that pattern when editing.

---

## Fixing and Managing Links

### Understanding Links in HTML

Links are created with the `<a>` tag:

```html
<a href="destination-url" class="styling-classes">Link Text</a>
```

- `href="destination-url"` = where the link goes
- `Link Text` = what the user sees and clicks

### Types of Links on Your Page

Your page has three types of links:

1. **Internal links** - Link to other sections on the same page
2. **External links** - Link to other websites
3. **Anchor links** - Jump to specific sections

### 1. Internal Navigation Links (Section Jumps)

**Location**: Header navigation and footer

These links jump to sections on the same page using the `#` symbol:

```html
<a href="#features" class="text-gray-700 hover:text-gray-900 font-medium transition-colors duration-300">Features</a>
```

The `#features` matches the section's ID:

```html
<section id="features" class="py-24 bg-gray-50">
```

**How to verify internal links are working:**

1. Open your page in a browser
2. Click a navigation link (e.g., "Features")
3. The page should smoothly scroll to that section

**If an internal link doesn't work:**

1. Check that the `href` value (e.g., `#features`) matches a section's `id`
2. Make sure there are no typos (case-sensitive)

**Current internal links in your page:**

| Link Text | href Value | Target Section |
|-----------|-----------|-----------------|
| Features | `#features` | `<section id="features">` |
| Benefits | `#benefits` | `<section id="benefits">` |
| Testimonials | `#testimonials` | `<section id="testimonials">` |
| FAQ | `#faq` | `<section id="faq">` |
| Contact | `#contact` | `<section id="contact">` |

All these links are already correctly set up. ✓

---

### 2. External Links (To Other Websites)

**Location**: Call-to-action buttons throughout the page

These links go to external websites:

```html
<a href="https://test.com" class="cta-button inline-flex items-center justify-center px-8 py-4 bg-gray-900 text-white font-bold text-lg rounded-lg hover:bg-gray-800 transition-all duration-300">
    Get Started Today
    <i class="fas fa-arrow-right ml-3"></i>
</a>
```

**Placeholder links that need updating:**

Your page currently has placeholder links (`https://test.com`) in these locations:

1. **Hero section - "Get Started Today" button**
   - Location: Search for `Get Started Today`
   - Current: `href="https://test.com"`

2. **CTA section - "Start Your Free Consultation" button**
   - Location: Search for `Start Your Free Consultation`
   - Current: `href="https://test.com"`

**How to update external links:**

**Step 1**: Find the link you want to update
```html
<a href="https://test.com" class="cta-button...">Get Started Today</a>
```

**Step 2**: Replace `https://test.com` with your actual URL
```html
<a href="https://your-website.com/get-started" class="cta-button...">Get Started Today</a>
```

**Step 3**: Save and test in your browser

**Examples of proper URLs:**

- Your contact form: `https://your-website.com/contact`
- Your booking system: `https://calendly.com/your-name`
- Your email: `mailto:your@email.com`
- External site: `https://www.google.com`

---

### 3. Email Links

**Location**: Contact section and footer

Email links use the `mailto:` prefix:

```html
<a href="mailto:bengrauwde@hotmail.com" class="text-gray-600 hover:text-gray-900 transition-colors duration-300">
    bengrauwde@hotmail.com
</a>
```

**How to update email links:**

Find:
```html
<a href="mailto:bengrauwde@hotmail.com">bengrauwde@hotmail.com</a>
```

Replace both instances of the email address:
```html
<a href="mailto:your@email.com">your@email.com</a>
```

**Important**: Update both places:
1. In the `href="mailto:..."` part
2. In the visible text

---

### 4. Social Media Links

**Location**: Contact section and footer

Social media links are placeholders:

```html
<a href="#" class="w-10 h-10 bg-gray-900 text-white rounded-lg flex items-center justify-center hover:bg-gray-700 transition-colors duration-300">
    <i class="fab fa-linkedin-in"></i>
</a>
```

**How to update social media links:**

**Step 1**: Find the social media link you want to update
```html
<a href="#" class="w-10 h-10 bg-gray-900...">
    <i class="fab fa-linkedin-in"></i>
</a>
```

**Step 2**: Replace `#` with your social media URL
```html
<a href="https://www.linkedin.com/company/your-company" class="w-10 h-10 bg-gray-900...">
    <i class="fab fa-linkedin-in"></i>
</a>
```

**Social media URL formats:**

| Platform | URL Format | Example |
|----------|-----------|---------|
| LinkedIn | `https://www.linkedin.com/company/[company-name]` | `https://www.linkedin.com/company/ai-bureau` |
| Twitter | `https://twitter.com/[username]` | `https://twitter.com/aibureau` |
| Facebook | `https://www.facebook.com/[page-name]` | `https://www.facebook.com/aibureau` |
| YouTube | `https://www.youtube.com/@[channel-name]` | `https://www.youtube.com/@aibureau` |

---

### 5. Navigation Menu Links - Complete Reference

**Desktop Menu Location** (appears on tablets and larger):
```html
<div class="hidden md:flex items-center space-x-8">
    <a href="#features">Features</a>
    <a href="#benefits">Benefits</a>
    <a href="#testimonials">Testimonials</a>
    <a href="#faq">FAQ</a>
    <a href="#contact">Contact</a>
</div>
```

**Mobile Menu Location** (appears on phones):
```html
<div class="mobile-menu hidden md:hidden pb-4 space-y-2">
    <a href="#features">Features</a>
    <a href="#benefits">Benefits</a>
    <a href="#testimonials">Testimonials</a>
    <a href="#faq">FAQ</a>
    <a href="#contact">Contact</a>
</div>
```

**Important**: Keep these menus synchronized. If you change one, change both.

---

### 6. Footer Links - Complete Reference

**Solutions Column:**
```html
<li><a href="#features">Predictive Maintenance</a></li>
<li><a href="#features">Autonomous Processes</a></li>
<li><a href="#features">Data Analytics</a></li>
<li><a href="#benefits">Business Intelligence</a></li>
```

**Company Column:**
```html
<li><a href="#">About Us</a></li>
<li><a href="#testimonials">Testimonials</a></li>
<li><a href="#faq">FAQ</a></li>
<li><a href="#contact">Contact</a></li>
```

**Legal Column** (see next section for updating these):
```html
<li><a href="privacy.html">Privacy Policy</a></li>
<li><a href="terms.html">Terms of Service</a></li>
<li><a href="blog.html">Blog</a></li>
<li><a href="#">Security</a></li>
```

---

### Checklist: Links to Update

Use this checklist to ensure you've updated all necessary links:

- [ ] "Get Started Today" button (hero section) - change from `https://test.com`
- [ ] "Start Your Free Consultation" button (CTA section) - change from `https://test.com`
- [ ] Email address in contact section - change from `bengrauwde@hotmail.com`
- [ ] Email address in footer - change from `bengrauwde@hotmail.com`
- [ ] LinkedIn social link - change from `#`
- [ ] Twitter social link - change from `#`
- [ ] Facebook social link - change from `#`
- [ ] YouTube social link - change from `#`
- [ ] Privacy Policy link - update if you have a different URL (see next section)
- [ ] Terms of Service link - update if you have a different URL (see next section)

---

## Adding Privacy and Terms Pages

### Overview

Your landing page currently links to `privacy.html` and `terms.html` in the footer. You need to create these pages.

### Step 1: Create the Privacy Policy Page

**Step 1a**: Create a new file

1. Open your text editor
2. Click **File** → **New File**
3. Save it as `privacy.html` in the same folder as your `index.html`

**Step 1b**: Add basic HTML structure

Copy and paste this into your new `privacy.html` file:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Privacy Policy - AI Bureau Solutions">
    <title>Privacy Policy - AI Bureau Solutions</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body class="bg-white text-gray-900">
    <!-- Header Navigation (Same as index.html) -->
    <header class="sticky top-0 z-50 bg-white shadow-md">
        <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <div class="flex-shrink-0">
                    <a href="index.html" class="flex items-center space-x-2">
                        <div class="w-10 h-10 bg-gradient-to-br from-gray-900 to-gray-700 rounded-lg flex items-center justify-center">
                            <i class="fas fa-brain text-white text-lg"></i>
                        </div>
                        <span class="text-xl font-bold text-gray-900">AI Bureau</span>
                    </a>
                </div>
                <div class="hidden md:flex items-center space-x-8">
                    <a href="index.html#features" class="text-gray-700 hover:text-gray-900 font-medium transition-colors duration-300">Features</a>
                    <a href="index.html#contact" class="text-gray-700 hover:text-gray-900 font-medium transition-colors duration-300">Contact</a>
                </div>
            </div>
        </nav>
    </header>

    <!-- Main Content -->
    <section class="py-24 bg-white">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
            <h1 class="text-5xl font-bold text-gray-900 mb-8">Privacy Policy</h1>
            
            <div class="prose prose-lg max-w-none text-gray-600 space-y-6">
                <p>
                    <strong>Last Updated: January 2025</strong>
                </p>

                <h2 class="text-3xl font-bold text-gray-900 mt-8 mb-4">1. Introduction</h2>
                <p>
                    AI Bureau Solutions ("Company," "we," or "us") is committed to protecting your privacy. This Privacy Policy explains how we collect, use, disclose, and safeguard your information when you visit our website.
                </p>

                <h2 class="text-3xl font-bold text-gray-900 mt-8 mb-4">2. Information We Collect</h2>
                <p>
                    We may collect information about you in a variety of ways. The information we may collect on the site includes:
                </p>
                <ul class="list-disc list-inside space-y-2">
                    <li><strong>Personal Data:</strong> Name, email address, phone number, company name, and any other information you voluntarily provide through our contact forms.</li>
                    <li><strong>Automatic Data:</strong> Browser type, IP address, pages visited, and time spent on our website.</li>
                    <li><strong>Cookies:</strong> We use cookies to enhance your browsing experience and remember your preferences.</li>
                </ul>

                <h2 class="text-3xl font-bold text-gray-900 mt-8 mb-4">3. Use of Your Information</h2>
                <p>
                    We use the information we collect for various purposes, including:
                </p>
                <ul class="list-disc list-inside space-y-2">
                    <li>To respond to your inquiries and provide customer support</li>
                    <li>To send marketing and promotional communications (with your consent)</li>
                    <li>To analyze website usage and improve our services</li>
                    <li>To comply with legal obligations</li>
                    <li>To prevent fraudulent transactions and other illegal activities</li>
                </ul>

                <h2 class="text-3xl font-bold text-gray-900 mt-8 mb-4">4. Disclosure of Your Information</h2>
                <p>
                    We do not sell, trade, or rent your personal information to third parties. We may share information with:
                </p>
                <ul class="list-disc list-inside space-y-2">
                    <li>Service providers who assist us in operating our website and conducting our business</li>
                    <li>Legal authorities when required by law</li>
                    <li>Business partners with your consent</li>
                </ul>

                <h2 class="text-3xl font-bold text-gray-900 mt-8 mb-4">5. Data Security</h2>
                <p>
                    We implement appropriate technical and organizational measures to protect your personal information against unauthorized access, alteration, disclosure, or destruction. However, no method of transmission over the internet is 100% secure.
                </p>

                <h2 class="text-3xl font-bold text-gray-900 mt-8 mb-4">6. Your Rights</h2>
                <p>
                    Depending on your location, you may have certain rights regarding your personal information, including:
                </p>
                <ul class="list-disc list-inside space-y-2">
                    <li>The right to access your personal information</li>
                    <li>The right to correct inaccurate information</li>
                    <li>The right to request deletion of your information</li>
                    <li>The right to opt-out of marketing communications</li>
                </ul>

                <h2 class="text-3xl font-bold text-gray-900 mt-8 mb-4">7. Contact Us</h2>
                <p>
                    If you have questions about this Privacy Policy or our privacy practices, please contact us at:
                </p>
                <p>
                    <strong>Email:</strong> <a href="mailto:bengrauwde@hotmail.com" class="text-blue-600 hover:text-blue-800">bengrauwde@hotmail.com</a><br>
                    <strong>Phone:</strong> +1 (555) 123-4567
                </p>
            </div>
        </div>
    </section>

    <!-- Footer (Same as index.html) -->
    <footer class="bg-gray-900 text-gray-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
            <div class="border-t border-gray-800 pt-8">
                <p class="text-gray-400">
                    &copy; 2025 AI Bureau Solutions. All rights reserved.
                </p>
            </div>
        </div>
    </footer>
</body>
</html>
```

**Step 1c**: Customize the privacy policy

Replace the placeholder content with your actual privacy policy. Key sections to update:

1. **Email address**: Replace `bengrauwde@hotmail.com` with your email
2. **Company name**: Replace `AI Bureau Solutions` with your company name
3. **Policy content**: Replace the generic sections with your specific policies

---

### Step 2: Create the Terms of Service Page

**Step 2a**: Create a new file

1. Click **File** → **New File**
2. Save it as `terms.html` in the same folder as your `index.html`

**Step 2b**: Add basic HTML structure

Copy and paste this into your new `terms.html` file:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Terms of Service - AI Bureau Solutions">
    <title>Terms of Service - AI Bureau Solutions</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body class="bg-white text-gray-900">
    <!-- Header Navigation (Same as index.html) -->
    <header class="sticky top-0 z-50 bg-white shadow-md">
        <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <div class="flex-shrink-0">
                    <a href="index.html" class="flex items-center space-x-2">
                        <div class="w-10 h-10 bg-gradient-to-br from-gray-900 to-gray-700 rounded-lg flex items-center justify-center">
                            <i class="fas fa-brain text-white text-lg"></i>
                        </div>
                        <span class="text-xl font-bold text-gray-900">AI Bureau</span>
                    </a>
                </div>
                <div class="hidden md:flex items-center space-x-8">
                    <a href="index.html#features" class="text-gray-700 hover:text-gray-900 font-medium transition-colors duration-300">Features</a>
                    <a href="index.html#contact" class="text-gray-700 hover:text-gray-900 font-medium transition-colors duration-300">Contact</a>
                </div>
            </div>
        </nav>
    </header>

    <!-- Main Content -->
    <section class="py-24 bg-white">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
            <h1 class="text-5xl font-bold text-gray-900 mb-8">Terms of Service</h1>
            
            <div class="prose prose-lg max-w-none text-gray-600 space-y-6">
                <p>
                    <strong>Last Updated: January 2025</strong>
                </p>

                <h2 class="text-3xl font-bold text-gray-900 mt-8 mb-4">1. Agreement to Terms</h2>
                <p>
                    By accessing and using this website and our services, you accept and agree to be bound by the terms and provision of this agreement. If you do not agree to abide by the above, please do not use this service.
                </p>

                <h2 class="text-3xl font-bold text-gray-900 mt-8 mb-4">2. Use License</h2>
                <p>
                    Permission is granted to temporarily download one copy of the materials (information or software) on AI Bureau Solutions' website for personal, non-commercial transitory viewing only. This is the grant of a license, not a transfer of title, and under this license you may not:
                </p>
                <ul class="list-disc list-inside space-y-2">
                    <li>Modifying or copying the materials</li>
                    <li>Using the materials for any commercial purpose or for any public display</li>
                    <li>Attempting to decompile or reverse engineer any software contained on the website</li>
                    <li>Removing any copyright or other proprietary notations from the materials</li>
                    <li>Transferring the materials to another person or "mirroring" the materials on any other server</li>
                </ul>

                <h2 class="text-3xl font-bold text-gray-900 mt-8 mb-4">3. Disclaimer</h2>
                <p>
                    The materials on AI Bureau Solutions' website are provided on an 'as is' basis. AI Bureau Solutions makes no warranties, expressed or implied, and hereby disclaims and negates all other warranties including, without limitation, implied warranties or conditions of merchantability, fitness for a particular purpose, or non-infringement of intellectual property or other violation of rights.
                </p>

                <h2 class="text-3xl font-bold text-gray-900 mt-8 mb-4">4. Limitations</h2>
                <p>
                    In no event shall AI Bureau Solutions or its suppliers be liable for any damages (including, without limitation, damages for loss of data or profit, or due to business interruption) arising out of the use or inability to use the materials on AI Bureau Solutions' website.
                </p>

                <h2 class="text-3xl font-bold text-gray-900 mt-8 mb-4">5. Accuracy of Materials</h2>
                <p>
                    The materials appearing on AI Bureau Solutions' website could include technical, typographical, or photographic errors. AI Bureau Solutions does not warrant that any of the materials on the website are accurate, complete, or current. AI Bureau Solutions may make changes to the materials contained on the website at any time without notice.
                </p>

                <h2 class="text-3xl font-bold text-gray-900 mt-8 mb-4">6. Links</h2>
                <p>
                    AI Bureau Solutions has not reviewed all of the sites linked to its website and is not responsible for the contents of any such linked site. The inclusion of any link does not imply endorsement by AI Bureau Solutions of the site. Use of any such linked website is at the user's own risk.
                </p>

                <h2 class="text-3xl font-bold text-gray-900 mt-8 mb-4">7. Modifications</h2>
                <p>
                    AI Bureau Solutions may revise these terms of service for the website at any time without notice. By using this website, you are agreeing to be bound by the then current version of these terms of service.
                </p>

                <h2 class="text-3xl font-bold text-gray-900 mt-8 mb-4">8. Governing Law</h2>
                <p>
                    These terms and conditions are governed by and construed in accordance with the laws of the United States, and you irrevocably submit to the exclusive jurisdiction of the courts in that location.
                </p>

                <h2 class="text-3xl font-bold text-gray-900 mt-8 mb-4">9. Contact Information</h2>
                <p>
                    If you have any questions about these Terms of Service, please contact us at:
                </p>
                <p>
                    <strong>Email:</strong> <a href="mailto:bengrauwde@hotmail.com" class="text-blue-600 hover:text-blue-800">bengrauwde@hotmail.com</a><br>
                    <strong>Phone:</strong> +1 (555) 123-4567
                </p>
            </div>
        </div>
    </section>

    <!-- Footer (Same as index.html) -->
    <footer class="bg-gray-900 text-gray-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
            <div class="border-t border-gray-800 pt-8">
                <p class="text-gray-400">
                    &copy; 2025 AI Bureau Solutions. All rights reserved.
                </p>
            </div>
        </div>
    </footer>
</body>
</html>
```

**Step 2c**: Customize the terms of service

Replace placeholder content with your specific terms. Update:

1. **Email address**: Replace `bengrauwde@hotmail.com` with your email
2. **Company name**: Replace `AI Bureau Solutions` with your company name
3. **Terms content**: Replace generic sections with your specific terms

---

### Step 3: Verify Links in Your Main Page

Your `index.html` already has the correct links to these pages in the footer:

```html
<li><a href="privacy.html" class="text-gray-400 hover:text-white transition-colors duration-300">Privacy Policy</a></li>
<li><a href="terms.html" class="text-gray-400 hover:text-white transition-colors duration-300">Terms of Service</a></li>
```

These links will work once you've created the `privacy.html` and `terms.html` files.

### Step 4: Test the Links

1. Save all three files in the same folder:
   - `index.html`
   - `privacy.html`
   - `terms.html`

2. Open `index.html` in your browser

3. Scroll to the footer and click "Privacy Policy" - it should take you to `privacy.html`

4. Click "Terms of Service" - it should take you to `terms.html`

5. Click the logo in the header to return to the main page

---

### File Structure

Your project folder should look like this:

```
your-project-folder/
├── index.html          (main landing page)
├── privacy.html        (privacy policy page)
├── terms.html          (terms of service page)
└── [other files if any]
```

**Important**: All three files must be in the same folder for the links to work correctly.

---

### Updating Links if You Use a Different URL Structure

If you host your files on a web server with a different structure, you may need to update the paths.

**Example 1: Files in subfolders**

If your structure is:
```
your-website.com/
├── index.html
└── pages/
    ├── privacy.html
    └── terms.html
```

Update the links in `index.html`:
```html
<li><a href="pages/privacy.html">Privacy Policy</a></li>
<li><a href="pages/terms.html">Terms of Service</a></li>
```

**Example 2: Files at different domains**

If your privacy policy is hosted elsewhere:
```html
<li><a href="https://your-website.com/privacy-policy/">Privacy Policy</a></li>
<li><a href="https://your-website.com/terms/">Terms of Service</a></li>
```

---

### Customizing Policy Content

Both `privacy.html` and `terms.html` contain placeholder content. You should customize these with your actual policies. Here are key things to update:

**In privacy.html:**
- [ ] Update "Last Updated" date
- [ ] Update company name throughout
- [ ] Add your actual data collection practices
- [ ] Add your actual data usage policies
- [ ] Update contact email
- [ ] Add GDPR/CCPA compliance statements if applicable

**In terms.html:**
- [ ] Update "Last Updated" date
- [ ] Update company name throughout
- [ ] Add your specific terms and conditions
- [ ] Update governing law to your jurisdiction
- [ ] Update contact email
- [ ] Add liability limitations specific to your services

---

## Troubleshooting Common Issues

### Issue 1: Links Not Working

**Problem**: You click a link but nothing happens or you get a 404 error.

**Solutions:**

1. **Check the href value matches the target ID**
   ```html
   <!-- Link -->
   <a href="#features">Features</a>
   
   <!-- Must match this -->
   <section id="features">
   ```

2. **Check for typos** (links are case-sensitive)
   - ❌ `href="#Features"` won't match `id="features"`
   - ✅ `href="#features"` matches `id="features"`

3. **Verify file names for external pages**
   - File name: `privacy.html`
   - Link: `href="privacy.html"` ✓
   - Link: `href="privacy_policy.html"` ✗ (wrong name)

4. **Test in browser**
   - Open the file directly (not through a server)
   - Some features may not work locally; use a local server if needed

---

### Issue 2: Text Not Updating

**Problem**: You edited text in the HTML but it doesn't show up on the page.

**Solutions:**

1. **Save the file** - Press Ctrl+S (Windows) or Cmd+S (Mac)

2. **Refresh the browser** - Press F5 or Ctrl+R (Windows) or Cmd+R (Mac)

3. **Hard refresh** - Press Ctrl+Shift+R (Windows) or Cmd+Shift+R (Mac) to clear browser cache

4. **Check you edited the right section**
   - Use Ctrl+F to search for the text you want to change
   - Make sure you're editing between the correct HTML tags

5. **Verify you didn't accidentally delete HTML tags**
   - ✅ `<p>New text here</p>`
   - ❌ `New text here` (missing `<p>` tags)

---

### Issue 3: Styling Looks Wrong

**Problem**: Colors, sizes, or spacing changed unexpectedly.

**Solutions:**

1. **Check for typos in class names**
   - ❌ `class="text-gra-900"` (typo)
   - ✅ `class="text-gray-900"` (correct)

2. **Verify you didn't remove Tailwind classes**
   - ❌ `<h1 class="">` (empty class)
   - ✅ `<h1 class="text-5xl font-bold">` (has classes)

3. **Check responsive prefixes**
   - If you see `md:` or `lg:` prefixes, maintain them
   - ❌ `<div class="grid-cols-3">` (always 3 columns)
   - ✅ `<div class="grid-cols-1 md:grid-cols-3">` (responsive)

4. **Verify color class format**
   - ❌ `bg-gray` (incomplete)
   - ✅ `bg-gray-900` (complete with shade)

---

### Issue 4: Mobile Menu Not Working

**Problem**: The mobile menu button doesn't open/close on phones.

**Solutions:**

1. **Check JavaScript is intact**
   - Scroll to the bottom of `index.html`
   - Verify the `<script>` section is present and complete
   - Don't delete or modify the JavaScript code

2. **Verify mobile menu classes**
   - The button should have: `class="mobile-menu-button"`
   - The menu should have: `class="mobile-menu"`

3. **Test on actual mobile device**
   - Browser developer tools might not perfectly simulate mobile behavior
   - Test on a real phone when possible

---

### Issue 5: Form Not Submitting

**Problem**: Contact form doesn't send messages.

**Solutions:**

1. **Add form action**
   - The current form is a placeholder
   - You need to add a backend service or form handler
   - Options: Formspree, Netlify Forms, EmailJS, or custom backend

2. **Using Formspree (easiest option)**
   
   Find the form in the Contact section:
   ```html
   <form class="space-y-6">
   ```
   
   Change to:
   ```html
   <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST" class="space-y-6">
   ```
   
   Steps:
   1. Go to [formspree.io](https://formspree.io)
   2. Sign up for free
   3. Create a new form and get your form ID
   4. Replace `YOUR_FORM_ID` with your actual ID

3. **Ensure form inputs have correct names**
   ```html
   <input type="text" name="name" required>
   <input type="email" name="email" required>
   <textarea name="message" required></textarea>
   ```

---

### Issue 6: Icons Not Showing

**Problem**: You see boxes or broken symbols instead of icons.

**Solutions:**

1. **Check Font Awesome is loading**
   - Look at the top of your HTML file
   - Verify this line exists in the `<head>`:
   ```html
   <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
   ```

2. **Check icon class names are correct**
   - ❌ `<i class="fas fa-checl">` (typo)
   - ✅ `<i class="fas fa-check">` (correct)

3. **Verify you're using Font Awesome icons**
   - Correct format: `<i class="fas fa-icon-name"></i>`
   - Find icon names at [fontawesome.com](https://fontawesome.com)

---

### Issue 7: Page Looks Different on Mobile

**Problem**: Layout breaks or looks wrong on phones/tablets.

**Solutions:**

1. **Check responsive classes are intact**
   - Look for `md:` and `lg:` prefixes
   - These control how the page looks at different sizes

2. **Test with browser developer tools**
   - Open your browser
   - Press F12 to open Developer Tools
   - Click the device icon (mobile view toggle)
   - Test different screen sizes

3. **Common responsive issues**
   - Missing `md:` or `lg:` prefixes
   - Changed grid column classes
   - Modified padding/margin values

---

### Issue 8: Colors Look Different Than Expected

**Problem**: You changed a color class but it looks wrong.

**Solutions:**

1. **Verify Tailwind color naming**
   
   Tailwind uses this format: `[property]-[color]-[shade]`
   
   Examples:
   - `text-gray-900` = very dark gray text
   - `text-gray-100` = very light gray text
   - `bg-blue-500` = medium blue background

2. **Check color availability**
   
   Available colors: gray, red, orange, yellow, green, blue, indigo, purple, pink, and more
   
   ❌ `text-dark` (not available)
   ✅ `text-gray-900` (correct)

3. **Test color combinations**
   
   Make sure text color contrasts with background:
   - ❌ Light text on light background (hard to read)
   - ✅ Dark text on light background (easy to read)

---

## Best Practices

### 1. Always Keep Backups

Before making major changes:
1. Copy your `index.html` file
2. Save it as `index-backup.html`
3. If something goes wrong, you can restore from the backup

### 2. Make One Change at a Time

- Change one thing
- Save and test
- Then make the next change

This way, if something breaks, you know exactly what caused it.

### 3. Use Version Control (Optional but Recommended)

For more advanced users, consider using Git:
1. Initialize a Git repository
2. Commit changes regularly
3. Easy to revert if needed

### 4. Test Across Devices

Always test your changes on:
- Desktop browser
- Tablet
- Mobile phone
- Different browsers (Chrome, Firefox, Safari)

### 5. Keep External Links Updated

Maintain a spreadsheet of all external links and their purposes:

| Link Location | Current URL | Purpose | Last Updated |
|---------------|-------------|---------|--------------|
| Get Started Button | https://... | CTA form | MM/DD/YYYY |
| LinkedIn | https://... | Social | MM/DD/YYYY |
| Email | your@email.com | Contact | MM/DD/YYYY |

### 6. Regularly Update Content

- Update testimonials quarterly
- Refresh statistics annually
- Review and update FAQ based on customer questions
- Keep "Last Updated" dates current

### 7. Test Forms Before Going Live

If you add a contact form:
1. Fill it out completely
2. Submit it
3. Verify you receive the email
4. Test from different devices

### 8. Maintain Consistency

- Use the same colors throughout
- Keep font sizes proportional
- Maintain consistent spacing
- Use the same style for similar elements

### 9. Document Your Changes

Keep a log of what you changed and when:

```
Date: 01/15/2025
Changed: Hero section headline
From: "Future-Proof Your Ops"
To: "Transform Your Business"
Reason: Better brand alignment

Date: 01/16/2025
Updated: Contact email
From: old@email.com
To: new@email.com
```

### 10. Optimize Before Launch

Before making your site live:
- [ ] Test all links
- [ ] Verify all email addresses
- [ ] Check forms work
- [ ] Test on mobile
- [ ] Verify images load
- [ ] Check spelling and grammar
- [ ] Update meta descriptions
- [ ] Remove placeholder content

---

## Quick Reference Guide

### Common Tasks

**Update a heading:**
```html
<!-- Find this -->
<h2 class="text-4xl font-bold text-gray-900">Old Heading</h2>

<!-- Change to -->
<h2 class="text-4xl font-bold text-gray-900">New Heading</h2>
```

**Update a button link:**
```html
<!-- Find this -->
<a href="https://test.com" class="cta-button...">Button Text</a>

<!-- Change to -->
<a href="https://your-url.com" class="cta-button...">New Button Text</a>
```

**Change a color:**
```html
<!-- Find this -->
<div class="bg-gray-900">

<!-- Change to -->
<div class="bg-blue-900">
```

**Change font size:**
```html
<!-- Find this -->
<p class="text-lg">

<!-- Change to -->
<p class="text-xl">
```

**Add a new bullet point:**
```html
<!-- Find this -->
<ul class="space-y-2 text-gray-600">
    <li class="flex items-start">
        <i class="fas fa-check text-gray-900 mr-3 mt-1 flex-shrink-0"></i>
        <span>Existing point</span>
    </li>
</ul>

<!-- Add this -->
<ul class="space-y-2 text-gray-600">
    <li class="flex items-start">
        <i class="fas fa-check text-gray-900 mr-3 mt-1 flex-shrink-0"></i>
        <span>Existing point</span>
    </li>
    <li class="flex items-start">
        <i class="fas fa-check text-gray-900 mr-3 mt-1 flex-shrink-0"></i>
        <span>New point</span>
    </li>
</ul>
```

---

## Additional Resources

### Learning Resources

- **HTML Basics**: [MDN Web Docs - HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
- **Tailwind CSS**: [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- **Font Awesome Icons**: [Font Awesome Icons](https://fontawesome.com/icons)
- **Color Tools**: [Tailwind Color Palette](https://tailwindcss.com/docs/customizing-colors)

### Tools

- **Text Editor**: [Visual Studio Code](https://code.visualstudio.com/) (Free)
- **Browser DevTools**: Press F12 in your browser
- **Color Picker**: [Coolors.co](https://coolors.co)
- **Image Optimization**: [TinyPNG](https://tinypng.com)

### Getting Help

1. **Check this guide** - Most issues are covered in the Troubleshooting section
2. **Search Stack Overflow** - Many HTML/CSS questions already have answers
3. **Check Tailwind docs** - Official documentation for class names
4. **Validate HTML** - Use [W3C Validator](https://validator.w3.org/)

---

## Summary

You now have a comprehensive guide to maintain and customize your AI Bureau Solutions landing page. Here's what you learned:

✅ How to find and update text content  
✅ How to modify Tailwind CSS classes without breaking responsive design  
✅ How to identify and fix all types of links  
✅ How to create and link privacy and terms pages  
✅ How to troubleshoot common problems  
✅ Best practices for maintaining your page  

**Next Steps:**

1. Update all placeholder links (especially `https://test.com`)
2. Replace contact information with your details
3. Create and customize your privacy and terms pages
4. Test everything on multiple devices
5. Keep this guide handy for future updates

Good luck with your landing page! If you need help, refer back to the relevant section in this guide.