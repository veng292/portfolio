# Portfolio Build Instructions — Vengadesh P

A complete reference for building a professional, human-crafted single-page portfolio website. Follow every section in order. Do not skip any step.

---

## 1. Project overview

**Owner:** Vengadesh P  
**Role:** B.Tech CSBS student, Backend & MERN Stack Developer  
**Goal:** A clean, professional, light-theme personal portfolio that looks hand-crafted — not AI-generated. Recruiters and technical peers are the primary audience. The page must load fast, work on mobile, and communicate competence and focus within the first 5 seconds.

**Live links to wire up:**
- GitHub: https://github.com/veng292
- Email: pvengadesh772@gmail.com
- Phone: +91 82708 59094

---

## 2. File structure

```
portfolio/
├── index.html
├── style.css
├── script.js
├── assets/
│   ├── profile.jpg          (your professional photo — see section 4)
│   └── favicon.ico
```

Keep it a single HTML file if deploying to GitHub Pages. No build tools required unless you choose React (see section 6).

---

## 3. Design system

### 3.1 Color palette

Use this exact palette. Do not substitute.

| Token           | Hex       | Use |
|-----------------|-----------|-----|
| `--white`       | `#FFFFFF` | Page background, card backgrounds |
| `--off-white`   | `#F8F9FA` | Section alternating backgrounds |
| `--text-primary`| `#111827` | Headings, body text |
| `--text-muted`  | `#6B7280` | Subtitles, dates, captions |
| `--accent`      | `#0EA5E9` | Links, active states, highlights (sky blue) |
| `--accent-dark` | `#0369A1` | Hover states on accent elements |
| `--border`      | `#E5E7EB` | Card borders, dividers |
| `--tag-bg`      | `#EFF6FF` | Skill tag backgrounds |
| `--tag-text`    | `#1D4ED8` | Skill tag labels |

No dark backgrounds anywhere. No colored section backgrounds except `--off-white` alternates.

### 3.2 Typography

Load from Google Fonts:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=Playfair+Display:wght@600&display=swap" rel="stylesheet">
```

| Role        | Font              | Weight | Size |
|-------------|-------------------|--------|------|
| Name / H1   | Playfair Display  | 600    | 42px desktop / 28px mobile |
| H2 sections | Inter             | 600    | 22px |
| H3 titles   | Inter             | 500    | 16px |
| Body text   | Inter             | 400    | 15px, line-height 1.75 |
| Tags / labels | Inter           | 500    | 12px |
| Nav links   | Inter             | 500    | 14px |

Letter-spacing: `-0.01em` on headings. `0` on body. Do not use font sizes below 12px anywhere.

### 3.3 Spacing scale

Use this scale consistently. Derive all margins and paddings from it.

```
4px   — micro gap (icon to label)
8px   — tight gap (tag to tag)
12px  — component internal padding
16px  — card padding
24px  — between card elements
32px  — between section items
48px  — section top/bottom padding (mobile)
80px  — section top/bottom padding (desktop)
```

### 3.4 Border radius

| Element      | Radius |
|--------------|--------|
| Cards        | 12px   |
| Tags / pills | 6px    |
| Buttons      | 8px    |
| Avatar photo | 50% (circle) |

### 3.5 Shadows

Use sparingly — only on cards and the sticky nav.

```css
--shadow-sm: 0 1px 3px rgba(0,0,0,0.08), 0 1px 2px rgba(0,0,0,0.05);
--shadow-md: 0 4px 12px rgba(0,0,0,0.08);
```

No glow effects. No colored shadows.

---

## 4. Profile photo

### Requirements
- Dimensions: minimum 400x400px, square crop
- Format: JPEG, compressed to under 150 KB
- Background: plain white or light gray — no busy backgrounds
- Dress: solid-color formal shirt (light blue or white recommended)
- Expression: neutral, professional, slight smile
- Lighting: natural light from one side, no harsh shadows on face

### Where to get a good photo
1. Use a recent photo taken outdoors in daylight (best option)
2. Use a phone in portrait mode against a plain wall
3. If no good photo is available: use https://pfpmaker.com to remove background and add a clean backdrop
4. Do not use illustrations, avatars, or cartoons — real photo only

### Save it as
```
assets/profile.jpg
```

---

## 5. Logo and brand assets for tech stack

Use official SVG logos from https://devicons.github.io/devicon/ or https://simpleicons.org/

Download and reference these logos for the skills section (save them inline as SVG or use CDN):

| Technology     | Simple Icons slug  |
|----------------|--------------------|
| C              | `c`                |
| C++            | `cplusplus`        |
| Python         | `python`           |
| JavaScript     | `javascript`       |
| HTML5          | `html5`            |
| CSS3           | `css3`             |
| React          | `react`            |
| Node.js        | `nodedotjs`        |
| MongoDB        | `mongodb`          |
| MySQL          | `mysql`            |
| Spring Boot    | `springboot`       |
| GitHub         | `github`           |
| VS Code        | `visualstudiocode` |

Use the CDN from Simple Icons:
```html
<img src="https://cdn.simpleicons.org/python" alt="Python" width="28" height="28">
```

For GitHub, LinkedIn, and email icons in the contact bar — use Devicon or Simple Icons SVG directly, not emoji or Unicode symbols.

---

## 6. HTML structure (index.html)

Build the page in this exact order, top to bottom. Each section is described with content and layout guidance.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Vengadesh P — Developer Portfolio</title>
  <meta name="description" content="Portfolio of Vengadesh P, B.Tech CSBS student and backend developer specialising in Spring Boot and the MERN stack.">
  <link rel="icon" href="assets/favicon.ico">
  <!-- Google Fonts -->
  <!-- style.css -->
</head>
<body>
  <!-- NAV -->
  <!-- HERO -->
  <!-- ABOUT -->
  <!-- EDUCATION -->
  <!-- EXPERIENCE -->
  <!-- PROJECTS -->
  <!-- SKILLS -->
  <!-- ACHIEVEMENTS -->
  <!-- CERTIFICATIONS -->
  <!-- CONTACT -->
  <!-- FOOTER -->
  <!-- script.js -->
</body>
</html>
```

