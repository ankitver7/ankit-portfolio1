# Tarun's Portfolio - AI Coding Agent Instructions

## Project Overview
Animated portfolio website built with React.js, Tailwind CSS, and Vite. Single-page application with smooth animations, parallax effects, and a dark theme with gradient accents. Deployed on Vercel with 27K+ YouTube views.

## Technology Stack
- **Framework**: React 18.3.1 with Vite 6.0.5
- **Styling**: Tailwind CSS 3.4 with PostCSS & Autoprefixer
- **UI Libraries**: react-icons, react-parallax-tilt, react-typing-effect
- **Forms**: @emailjs/browser for contact functionality
- **Routing**: react-router-dom 7.1.3
- **Notifications**: react-toastify 11.0.3
- **Deployment**: Vercel

## Project Structure
```
portfolio website/
├── src/
│   ├── components/          # Section-based component folders
│   │   ├── About/          # About section with typing effect
│   │   ├── Contact/        # EmailJS-powered contact form
│   │   ├── Education/      # Education timeline
│   │   ├── Experience/     # Work experience cards
│   │   ├── Footer/         # Social links footer
│   │   ├── Navbar/         # Fixed navigation with sections
│   │   ├── Skills/         # Tech stack grid with logos
│   │   ├── Work/           # Project showcase cards
│   │   └── BlurBlob.jsx    # Animated background effect
│   ├── assets/             # Images and tech logos
│   │   ├── tech_logo/      # Technology stack icons
│   │   ├── company_logo/   # Company/work logos
│   │   ├── education_logo/ # Educational institution logos
│   │   └── work_logo/      # Project thumbnail images
│   ├── constants.js        # All content data (skills, projects, etc.)
│   ├── App.jsx             # Main app with section layout
│   ├── App.css             # Global styles
│   ├── index.css           # Tailwind directives
│   └── main.jsx            # React entry point
├── public/                 # Static assets
├── index.html              # HTML entry point
├── tailwind.config.js      # Custom animations & gradients
└── vite.config.js          # Vite configuration
```

## Development Workflow
- **Install**: `npm install`
- **Dev Server**: `npm run dev` (starts Vite dev server)
- **Build**: `npm run build` (production build to dist/)
- **Preview**: `npm run preview` (preview production build)
- **Lint**: `npm run lint` (ESLint check)

## Architecture & Design Patterns

### Component Organization
- Each major section has its own folder under `src/components/`
- Components are self-contained with their own styling
- No prop drilling - data imported from `constants.js`
- Single-page layout with all sections in `App.jsx`

### Data Management
- **All content centralized in `src/constants.js`**
- Export arrays for skills, experience, education, projects
- Images imported and exported as constants
- To update portfolio content, edit `constants.js` only

### Styling Approach
- Dark theme: background `bg-[#050414]` throughout
- Tailwind utility classes for all styling (no CSS modules)
- Custom Tailwind extensions in `tailwind.config.js`:
  - `blob` animation for background effects
  - `skills-gradient` for custom gradients
- Grid pattern background created with CSS gradients
- Absolute positioning for layered effects (BlurBlob, grid overlay)

### Visual Effects
- **BlurBlob**: Animated gradient blobs using absolute positioning
- **Parallax**: `react-parallax-tilt` on cards for depth
- **Typing Effect**: `react-typing-effect` in About section
- **Grid Background**: Radial mask gradient for fade effect

## Key Conventions

### File Naming
- Components: PascalCase folders with PascalCase `.jsx` files
- Assets: lowercase with underscores (e.g., `company_logo/`)
- Constants file: singular `constants.js`

### Component Structure Pattern
```jsx
// Typical section component structure
import React from 'react';
import { data } from '../../constants';

const SectionName = () => {
  return (
    <section id="section-name" className="relative py-20 px-6">
      {/* Content mapping over constants data */}
    </section>
  );
};

export default SectionName;
```

### Layout Pattern
- All sections use `relative` positioning with `py-20 px-6`
- Dark background with light text (`text-white` variants)
- Responsive grid layouts with Tailwind breakpoints
- Section IDs for navigation anchors

## EmailJS Integration
- Contact form uses `@emailjs/browser` package
- Configuration in Contact component
- Toast notifications for success/error feedback

## Content Updates
**To modify portfolio content, update these arrays in `constants.js`:**
- `skills` - Technology logos and names
- `experience` - Work experience cards
- `education` - Educational background
- `projects` - Portfolio projects with links

## Deployment
- Configured for Vercel deployment
- Build output: `dist/` directory
- No environment variables needed for basic deployment
- Custom domain: tarunkaushik.vercel.app

## Notes for AI Agents
- **Never hardcode content** - always use or update `constants.js`
- When adding new tech logos, place in `src/assets/tech_logo/` and import in constants
- Maintain dark theme consistency (`bg-[#050414]` base color)
- All new sections should follow the existing vertical layout in `App.jsx`
- Use Tailwind's arbitrary values for custom colors/gradients
- Keep animations subtle - this project favors smooth over flashy
- Test contact form with valid EmailJS credentials before deployment
