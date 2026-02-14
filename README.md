# Developer Portfolio - Frontend

A modern, responsive portfolio website showcasing web development projects with a clean design and interactive contact form.

## Overview

This is the frontend portion of a full-stack portfolio application. Built with vanilla HTML, CSS, and JavaScript, it demonstrates modern web development practices including semantic markup, modular CSS architecture, responsive design, and asynchronous API communication. The site features a main portfolio page showcasing projects and a dedicated contact page with real-time form validation and user feedback.

## Live Demo

**Live Site:** [Your deployed frontend URL]  
**GitHub Repository:** [Your repository URL]

## Features

### Design & User Experience
- **Responsive Layout** - Mobile-first design that adapts to all screen sizes
- **Modular CSS Architecture** - Organized into separate concern files for maintainability
- **CSS Custom Properties** - Centralized theming and easy customization
- **Smooth Scrolling** - Anchor navigation with header offset compensation
- **Professional Typography** - Google Fonts integration (Montserrat)
- **Visual Hierarchy** - Card-based layout with shadows and spacing

### Contact Form
- **Client-Side Validation** - Real-time HTML5 form validation
- **Async Form Submission** - Fetch API for seamless user experience
- **Status Feedback** - Live updates on submission status
- **Honeypot Spam Prevention** - Hidden fields to catch automated bots
- **Form Reset** - Automatic clearing after successful submission
- **Error Handling** - User-friendly error messages for failed submissions

### Portfolio Showcase
- **Project Display** - Grid layout for project cards
- **Technology Stack** - Visual representation of skills
- **Direct GitHub Link** - Easy access to source code
- **Resume Access** - Downloadable PDF resume

### Accessibility
- **Semantic HTML** - Proper heading hierarchy and ARIA labels
- **Keyboard Navigation** - Full keyboard accessibility
- **Focus Management** - Visible focus indicators
- **Alt Text** - Descriptive image alternatives
- **Screen Reader Support** - Proper labeling and live regions

## Architecture

```
┌─────────────────────────────────┐
│                                 │
│   Static HTML Pages             │
│   - index.html (Portfolio)      │
│   - contact/index.html          │
│                                 │
└────────────┬────────────────────┘
             │
             │ Loads
             ▼
┌─────────────────────────────────┐
│                                 │
│   CSS Modules                   │
│   - base.css (Global)           │
│   - Component styles            │
│                                 │
└────────────┬────────────────────┘
             │
             │ Styles
             ▼
┌─────────────────────────────────┐
│                                 │
│   JavaScript                    │
│   - Event listeners             │
│   - Form handling               │
│   - API communication           │
│                                 │
└────────────┬────────────────────┘
             │
             │ HTTPS POST
             ▼
┌─────────────────────────────────┐
│                                 │
│   Backend API                   │
│   /api/contact                  │
│                                 │
└─────────────────────────────────┘
```

### Component Architecture

**Modular CSS System:**
```
style.css (Main)
  ├── base.css       (Reset, variables, typography)
  ├── header.css     (Navigation bar)
  ├── hero.css       (Hero section)
  ├── projects.css   (Project showcase)
  ├── tech.css       (Technology stack)
  ├── video.css      (Video components)
  ├── why.css        (About section)
  └── footer.css     (Footer)
```

**Contact Page Structure:**
```
contact/style.css
  ├── Imports base.css & header.css
  ├── Card system
  ├── Form styles
  └── Responsive layouts
```

## Tech Stack

### Core Technologies
- **HTML5** - Semantic markup, form validation
- **CSS3** - Grid, Flexbox, custom properties, animations
- **JavaScript (ES6+)** - Fetch API, async/await, DOM manipulation

### Design Patterns
- **BEM Methodology** - Block Element Modifier naming convention
- **Mobile-First** - Progressive enhancement approach
- **Component-Based** - Modular, reusable CSS components

### External Resources
- **Google Fonts** - Montserrat font family
- **Favicon** - Custom branding icon