---

## 7. Section-by-section build guide

### 7.1 Navigation bar

**Layout:** Fixed to top. Full-width. White background. Bottom border `1px solid var(--border)`. Box shadow `--shadow-sm` on scroll.

**Left:** Your name — `Vengadesh P` — in Inter 500 16px, color `--text-primary`.

**Right:** Links — About, Education, Experience, Projects, Skills, Achievements, Certifications, Contact

**Mobile:** Hamburger menu icon (three horizontal lines, 24px). On click, slide down a full-width dropdown with the same links stacked vertically, padding 16px each.

**Active link indicator:** Thin 2px underline in `--accent` color on the currently visible section's link. Update this on scroll using IntersectionObserver (see section 10).

**No logo image in nav** — name as text is cleaner.

---

### 7.2 Hero section

**Layout:** Two columns on desktop (60/40 split). Single column on mobile (photo centered above text).

**Left column (text):**

```
Eyebrow label (small caps, --text-muted, 13px, letter-spacing 0.08em):
  COMPUTER SCIENCE & BUSINESS SYSTEMS

Name (Playfair Display 600, 42px):
  Vengadesh P

Tagline (Inter 400, 18px, --text-muted, max-width 480px):
  Backend developer and MERN stack engineer building real-world systems —
  from drowsiness detection to vehicle-to-vehicle communication.

Contact row (flex, gap 16px, margin-top 24px):
  [phone icon] 82708 59094
  [mail icon]  pvengadesh772@gmail.com
  [github icon] GitHub  → links to https://github.com/veng292
  [linkedin icon] LinkedIn

CTA buttons (margin-top 32px):
  Primary button: "View Projects"  → scrolls to #projects
  Secondary button (outline): "Download Resume"  → link to PDF
```

**Right column (photo):**
- Circular profile photo, 220px diameter on desktop, 160px on mobile
- Thin 3px solid ring in `--accent` color around the circle (use outline or box-shadow)
- Add a subtle floating card below the photo — a small badge:
  ```
  [trophy icon]  L&T Techgium 2026 Finalist
  ```
  White card, shadow-sm, border-radius 8px, font-size 13px. Position it slightly overlapping the bottom of the photo circle.

**Section background:** White. No pattern, no gradient.

---

### 7.3 About section

**Background:** `--off-white`

**Layout:** Single centered column, max-width 680px.

**Section heading style (apply to all sections):**
```
Small label above heading (--text-muted, 13px, uppercase, letter-spacing 0.1em):
  ABOUT ME

Heading (Inter 600, 22px):
  Who I am

Divider: 40px wide, 3px tall, background --accent, margin-top 8px margin-bottom 24px
```

