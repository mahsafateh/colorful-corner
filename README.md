# Masal's Colorful Corner

A multi-page personal portfolio website built with pure HTML and CSS, showing two sides of my life: **work** (web development) and **life** (my watercolor artworks).

**Live site:** [jazzy-medovik-4552aa.netlify.app](https://jazzy-medovik-4552aa.netlify.app)

---

## The task

Final project for the *Layout & Styling Fundamentals* course (Hyper Island, FED28). The brief:

- Build a multi-page personal portfolio with **pure HTML and CSS, no frameworks**
- Minimum three pages: **Home** (who you are, one clear visual focus), **About** (story, skills) and **Work** (project cards laid out with CSS grid or flexbox)
- The **same navigation** on every page, using relative links
- Technical checklist:
  - `alt` text on all images
  - external CSS with a mix of element, class and id selectors
  - fully responsive (desktop and mobile)
  - Git repo with regular, meaningful commits, pushed to GitHub

---

## Pages

| Page | File | What it shows |
| --- | --- | --- |
| Home | `index.html` | Full-screen watercolor lake scene with my name, a tagline and an "Enter" button |
| About | `pages/home.html` | Split screen: **WORK** (the developer, dark side) and **LIFE** (the artist, watercolor side) |
| Work | `pages/portfolio.html` | Cards for my GitHub projects in a responsive CSS grid |
| Hobby | `pages/hobby.html` | A small gallery exhibition of my artworks |

```
colorful-corner/
├── index.html          # Home / landing page
├── index.css           # One shared stylesheet for all pages
├── assets/             # Artwork images
└── pages/
    ├── home.html       # About
    ├── portfolio.html  # Work
    └── hobby.html      # Hobby / gallery
```

---

## Planning

### 1. Concept and content
The idea was to present myself as two sides of one person:
- by day I write code
- by night I create dreamy watercolor-style worlds

The lake image welcomes visitors on the landing page. The About page splits the screen into those two sides. The Work page shows my GitHub repos, and the Hobby page exhibits my artworks.

### 2. Breaking the work down
I split the project into small tasks, following the three parts of the brief:

1. **Design:** theme, wireframes, colors and fonts
2. **Setup:**
   - folder structure and boilerplate HTML files
   - one shared stylesheet
   - Git repo
3. **Navigation:** the same header on every page, with all links tested before adding any content
4. **Pages, one at a time:** landing, then About, Work and Hobby
5. **Footer and responsiveness:** mobile-first CSS, tested at 320px, 375px, 768px and 1280px
6. **Polish:**
   - consistent headers and spacing across pages
   - link check
   - accessibility check
7. **Deploy** on Netlify

---

- **Fonts:**
  - **Noto Serif** for text: soft and readable, it suits the storybook feel
  - **Bitcount Ink**, a pixel-style font, as an accent on the "code" side
- **Split About page:** the dark, pixel-font left side and the soft watercolor right side show the contrast between my two worlds.

---

## How it was built

- **Layout:**
  - Flexbox for the navigation, the About split and the footer
  - CSS Grid for the project cards and the gallery
- **Responsive:** mobile-first styles, with `@media (min-width: 768px)` switching to the desktop layouts
  - The Work grid uses `repeat(auto-fit, minmax(min(300px, 100%), 1fr))`, which gives 1, 2 or 3 columns depending on the screen width
- **CSS variables** in `:root` hold the colors, fonts and spacing, so every page stays consistent
- **Selectors:**
  - element: `body`, `img`, `a`
  - class: `.card`, `.side`, `.artwork`
  - id: `#site-header`, plus a per-page id on `<body>`
- **Accessibility:**
  - descriptive `alt` text on every artwork
  - `aria-current="page"` on the active nav link
  - a visually hidden `<h1>` on the About page

---

## Run it locally

No installation needed. Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server
```

Then visit `http://localhost:8000`.