### Browser Support
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Setup

### Prerequisites
- A modern web browser
- A local web server (optional for development)
- Git

### Local Development

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd developer-portfolio/developer-portfolio-frontend
   ```

2. **Update API endpoint (if needed)**
   
   In `contact/script.js`, update the backend URL:
   ```javascript
   const response = await fetch("http://localhost:5000/api/contact", {
     method: "POST",
     headers: { "Content-Type": "application/json" },
     body: JSON.stringify(formData),
   });
   ```

3. **Serve the files**

   **Option 1: Python HTTP Server**
   ```bash
   # Python 3
   python -m http.server 3000
   
   # Python 2
   python -m SimpleHTTPServer 3000
   ```

   **Option 2: Node.js http-server**
   ```bash
   npx http-server -p 3000
   ```

   **Option 3: VS Code Live Server**
   - Install Live Server extension
   - Right-click `index.html` → Open with Live Server

4. **Access the application**
   
   Open `http://localhost:3000` in your browser

### Project Structure

```
developer-portfolio-frontend/
├── index.html                   # Main portfolio page
├── style.css                    # Main stylesheet (imports modules)
├── script.js                    # Global JavaScript (year, smooth scroll)
│
├── contact/
│   ├── index.html              # Contact page
│   ├── style.css               # Contact-specific styles
│   ├── script.js               # Form submission logic
│   └── selfie.jpg              # Profile photo
│
├── css-modules/
│   ├── base.css                # CSS reset, variables, typography
│   ├── header.css              # Navigation header
│   ├── hero.css                # Hero section styles
│   ├── projects.css            # Project grid & cards
│   ├── tech.css                # Technology stack section
│   ├── video.css               # Video components
│   ├── why.css                 # About/why section
│   └── footer.css              # Footer styles
│
├── images/
│   ├── favicon.png             # Site favicon
│   ├── etch.png                # Etch-a-Sketch project
│   ├── pw.png                  # Password generator project
│   └── ttt.png                 # Tic-tac-toe project
│
├── Harold_Durant_Resume.pdf    # Downloadable resume
└── README.md                   # This file
```

## Deployment

### Static Hosting Platforms

#### Netlify (Recommended)