**Content:**
```
Paragraph 1:
  I am a third-year B.Tech student in Computer Science and Business Systems at Sri Eshwar
  College of Engineering, currently in my fifth semester. My work spans backend systems,
  full-stack web applications, and IoT-based communication projects.

Paragraph 2:
  I interned at RampeX Technologies in 2025, where I built and integrated RESTful APIs
  using Spring Boot. I was a finalist at L&T Techgium 2026, competing with over 62,500
  students from 500+ institutions across India with a LoRa-based vehicle communication
  system.

Paragraph 3:
  Outside of coursework and projects, I solve problems on LeetCode, HackerRank, and
  SkillRack daily to keep my algorithmic thinking sharp.
```

Three small stat cards below the text (flex row, gap 24px, wrap on mobile):

| Stat | Label |
|------|-------|
| 6.62 | CGPA (5th Sem) |
| 4    | Projects built |
| 800+ | Problems solved |

Each card: white background, border, border-radius 12px, padding 20px 24px, centered text. Number in Inter 600 28px `--accent`. Label in Inter 400 13px `--text-muted`.

---

### 7.4 Education section

**Background:** White

**Layout:** Vertical timeline. Center line for desktop (optional), left-aligned line for mobile.

**Timeline line:** 2px solid `--border`, runs vertically from top to bottom of section content.

**Each education entry (3 total):**

```
Timeline dot: 10px circle, background --accent, centered on the vertical line.

Card (white, shadow-sm, border-radius 12px, padding 20px 24px, margin-left 24px):
  
  Institution name  (Inter 500 16px, --text-primary)
  Degree / Board    (Inter 400 14px, --text-muted)
  Result            (Inter 600 14px, --accent)
  Date range        (Inter 400 13px, --text-muted, float right or below)
```

**Entries:**

1. Sri Eshwar College of Engineering — B.Tech, Computer Science and Business Systems (CSBS) — CGPA: 6.62 — 2023–2027 — badge: "Current"
2. PMG Matriculation Hr.Sec School — HSC — 74% — 2021–2023
3. PMG Matriculation Hr.Sec School — SSLC — Pass — 2020–2021

**"Current" badge:** Small pill, background `--tag-bg`, color `--tag-text`, font-size 11px, padding 2px 10px.

---

### 7.5 Experience section

**Background:** `--off-white`

**Single entry (one internship):**

```
Card (white, shadow-sm, border-radius 12px, padding 28px):

  Top row:
    Left:  "Spring Boot Intern"  (Inter 600 17px)
           "RampeX Technologies"  (Inter 500 14px, --accent)
    Right: "2025"  (Inter 400 13px, --text-muted)
           Badge: "Internship" (pill, --tag-bg, --tag-text)

  Divider line

  Description:
    - Completed a Spring Boot internship focused on building and integrating RESTful APIs.
    - Gained practical understanding of dependency injection, layered architecture, and backend best practices.
    - Developed and tested real-time application modules using Spring Boot frameworks.
    - The college-organised internship strengthened overall backend development skills.

  Tag row (tech used):
    [Spring Boot] [REST API] [Java] [Dependency Injection] [Layered Architecture]
```

Each bullet: 15px Inter 400, `--text-primary`, line-height 1.75. Lead each bullet with a thin right-pointing chevron (›) in `--accent`.

---

### 7.6 Projects section

**Background:** White

**Layout:** Grid — 2 columns on desktop, 1 column on mobile. Gap 24px.

**Each project card:**

```
Card (white, border 1px solid --border, border-radius 12px, padding 24px):
  
  Top row:
    Left:  Project title (Inter 600 16px)
    Right: Year (Inter 400 13px, --text-muted)

  Tech stack row (flex, gap 6px, flex-wrap, margin 10px 0):
    Small tags per technology used

  Description (Inter 400 14px, --text-muted, line-height 1.7):
    2–3 sentences max. Clear and direct.

  Bottom row (margin-top 16px):
    If GitHub link available: "[github icon] View Code" — styled as a text link, --accent
```

On hover: card `border-color` transitions to `--accent`. `transition: border-color 0.2s ease`.

**Three project entries:**

