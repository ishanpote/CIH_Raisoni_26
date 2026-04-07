# NexusLaunch

A comprehensive startup ecosystem platform connecting founders, investors, and innovators to accelerate startup growth through AI-powered tools and verified investor networks.

**Live Demo:** https://nexuslaunch-pi.vercel.app

---

## Table of Contents

- [Features](#features)
- [Project Structure](#project-structure)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Authentication System](#authentication-system)
- [Available Tools](#available-tools)
- [Dashboards](#dashboards)
- [Deployment](#deployment)
- [Team](#team)

---

## Features

✨ **Key Capabilities:**

- **Role-Based Access:** Three distinct user roles (Founder, Investor, User) with tailored experiences
- **AI-Powered Tools:**
  - Pitch Generator - Create compelling startup pitches
  - Idea Analyzer - Evaluate business ideas
  - Pitch Enhancer - Improve pitch quality with AI
  - Investor Connect - Browse verified investor database
  
- **Founder Dashboard:** Manage pitches, track investor interest, monitor AI-scored metrics, submit new pitches
- **Investor Dashboard:** Browse startups, filter by industry/stage, save deals, manage portfolio pipeline
- **Investor Directory:** 500+ verified investors with detailed profiles, filters by stage and sector
- **Session Persistence:** Client-side authentication with localStorage for seamless experience

---

## Project Structure

```
CIH_raisoni/
├── index.html                 # Root entry point (redirects to landing_v2.html)
├── landing_v2.html            # Main landing page with hero, solutions, tools, about
├── login.html                 # Authentication interface with role selection
├── user_founder.html          # Founder dashboard
├── user_investor.html         # Investor dashboard
├── generator.html             # Pitch Generator tool
├── analysis.html              # Idea Analyzer tool
├── enhancer.html              # Pitch Enhancer tool
├── investor.html              # Investor directory & search
├── connect.html               # Investor connection interface
├── README.md                  # This file
└── [CSS/Assets]               # (Inline in HTML files)
```

---

## Tech Stack

**Frontend:**
- **HTML5** - Semantic markup
- **CSS3** - Advanced animations (fadeUp, glowPulse, shimmer, float), CSS Grid, Flexbox, scroll-snap
- **JavaScript (Vanilla)** - No frameworks; ES6+ features
- **Font Awesome 6.0-beta3** - Icon library
- **Google Fonts** - Inter typeface (weights 300–800)

**Storage:**
- **localStorage** - Client-side session management (key: `nexusLaunchAuth`)

**Deployment:**
- **Vercel** - Serverless hosting platform
- **GitHub** - Source control with auto-deployment on push

---

## Getting Started

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, Edge)
- No backend server required; runs as static site

### Local Development

1. **Clone the repository:**
   ```bash
   git clone https://github.com/ishanpote/CIH_Raisoni_26.git
   cd CIH_raisoni
   ```

2. **Open in browser:**
   ```bash
   # Option 1: Open directly
   open index.html
   
   # Option 2: Use a local server (for best experience)
   python -m http.server 8000
   # Then visit http://localhost:8000
   ```

3. **Navigate to landing page:**
   - Deployed: https://nexuslaunch-pi.vercel.app
   - Local: http://localhost:8000

---

## Authentication System

### How It Works

1. **Login Flow:**
   - User selects role on login.html (Founder, Investor, or User)
   - Credentials are NOT validated (demo auth)
   - Session stored in localStorage under key `nexusLaunchAuth`
   - User redirected to role-appropriate dashboard

2. **Session Structure:**
   ```javascript
   {
     role: "founder" | "investor" | "user",
     loggedIn: true,
     at: 1712505600000  // timestamp
   }
   ```

3. **Logout:**
   - Clears localStorage
   - Redirects to landing_v2.html
   - Available from dashboards and landing page

### Roles

| Role | Dashboard | Tools | Purpose |
|------|-----------|-------|---------|
| **Founder** | `user_founder.html` | All tools | Submit pitches, track investor interest, improve ideas |
| **Investor** | `user_investor.html` | All tools | Browse startups, manage portfolio, discover deals |
| **User** | `landing_v2.html` | Pitch Generator only | Demo access, no dashboard |

---

## Available Tools

### 🎯 Pitch Generator (`generator.html`)
- **Access:** Public (no login required)
- **Purpose:** Create structured startup pitches with AI assistance
- **Features:** Template-based generator, AI refinement suggestions

### 📊 Idea Analyzer (`analysis.html`)
- **Access:** Login required
- **Purpose:** Evaluate business ideas against market criteria
- **Features:** Viability scoring, market analysis, risk assessment

### ✨ Pitch Enhancer (`enhancer.html`)
- **Access:** Login required
- **Purpose:** Improve pitch quality with AI-generated recommendations
- **Features:** Grammar check, persuasion scoring, formatting suggestions

### 💼 Investor Connect (`investor.html`)
- **Access:** Public (no login required)
- **Purpose:** Browse verified investor directory
- **Features:** Search by stage/sector, investor profiles, pitch day calendar

---

## Dashboards

### Founder Dashboard (`user_founder.html`)

**Metrics:**
- Pitch Views - Number of investors who viewed pitch
- Investor Interest - Count of interested parties
- AI Score - Automated pitch quality score
- Startup Stage - Current company stage

**Features:**
- Submit new pitches
- View pitch history with metrics
- Track investor engagement
- Logout to landing page

### Investor Dashboard (`user_investor.html`)

**Metrics:**
- Startups Viewed - Number of startups reviewed
- Deals in Pipeline - Active deal tracking
- Portfolio Value - Aggregate investment value
- Avg Pitch Score - Average quality rating

**Features:**
- Browse startup database with filters (industry, stage)
- Like, save, or connect with startups
- Filter by sector and funding stage
- Logout to landing page

---

## Deployment

### Vercel (Current Production)

**Status:** ✅ Live at https://nexuslaunch-pi.vercel.app

**Setup:**

```bash
# Install Vercel CLI
npm install -g vercel

# Authenticate (first time)
vercel whoami

# Deploy to production
vercel --prod --yes
```

**Configuration:**
- Project Name: `nexuslaunch`
- GitHub Integration: Enabled (auto-deploy on push to main)
- Environment: Static site (no build required)
- Repository: https://github.com/ishanpote/CIH_Raisoni_26

**Continuous Deployment:**
- Push to `main` branch → Automatic redeploy
- Deployment URL: https://nexuslaunch-pi.vercel.app
- Preview URLs generated for pull requests

### Root Entry Point

**index.html** serves as the root entry point for Vercel, redirecting all root requests to `landing_v2.html`:

```html
<meta http-equiv="refresh" content="0; url=landing_v2.html">
<script>window.location.replace('landing_v2.html');</script>
```

---

## Design System

### Animation Classes
- `.fadeUp` - Fade in with upward scroll
- `.glowPulse` - Pulsing glow effect
- `.shimmer` - Text shimmer animation
- `.float` - Floating motion effect

### Color Scheme
- **Primary:** Blue/teal gradients
- **Accents:** Gold/yellow highlights
- **Background:** Dark theme with contrast

### Responsive Design
- Mobile-first approach
- Full-viewport sections (100vh min-height)
- CSS Grid and Flexbox layouts
- Scroll-snap for section navigation

---

## Accessibility Features

- Semantic HTML5 elements
- ARIA labels where applicable
- Keyboard navigation support
- High contrast text for readability
- Font sizes optimized for mobile and desktop

---

## Team

**Developers:**
- **Rajat Kantode** - Full-stack design & implementation
- **Ishan Pote** - Authentication & tools architecture
- **Om Thaware** - Dashboard development
- **Abhinandan Pakhare** - UI/UX refinement

**Technologies Used:**
- HTML5, CSS3, JavaScript
- Font Awesome Icons
- Google Fonts
- Qwen 3.6+ (AI model for suggestions)

---

## Future Enhancements

🚀 **Planned Features:**

- Backend authentication with secure session management
- Real investor/startup database integration
- Video pitch uploads
- Investor messaging system
- Advanced analytics dashboard
- Mobile native apps (iOS/Android)

---

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/YourFeature`)
3. Commit changes (`git commit -m 'Add YourFeature'`)
4. Push to branch (`git push origin feature/YourFeature`)
5. Open a Pull Request

---

## License

This project is part of the CIH (Caring in Hardware) Raisoni hackathon initiative. All rights reserved.

---

## Support

For issues, feature requests, or questions:
- **GitHub Issues:** https://github.com/ishanpote/CIH_Raisoni_26/issues
- **Email:** contact@nexuslaunch.com (demo)

---

## Acknowledgments

- Font Awesome for icon library
- Google Fonts for typography
- Vercel for hosting infrastructure
- GitHub for version control and CI/CD

---

**Last Updated:** April 2026
**Status:** Active Development 🚀