1. **Via Drag & Drop:**
   - Go to [Netlify](https://www.netlify.com/)
   - Drag the `developer-portfolio-frontend` folder onto the dashboard
   - Site is live instantly

2. **Via Git:**
   - Connect your repository
   - Set build settings:
     - Base directory: `developer-portfolio-frontend`
     - Build command: (leave empty)
     - Publish directory: `.` (current directory)
   - Deploy

#### Vercel

1. Install Vercel CLI or use dashboard
   ```bash
   npm i -g vercel
   cd developer-portfolio-frontend
   vercel
   ```

2. Follow prompts to deploy

#### GitHub Pages

1. **Create gh-pages branch:**
   ```bash
   git checkout -b gh-pages
   git add .
   git commit -m "Deploy to GitHub Pages"
   git push origin gh-pages
   ```

2. **Enable in repository settings:**
   - Go to Settings → Pages
   - Source: Deploy from branch
   - Branch: `gh-pages` / `root`

#### Render Static Site

1. Create new Static Site on Render
2. Connect repository
3. Configure:
   - Root directory: `developer-portfolio-frontend`
   - Build command: (leave empty)
   - Publish directory: `.`

### Post-Deployment Configuration

1. **Update API endpoint** in `contact/script.js`:
   ```javascript
   const response = await fetch("https://your-backend.onrender.com/api/contact", {
     // ...
   });
   ```

2. **Update backend CORS settings** to allow your frontend domain:
   ```javascript
   // In backend server.js
   app.use(cors({
     origin: "https://your-frontend-domain.com",
   }));
   ```

3. **Test the contact form** to ensure frontend-backend communication works

## Code Structure

### Main Portfolio Page (index.html)

**Sections:**
- Header with navigation
- Hero section with introduction
- Projects showcase grid
- Technology stack display
- Why hire me section
- Footer with copyright

### Contact Page (contact/index.html)

**Layout:**
- Two-column grid (desktop)
- Single column (mobile)
- Left: About section with photo and resume
- Right: Contact form

**Form Fields:**
- First name (required, max 20 chars)
- Last name (required, max 20 chars)
- Email (required, validated, max 254 chars)
- Subject (dropdown selection)
- Message (required, max 1000 chars)
- Honeypot field (hidden)

### JavaScript Functionality

**Global (script.js):**
```javascript
// Dynamic copyright year
document.getElementById('year').textContent = new Date().getFullYear();

// Smooth scrolling for anchor links
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
  anchor.addEventListener('click', function (e) {
    e.preventDefault();
    const target = document.querySelector(this.getAttribute('href'));
    window.scrollTo({
      top: target.offsetTop - 80,
      behavior: 'smooth'
    });
  });
});
```

**Contact Form (contact/script.js):**
```javascript
// Async form submission
form.addEventListener("submit", async (e) => {
  e.preventDefault();
  
  // Show loading state
  status.textContent = "Sending message";
  
  // Prepare form data
  const formData = { /* ... */ };
  
  try {
    // Send to backend
    const response = await fetch(API_URL, {
      method: "POST",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify(formData),
    });
    
    // Handle response
    if (response.ok) {
      status.textContent = "Message sent successfully!";
      form.reset();
    }
  } catch (error) {
    status.textContent = "Server error. Please try again later.";
  }
});
```

### CSS Architecture

**CSS Custom Properties (base.css):**
```css
:root {
  --dark-bg: #0f172a;
  --button-color: #3b82f6;
  --text-primary: #1f2937;
  --text-light: #6b7280;
  --border-color: #d1d5db;
  --shadow: 0 8px 24px rgba(0, 0, 0, 0.15);
}
```

**Responsive Breakpoints:**
- Mobile: < 480px
- Tablet: 768px
- Desktop: > 768px

**Layout System:**
- CSS Grid for page layouts
- Flexbox for component alignment
- Mobile-first media queries

## Form Validation

### Client-Side Validation

**HTML5 Attributes:**
- `required` - Ensures field is filled
- `type="email"` - Validates email format
- `maxLength` - Prevents excessive input
- `pattern` (can be added) - Custom regex validation

**JavaScript Validation:**
- Trims whitespace from inputs
- Checks honeypot field for spam
- Provides real-time feedback

### Server-Side Validation

The backend performs additional validation:
- Email format verification
- Length constraints
- XSS prevention through sanitization
- Rate limiting

## Security Features

### Spam Prevention
**Honeypot Field:**
```html
<input 
  type="text" 
  name="company" 
  tabindex="-1" 
  autocomplete="off" 
  class="honeypot"
/>
```
```css
.honeypot { display: none; }
```

### Data Sanitization
- Form data is trimmed on client
- Backend sanitizes with validator.js
- XSS protection on server side

### HTTPS
- All API calls use HTTPS
- No sensitive data stored in frontend
- Secure credential handling

## Customization Guide

### Update Colors
Edit CSS custom properties in `css-modules/base.css`:
```css
:root {
  --button-color: #your-color;
  --dark-bg: #your-dark-color;
}
```

### Change Fonts
Update Google Fonts import in `index.html`:
```html
<link href="https://fonts.googleapis.com/css2?family=YourFont&display=swap" rel="stylesheet"/>
```

### Add Projects
In `index.html`, add new project card:
```html
<div class="project-card">
  <img src="images/your-project.png" alt="Project description">
  <h3>Project Name</h3>
  <p>Description...</p>
  <a href="#" class="btn">View Project</a>
</div>
```

### Modify Contact Form
Add new fields in `contact/index.html`:
```html
<p>
  <label for="phone">Phone</label>
  <input type="tel" id="phone" name="phone">
</p>
```

Update `contact/script.js` to include new field:
```javascript
const formData = {
  // ... existing fields
  phone: form.phone.value.trim(),
};
```

## Performance Optimization

### Current Optimizations
- Minimal external dependencies
- CSS imports for modular loading
- Deferred JavaScript loading
- Optimized images (recommended: WebP format)

### Recommended Improvements
- [ ] Implement lazy loading for images
- [ ] Minify CSS and JavaScript for production
- [ ] Use WebP images with fallbacks
- [ ] Add service worker for offline support
- [ ] Implement critical CSS inlining
- [ ] Use CDN for static assets

## Browser Compatibility

### Supported Features
- CSS Grid (IE 11+ with prefixes)
- Flexbox (All modern browsers)
- Fetch API (All modern browsers)
- CSS Custom Properties (All modern browsers)
- Async/Await (All modern browsers)

### Polyfills (if needed)
For older browser support, consider:
- Fetch polyfill for IE 11
- CSS Custom Properties polyfill
- Grid layout fallbacks

## Accessibility Checklist

- [x] Semantic HTML structure
- [x] Proper heading hierarchy (h1 → h2 → h3)
- [x] ARIA labels for navigation
- [x] Alt text for all images
- [x] Keyboard navigation support
- [x] Focus visible on interactive elements
- [x] Form labels properly associated
- [x] Live region for form status updates
- [x] Sufficient color contrast ratios
- [x] Responsive text sizing

## Testing

### Manual Testing Checklist

**Desktop:**
- [ ] Navigation links work
- [ ] Smooth scrolling functions
- [ ] Form submits successfully
- [ ] Form validation works
- [ ] Error messages display
- [ ] Success message displays
- [ ] Resume downloads
- [ ] External links open in new tab

**Mobile:**
- [ ] Layout is responsive
- [ ] Touch targets are adequate (44x44px minimum)
- [ ] Form is usable on small screens
- [ ] Navigation is accessible
- [ ] Images load properly

**Cross-Browser:**
- [ ] Chrome
- [ ] Firefox
- [ ] Safari
- [ ] Edge
- [ ] Mobile browsers

## Troubleshooting

### Form Not Submitting

**Issue:** Form shows "Server error" message

**Solutions:**
1. Check backend URL in `contact/script.js`
2. Ensure backend is running
3. Check browser console for CORS errors
4. Verify backend CORS settings allow frontend origin

### Styles Not Loading

**Issue:** Page appears unstyled

**Solutions:**
1. Check file paths in HTML `<link>` tags
2. Ensure CSS files are in correct directories
3. Check browser console for 404 errors
4. Verify `@import` statements in CSS files

### Images Not Displaying

**Issue:** Broken image icons

**Solutions:**
1. Check file paths in `<img>` tags
2. Ensure images exist in `images/` directory
3. Verify image file extensions match HTML
4. Check server configuration for static files

## Future Enhancements

- [ ] Add dark mode toggle
- [ ] Implement project filtering by technology
- [ ] Add animations and transitions
- [ ] Create blog section
- [ ] Add testimonials section
- [ ] Implement search functionality
- [ ] Add print stylesheet
- [ ] Create sitemap.xml
- [ ] Add Open Graph meta tags
- [ ] Implement analytics (Google Analytics/Plausible)
- [ ] Add RSS feed for blog
- [ ] Create downloadable project case studies

## Contributing

If you'd like to contribute or suggest improvements:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit your changes (`git commit -m 'Add improvement'`)
4. Push to the branch (`git push origin feature/improvement`)
5. Open a Pull Request

## License

This project is open source and available under the [MIT License](LICENSE).

## Contact

**Harold Durant**  
Email: [Your Email]  
GitHub: [@ROIEngineer](https://github.com/ROIEngineer)  
Portfolio: [Your Portfolio URL]

---

Built with ❤️ using HTML, CSS, and JavaScript