**1. Driver Drowsiness Detection System (2025)**
Tags: `MERN Stack` `Computer Vision` `Real-time Alerts` `MongoDB` `Node.js`
Description: A MERN stack application that analyses real-time video to detect driver fatigue and closed-eye patterns. Triggers instant visual and audio alerts when drowsiness is identified, reducing the risk of fatigue-related road accidents.

**2. Multi-Vendor Marketplace (2024)**
Tags: `Spring Boot` `Java` `MySQL` `REST API` `Admin Panel`
Description: A Spring Boot platform where multiple vendors register and manage products independently. Includes separate dashboards for vendors, customers, and administrators, with real-time order tracking and product approval workflows.

**3. Vehicle-to-Vehicle Communication System (2024)**
Tags: `LoRa` `ESP32` `GPS` `IMU` `IoT` `C++`
Description: A LoRa-based V2V system using ESP32, GPS, and IMU sensors for long-range, internet-independent accident and hazard alert transmission. Built for the L&T Techgium 2026 competition. Low-cost, real-time, and designed to improve road safety.

---

### 7.7 Skills section

**Background:** `--off-white`

**Layout:** Two subsections side by side on desktop, stacked on mobile.

**Left — Programming languages (with logos):**

Use a 3-column icon grid. Each cell:
```
[tech logo SVG, 32px]
[tech name, Inter 500 13px, --text-muted, text-align center, margin-top 6px]
```

Technologies to show with logos:
C, C++, Python, JavaScript, HTML5, CSS3

**Right — Frameworks and tools (with logos):**

Same grid layout:
React, Node.js, Spring Boot, MongoDB, MySQL, GitHub, VS Code

**Below both columns — Core concepts (text tags only):**
```
[Object-Oriented Programming]  [Data Structures]  [Algorithms]
[REST API Design]  [Layered Architecture]  [Backend Development]
```

Each tag: `--tag-bg` background, `--tag-text` color, border-radius 6px, padding 6px 14px, font-size 13px Inter 500.

Logo sourcing: `https://cdn.simpleicons.org/{slug}` — see the full slug table in section 5.

---

### 7.8 Achievements section

**Background:** White

**Layout:** Stacked cards, full-width.

**Each achievement card:**

```
Card (white, border-left: 3px solid --accent, padding 20px 24px, border-radius 0 8px 8px 0, background --off-white):

  Row:
    Icon (left, 22px, --accent)
    Content (right):
      Title (Inter 600 15px)
      Description (Inter 400 14px, --text-muted, margin-top 4px)
```

**Four entries:**

1. Icon: trophy
   Title: L&T Techgium 2026 Finalist
   Description: Competed against 62,500+ students from 500+ institutions across India with a LoRa-based vehicle-to-vehicle communication system.

2. Icon: code
   Title: LeetCode — Contest Rating 1500+
   Description: Active participant in LeetCode weekly and biweekly contests with a rating above 1500.

3. Icon: check-circle
   Title: HackerRank — 250+ problems solved
   Description: Proficient in data structures, algorithms, and SQL problem sets on HackerRank.

4. Icon: layers (or stack)
   Title: SkillRack — 550+ problems solved
   Description: One of the consistent high-performers on the SkillRack platform with daily practice.

Use Heroicons or Lucide SVG icons. Recommended source: https://heroicons.com (use outline variants, 24px).

---

### 7.9 Certifications section

**Background:** `--off-white`

**Layout:** 2-column grid on desktop, 1 column on mobile.

**Each certification card:**

```
Card (white, shadow-sm, border-radius 12px, padding 20px 24px):

  Top row:
    [Issuer logo — see below]
    Year badge (--tag-bg, --tag-text, font 12px, float right)

  Title (Inter 600 15px, margin-top 12px)
  Issuer (Inter 400 13px, --text-muted)
```

**Issuer logos (use official logos):**
- Infosys: https://cdn.simpleicons.org/infosys — hex `#007CC3`
- Udemy: https://cdn.simpleicons.org/udemy — hex `#EC5252`
- SkillRack: no Simple Icons entry — use text "SkillRack" in Inter 600 --accent instead
- HackerRank: https://cdn.simpleicons.org/hackerrank — hex `#00EA64`

**Four entries:**

| Title | Issuer | Year |
|-------|--------|------|
| Learn React | Infosys | 2025 |
| Machine Learning A-Z: AI, Python | Udemy | 2025 |
| SQL Basics (Standard) | SkillRack | 2024 |
| SQL Basics | HackerRank | 2025 |

---

### 7.10 Contact section

**Background:** White

