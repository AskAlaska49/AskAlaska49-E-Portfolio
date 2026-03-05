# AskAlaska49 E-Portfolio - AI Coding Instructions

## Project Overview
A personal e-portfolio website showcasing Barbara Ralston's frontend development skills. Static HTML with semantic structure, responsive CSS using BEM naming conventions, and assets in `/assets/`.

## Architecture & Structure

### Single-Page Layout
- **index.html**: Single section `#about-me` containing navigation and hero content
- **styles.css**: All styles (no preprocessor) using BEM-style class naming
- **assets/**: Images, PDFs, SVGs (portfolio pieces, resume, profile photos)

### Key Components
1. **Navigation Bar** (`nav`): Fixed-height (100px) flex layout with logo and links
   - Primary CTA button uses `nav__link--anchor-primary` class with purple background (#6030b1)
   - All nav links use `link__hover-effect` for consistent interaction
2. **About Section** (`#about-me`): Full viewport height, intro with profile image, bio, and skills
   - Profile image uses circular mask with shadow (`about-me__picture--mask`)
   - Uses `text--purple` for accent color on key terms (Frontend Developer)

## Naming Conventions & Patterns

### BEM (Block Element Modifier) Structure
- **Block**: `.nav__`, `.about-me__`, `.link__`
- **Element**: `__link--list`, `__picture--mask` (double underscore)
- **Modifier**: `--primary`, `--black`, `--effect` (double hyphen)
- Example: `.nav__link--anchor-primary` = nav block, link anchor element, primary modifier

### Color System
- **Primary Brand**: `#6030b1` (purple) - stored inline, use for CTA buttons and accents
- **Dark Text**: `#242424` - default heading and text color
- **White**: Used on dark backgrounds (e.g., CTA button text)

### Responsive Units
- Max-width constraints: `max-width: 800px` (content row), `max-width: 1000px` (nav)
- All margins/paddings in pixels (8px, 12px, 20px, 28px increments)
- Flexbox-first layout approach (no CSS Grid currently used)

## Styling Patterns

### Reusable Classes
- `.flex`: Simple flexbox display
- `.flex-1`: `flex: 1` for flex-grow
- `.row`: Centered container with max-width, 0 auto margins
- `.text--purple`: Accent color for important terms

### Hover Effects
- `link__hover-effect` class exists but implementation not shown
- `nav__link--anchor-primary:hover` transitions with `all 300ms ease` to lighter purple (#5d3eff)
- Always include transition timing for consistency

### Typography
- **Font Stack**: "Lato" (primary) with Google Fonts imports for Dosis, Gravitas One, Lexend, Macondo, Roboto
- **Base Font Size**: 16px (p, h1-h6)
- **Line Heights**: 1.25 (headings), 1.5 (paragraphs)
- **Font Weight**: 700 for nav links and `.personal__logo` (bold)

## Key Patterns & Gotchas

1. **Section ID Naming**: Currently uses `#about me` (space) in HTML but CSS targets `#about-me` (hyphen) - watch for consistency
2. **Image Optimization**: Profile images use `transform: scale(1.5)` + `padding-top: 8px` for cropping effect instead of CSS object-fit
3. **Circular Images**: Use `border-radius: 50%` + `overflow: hidden` + `box-shadow` pattern for profile pictures
4. **Global Reset**: All elements reset padding/margin/box-sizing in `*` selector
5. **No JavaScript Currently**: All interactivity is CSS-based (transitions, hover states)

## Development Workflow

### Git & Deployment
- Repository initialized (`.git/` present)
- Recent activity: `git push` successful (exit code 0)
- Maintain conventional commit messages for portfolio updates

### Adding New Sections
1. Create semantic HTML section in `<body>`
2. Define BEM classes following existing pattern (`about-me__`, `projects__`, etc.)
3. Add styles to bottom of `styles.css` (no organization by section yet)
4. Use existing utility classes (`.flex`, `.row`, `.text--purple`)

### Image Management
- Store in `/assets/` with descriptive names (e.g., `chat.png`, `dashboard.png` for project screenshots)
- Multiple photo variations exist (`me.jpeg`, `memedsize.jpeg`, `meorg.jpeg`) - consolidate to single optimized version

## Common Tasks

### Update Navigation Links
- Modify `<a>` elements in `nav` > `ul.nav__link--list`
- Use `nav__link--anchor` for regular links, `nav__link--anchor-primary` for CTA
- Remember space-separated classes for multi-effect (e.g., `nav__link--anchor link__hover-effect`)

### Add New Portfolio Section
- Create `<section>` with descriptive ID and classes
- Use `.row` wrapper for centered content with max-width
- Use `.flex` + `flex-direction: column` for vertical stacking
- Color accents use `.text--purple` or inline color

### Modify Colors
- Primary brand color (#6030b1) appears in multiple places - search/replace all occurrences
- Hover states typically use slightly lighter shade (#5d3eff)

## Tools & Commands
- **Version Control**: Git (no build tools, linter, or preprocessor)
- **No Build Step**: Serve directly from project directory
- **Testing**: Manual browser testing (no automation framework)