**Layout:** Centered, max-width 560px, text-align center.

```
Section label: CONTACT
Heading: Get in touch

Short paragraph (--text-muted, 15px):
  Open to internship opportunities, collaborative projects, and full-time roles after graduation.
  Feel free to reach out.

Three contact tiles (flex row, centered, gap 16px, wrap on mobile):

  Each tile (white, border, border-radius 12px, padding 20px, min-width 150px):
    [icon, 24px, --accent]
    [label, 13px, --text-muted, margin-top 6px]
    [value/link, 14px, --text-primary or --accent for links]

Tile 1: phone icon, "Phone", 82708 59094
Tile 2: mail icon, "Email", pvengadesh772@gmail.com (href="mailto:...")
Tile 3: github icon, "GitHub", github.com/veng292 (href="https://github.com/veng292", target="_blank")
```

---

### 7.11 Footer

**Background:** `#111827` (dark, this is the only dark surface on the page)

**Content (centered, padding 32px):**

```
Name: Vengadesh P  (Inter 500 14px, color #fff)
Tagline: B.Tech CSBS · Sri Eshwar College of Engineering  (Inter 400 13px, color #9CA3AF)
Copyright line: © 2025 Vengadesh P. All rights reserved.  (Inter 400 12px, color #6B7280)
```

No social icons repeated in footer — keep it minimal.

---

## 8. CSS architecture (style.css)

Structure your CSS in this order:

```css
/* 1. CSS custom properties (design tokens) */
:root { ... }

/* 2. Reset and base */
*, *::before, *::after { box-sizing: border-box; }
body { ... }
img { ... }

/* 3. Typography utilities */
.eyebrow { ... }
.section-heading { ... }
.section-divider { ... }

/* 4. Layout utilities */
.container { max-width: 1100px; margin: 0 auto; padding: 0 24px; }
.section { padding: 80px 0; }
.section--alt { background: var(--off-white); }

/* 5. Navigation */
.nav { ... }

/* 6. Hero */
.hero { ... }

/* 7. Each section in order */

/* 8. Responsive breakpoints (mobile-first) */
@media (min-width: 768px) { ... }
@media (min-width: 1024px) { ... }
```

Mobile-first means: write base styles for mobile, then add desktop overrides in `min-width` breakpoints. This is the correct order.

---

## 9. Responsive breakpoints

| Breakpoint | Width    | Layout changes |
|------------|----------|----------------|
| Mobile     | < 768px  | Single column everywhere. Nav collapses to hamburger. Photo centered above hero text. Stats stacked. |
| Tablet     | 768–1023px | 2-column projects grid. Hero still single column or 50/50. |
| Desktop    | 1024px+  | Full 2-column hero. 3-column skill icons. Side-by-side education timeline columns. |

Hamburger menu: on mobile, hide nav links. Show a `<button>` with three horizontal bars. On click, toggle a `.nav-open` class that slides down the mobile menu. Close it on outside click or Escape key.

---

## 10. JavaScript (script.js)

Keep JavaScript minimal. Three functions only:

### 10.1 Sticky nav shadow on scroll
```javascript
window.addEventListener('scroll', () => {
  const nav = document.querySelector('.nav');
  nav.classList.toggle('nav--scrolled', window.scrollY > 10);
});
```

### 10.2 Active nav link using IntersectionObserver
```javascript
const sections = document.querySelectorAll('section[id]');
const navLinks = document.querySelectorAll('.nav-link');

const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      navLinks.forEach(link => {
        link.classList.toggle('active', link.getAttribute('href') === '#' + entry.target.id);
      });
    }
  });
}, { rootMargin: '-40% 0px -55% 0px' });

sections.forEach(section => observer.observe(section));
```

### 10.3 Hamburger toggle
```javascript
const hamburger = document.querySelector('.nav-hamburger');
const mobileMenu = document.querySelector('.nav-mobile');

hamburger.addEventListener('click', () => {
  mobileMenu.classList.toggle('open');
  hamburger.setAttribute('aria-expanded', mobileMenu.classList.contains('open'));
});

document.addEventListener('click', (e) => {
  if (!e.target.closest('.nav')) {
    mobileMenu.classList.remove('open');
  }
});
```

No jQuery. No animation libraries. No scroll-triggered entrance animations — they feel AI-generated. Transition on hover states only.

---

## 11. Performance requirements

- Total page weight: under 500 KB (excluding profile photo)
- Profile photo: under 150 KB (compress at https://squoosh.app)
- Google Fonts: use `display=swap` parameter (already in the link tag above)
- No unused CSS. No unused JavaScript.
- All images must have descriptive `alt` attributes
- Logo SVGs from CDN load asynchronously — add `loading="lazy"` to all `<img>` tags except the profile photo (that one gets `loading="eager"`)

---

## 12. Accessibility requirements

- All interactive elements (nav links, buttons, cards with links) must have visible `:focus` outlines. Use:
  ```css
  :focus-visible { outline: 2px solid var(--accent); outline-offset: 3px; }
  ```
- Contrast ratios: all body text must pass WCAG AA (4.5:1 minimum). `--text-muted` (#6B7280) on white passes at 4.6:1 — do not use a lighter gray.
- Navigation landmark: wrap nav in `<nav aria-label="Main navigation">`
- Hamburger button: `aria-label="Open menu"` and `aria-expanded` toggled by JS (see above)
- Tech stack logos: `alt="Python"` etc. — not `alt="logo"` or `alt=""`
- Section headings must follow logical order: one `<h1>` (name in hero), `<h2>` for each section, `<h3>` within sections.

---

## 13. Deployment (GitHub Pages)

1. Create a new repository: `github.com/veng292/portfolio` (public)
2. Push all files to the `main` branch
3. Go to Settings > Pages > Source: Deploy from branch > branch: `main` > folder: `/ (root)`
4. Your site will be live at: `https://veng292.github.io/portfolio/`
5. Add this URL to your GitHub profile and LinkedIn bio

Custom domain (optional): Buy `vengadesh.dev` or `vengadeshp.com` from Namecheap (~$10/year) and point it to GitHub Pages via CNAME.

---

## 14. What not to do

- Do not use Bootstrap or Tailwind — write your own CSS. It keeps the codebase small and the design distinctive.
- Do not use AOS.js or other scroll animation libraries — they make portfolios look templated.
- Do not use placeholder images or Lorem Ipsum text anywhere.
- Do not use emojis anywhere on the page.
- Do not add a "dark mode toggle" — it adds complexity without value for a portfolio.
- Do not write "Welcome to my portfolio" anywhere — it wastes the user's attention.
- Do not use a hero background gradient or pattern — keep it white and clean.
- Do not add a "Skills" percentage chart (pie chart, radar chart) — they look like filler and percentages of skill are meaningless.

---

## 15. Quality checklist before publishing

Run through every item below before sharing the URL with anyone.

- [ ] Profile photo is real, professional, well-lit, under 150 KB
- [ ] Name is spelled correctly everywhere: Vengadesh P
- [ ] Phone number is correct: 82708 59094
- [ ] Email link opens mail client: pvengadesh772@gmail.com
- [ ] GitHub link opens https://github.com/veng292 in a new tab
- [ ] All three project descriptions are complete and accurate
- [ ] All four certifications are listed with correct issuers and years
- [ ] L&T Techgium achievement year is 2026
- [ ] Navigation links scroll to the correct sections
- [ ] Active nav link updates on scroll
- [ ] Hamburger menu works on mobile
- [ ] Page loads in under 3 seconds on a mobile connection (test with PageSpeed Insights)
- [ ] No horizontal scroll on mobile
- [ ] Tested on Chrome, Firefox, and Safari
- [ ] Tested on iPhone and Android screen sizes (use Chrome DevTools)
- [ ] All images have alt text
- [ ] No console errors in browser DevTools
- [ ] Meta description is filled in (for search engines and link previews)

---

## 16. Tools and references

| Task | Tool | URL |
|------|------|-----|
| Compress profile photo | Squoosh | https://squoosh.app |
| Tech stack logos | Simple Icons CDN | https://cdn.simpleicons.org/{slug} |
| UI icons (outline) | Heroicons | https://heroicons.com |
| Color contrast check | WebAIM | https://webaim.org/resources/contrastchecker |
| Fonts | Google Fonts | https://fonts.google.com |
| Page speed test | PageSpeed Insights | https://pagespeed.web.dev |
| Deploy | GitHub Pages | https://pages.github.com |
| Background removal | Remove.bg | https://remove.bg |
| Photo cleanup | PFP Maker | https://pfpmaker.com |

---

*End of instructions. Build section by section in the order listed. Test on mobile after every major section.*
