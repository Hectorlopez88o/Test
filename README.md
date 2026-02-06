# LM Brokerage & Logistics - New Website

> **Built by [Jorge Armenta](mailto:jorgeandresarmentat@gmail.com)** — Custom landing pages, web applications, and modern website redesigns for B2B companies.
>
> **Contact:** jorgeandresarmentat@gmail.com

---

## About the Business

**LM Brokerage & Logistics Inc.** is a licensed U.S. Customs Broker headquartered in Nogales, Arizona—one of the busiest U.S.-Mexico border crossings for international trade. Founded in 2012, the company specializes in:

- **Import/Export Clearance** - Handling all customs documentation, tariff classifications, and regulatory compliance for goods entering or leaving the United States
- **USMCA Analysis** - Helping clients maximize duty savings under the United States-Mexico-Canada Agreement
- **In-Bond Shipments** - Moving goods between U.S. ports of entry under customs bond
- **Bonded Warehousing** - Secure storage for imported goods before duty payment
- **Air & Ocean Freight** - Clearance services for all transportation modes
- **CTPAT Certified** - Customs-Trade Partnership Against Terrorism certification for enhanced security

**Key Clients:** Continental, Belkin, BAE Systems, Faurecia, Ducommun, Sargent Aerospace, BD Medical, and others across automotive, aerospace, medical, and electronics industries.

**Contact:**
- Phone: 1 (520) 281-2400
- Email: info@lmchb.com
- Hours: 7:00 AM - 6:00 PM MST

---

## About This Project

This repository contains a **complete redesign** of the LM Brokerage & Logistics public website. The goal is to replace the outdated legacy website at [lmchb.com](https://www.lmchb.com/new-page.html) with a modern, mobile-responsive landing page that better represents the company's professionalism and services.

### What Changed

| Aspect | Old Website | New Website |
|--------|-------------|-------------|
| **Technology** | Static HTML with Artisteer templates | Next.js 16 + React + TypeScript |
| **Design** | Mid-2010s corporate blue/gray | Modern white/red brand colors |
| **Mobile** | Not responsive | Fully responsive |
| **Animations** | None | Smooth Framer Motion animations |
| **Performance** | ~3-5s load time | <1s load time |
| **Hosting** | Traditional web server | Vercel edge network (global CDN) |

---

## What's Included (Ready to Use)

This repository contains a **fully functional frontend** landing page. Everything below works out of the box:

| Feature | Description | Status |
|---------|-------------|--------|
| **Homepage Design** | Complete modern landing page with all sections | ✅ Ready |
| **10 Service Cards** | Interactive cards with click-to-expand details and images | ✅ Ready |
| **Contact Form** | Full form with validation (name, email, company, phone, service, message) | ✅ Ready |
| **Mobile Responsive** | Optimized for phones, tablets, and desktop | ✅ Ready |
| **Animated Background** | Canvas-based shipping route animations | ✅ Ready |
| **Company Locations** | Both office addresses with Google Maps links | ✅ Ready |
| **Client Testimonial** | Featured quote from Continental | ✅ Ready |
| **Statistics Section** | Animated counters (12+ years, 10+ services, etc.) | ✅ Ready |
| **Navigation** | Desktop nav + mobile hamburger menu | ✅ Ready |
| **Footer** | Contact info, locations, quick links | ✅ Ready |
| **SEO Metadata** | Page titles, descriptions, Open Graph tags | ✅ Ready |
| **Favicon & Icons** | App icons for browser and mobile | ✅ Ready |

---

## What Needs Configuration (Action Required)

The following items require setup by your team before going live:

| Task | Instructions |
|------|--------------|
| **1. Deploy to Vercel** | [See Deployment Guide](#step-1-deploy-to-vercel-recommended) |
| **2. Connect Domain** | [See Domain Setup](#step-2-connect-custom-domain) |
| **3. Wire Contact Form** | [See Form Setup](#connecting-the-contact-form) |
| **4. Add Analytics** | [See Analytics Setup](#adding-analytics) |
| **5. Backend/Login** | [See Auth Setup](#adding-backendintranet-login) |

### Detailed Breakdown

#### 1. Deploy to Vercel (REQUIRED)
**What:** Host the website on Vercel's global CDN
**Why:** The site is just code right now—it needs to be deployed to be accessible on the internet
**Result:** Site live at `https://your-project.vercel.app`

#### 2. Connect Domain (REQUIRED)
**What:** Point `lmchb.com` (or new domain) to the Vercel deployment
**Why:** So customers visit your actual domain, not a Vercel URL
**Result:** Site live at `https://lmchb.com` with automatic SSL

#### 3. Wire Contact Form (REQUIRED)
**What:** Connect the form to actually send emails
**Why:** Currently the form validates and shows a success message, but doesn't send anywhere
**Result:** Form submissions go to `info@lmchb.com` (or your preferred inbox)

#### 4. Add Analytics (RECOMMENDED)
**What:** Track visitor behavior with Google Analytics or Vercel Analytics
**Why:** Understand how customers use your site, which services they view
**Result:** Dashboard showing traffic, page views, user flow

#### 5. Backend/Login (OPTIONAL)
**What:** Add authentication for a customer portal or employee intranet
**Why:** Only needed if you want password-protected pages
**Result:** Login page, protected dashboard routes

---

## System Architecture

### Current State (Frontend Only)

This is what's deployed now—a static frontend with no backend connections:

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                              INTERNET                                        │
└─────────────────────────────────────────────────────────────────────────────┘
                                    │
                                    ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                         VERCEL EDGE NETWORK                                  │
│                    (Global CDN - 100+ locations)                             │
│  ┌────────────────────────────────────────────────────────────────────────┐ │
│  │                        Next.js Application                              │ │
│  │  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐                  │ │
│  │  │   Homepage   │  │   Contact    │  │    Static    │                  │ │
│  │  │   (page.tsx) │  │  Form (CTA)  │  │    Assets    │                  │ │
│  │  └──────────────┘  └──────────────┘  └──────────────┘                  │ │
│  │         │                  │                 │                          │ │
│  │         ▼                  ▼                 ▼                          │ │
│  │  ┌─────────────────────────────────────────────────────────────────┐   │ │
│  │  │                     React Components                             │   │ │
│  │  │  Hero │ Services │ Stats │ Testimonial │ Locations │ Footer     │   │ │
│  │  └─────────────────────────────────────────────────────────────────┘   │ │
│  └────────────────────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────────────────┘
                                    │
                                    ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                              USER BROWSER                                    │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐        │
│  │   Desktop   │  │   Tablet    │  │   Mobile    │  │   Mobile    │        │
│  │   Chrome    │  │   Safari    │  │   Safari    │  │   Chrome    │        │
│  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘        │
└─────────────────────────────────────────────────────────────────────────────┘
```

### Full Architecture (With Backend Integrations)

This is the recommended production setup after completing all configuration:

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                              INTERNET                                        │
└─────────────────────────────────────────────────────────────────────────────┘
                                    │
            ┌───────────────────────┼───────────────────────┐
            ▼                       ▼                       ▼
┌───────────────────┐   ┌───────────────────┐   ┌───────────────────┐
│   lmchb.com       │   │  www.lmchb.com    │   │  *.vercel.app     │
│   (apex domain)   │   │   (subdomain)     │   │   (preview)       │
└───────────────────┘   └───────────────────┘   └───────────────────┘
            │                       │                       │
            └───────────────────────┼───────────────────────┘
                                    ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                         VERCEL EDGE NETWORK                                  │
│                                                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                     Next.js Application                              │    │
│  │                                                                      │    │
│  │   FRONTEND (Server-Side Rendered)                                    │    │
│  │  ┌────────────┐ ┌────────────┐ ┌────────────┐ ┌────────────┐        │    │
│  │  │  Homepage  │ │  Services  │ │  Contact   │ │  Dashboard │        │    │
│  │  │    /       │ │    /#      │ │  /#contact │ │ /dashboard │        │    │
│  │  └────────────┘ └────────────┘ └────────────┘ └────────────┘        │    │
│  │                                      │               │               │    │
│  │   API ROUTES (Serverless Functions)  │               │               │    │
│  │  ┌────────────────────────────────────────────────────────────┐     │    │
│  │  │  /api/contact    │  /api/auth/*    │  /api/dashboard/*     │     │    │
│  │  │  (form handler)  │  (NextAuth.js)  │  (protected routes)   │     │    │
│  │  └────────────────────────────────────────────────────────────┘     │    │
│  │           │                  │                    │                  │    │
│  └───────────┼──────────────────┼────────────────────┼──────────────────┘    │
└──────────────┼──────────────────┼────────────────────┼──────────────────────┘
               │                  │                    │
               ▼                  ▼                    ▼
┌──────────────────────────────────────────────────────────────────────────────┐
│                         EXTERNAL SERVICES                                     │
│                                                                               │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐               │
│  │  EMAIL SERVICE  │  │   AUTH PROVIDER │  │    DATABASE     │               │
│  │                 │  │                 │  │   (Optional)    │               │
│  │  ○ Formspree    │  │  ○ NextAuth.js  │  │                 │               │
│  │  ○ SendGrid     │  │  ○ Clerk        │  │  ○ PostgreSQL   │               │
│  │  ○ Resend       │  │  ○ Auth0        │  │  ○ MongoDB      │               │
│  │  ○ SMTP Server  │  │  ○ Custom       │  │  ○ Supabase     │               │
│  │                 │  │                 │  │                 │               │
│  │  Receives form  │  │  Handles user   │  │  Stores user    │               │
│  │  submissions    │  │  login/logout   │  │  data, sessions │               │
│  └─────────────────┘  └─────────────────┘  └─────────────────┘               │
│           │                    │                    │                        │
│           ▼                    ▼                    ▼                        │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                      ANALYTICS & MONITORING                          │    │
│  │   ○ Google Analytics (traffic)    ○ Vercel Analytics (performance)  │    │
│  │   ○ Sentry (error tracking)       ○ LogRocket (session replay)      │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
└──────────────────────────────────────────────────────────────────────────────┘
```

### Data Flow Diagram

```
┌──────────────────────────────────────────────────────────────────────────────┐
│                         USER INTERACTIONS                                     │
└──────────────────────────────────────────────────────────────────────────────┘

1. VIEWING THE WEBSITE (No backend needed)
   ┌────────┐      ┌─────────┐      ┌──────────┐
   │  User  │ ───▶ │  Vercel │ ───▶ │  Static  │
   │Browser │ ◀─── │   CDN   │ ◀─── │   HTML   │
   └────────┘      └─────────┘      └──────────┘
        Fast: ~50-200ms globally


2. SUBMITTING CONTACT FORM (Requires email service)
   ┌────────┐      ┌─────────┐      ┌──────────┐      ┌─────────┐
   │  User  │ ───▶ │   Form  │ ───▶ │   API    │ ───▶ │  Email  │
   │ fills  │      │ Submit  │      │  Route   │      │ Service │
   │  form  │      │         │      │/api/     │      │(Formspree│
   └────────┘      └─────────┘      │ contact  │      │ SendGrid)│
                                    └──────────┘      └─────────┘
                                          │                 │
                                          ▼                 ▼
                                    ┌──────────┐      ┌─────────┐
                                    │ Success  │      │  Email  │
                                    │ Message  │      │  Inbox  │
                                    └──────────┘      │info@    │
                                                      │lmchb.com│
                                                      └─────────┘


3. USER AUTHENTICATION (Optional - for intranet/dashboard)
   ┌────────┐      ┌─────────┐      ┌──────────┐      ┌─────────┐
   │  User  │ ───▶ │  Login  │ ───▶ │NextAuth/ │ ───▶ │   Auth  │
   │ clicks │      │  Page   │      │  Clerk   │      │ Provider│
   │ login  │      │         │      │          │      │         │
   └────────┘      └─────────┘      └──────────┘      └─────────┘
                                          │
                                          ▼
                                    ┌──────────┐
                                    │ Session  │
                                    │  Cookie  │
                                    └──────────┘
                                          │
                                          ▼
                                    ┌──────────┐
                                    │Protected │
                                    │Dashboard │
                                    │  Pages   │
                                    └──────────┘
```

### Component Architecture

```
src/
├── app/                          # Next.js App Router
│   ├── page.tsx                  # Homepage (entry point)
│   ├── layout.tsx                # Root layout (wraps all pages)
│   ├── globals.css               # Global styles & theme
│   │
│   ├── api/                      # API Routes (serverless functions)
│   │   ├── contact/              # POST /api/contact
│   │   │   └── route.ts          #   → Handles form submissions
│   │   └── auth/                 # Auth endpoints (if using NextAuth)
│   │       └── [...nextauth]/
│   │           └── route.ts      #   → Login, logout, session
│   │
│   └── dashboard/                # Protected pages (future)
│       └── page.tsx              #   → Customer/employee portal
│
├── components/
│   ├── layout/
│   │   ├── Header.tsx            # Navigation bar
│   │   └── Footer.tsx            # Site footer
│   │
│   ├── sections/                 # Page sections (compose the homepage)
│   │   ├── Hero.tsx              #   → Main headline + partners
│   │   ├── Services.tsx          #   → 10 service cards
│   │   ├── WhyChooseUs.tsx       #   → Value propositions
│   │   ├── Stats.tsx             #   → Company statistics
│   │   ├── Testimonial.tsx       #   → Client quote
│   │   ├── Locations.tsx         #   → Office addresses
│   │   └── CTA.tsx               #   → Contact form
│   │
│   └── ui/
│       └── InteractiveBackground.tsx  # Canvas animations
│
└── data/
    └── content.ts                # All editable text content
                                  # (single source of truth)
```

---

## Tech Stack

| Technology | Purpose |
|------------|---------|
| [Next.js 16](https://nextjs.org/) | React framework with App Router |
| [TypeScript](https://www.typescriptlang.org/) | Type-safe JavaScript |
| [Tailwind CSS v4](https://tailwindcss.com/) | Utility-first CSS |
| [Framer Motion](https://www.framer.com/motion/) | Animations |
| [Lucide React](https://lucide.dev/) | Icons |

---

## Project Structure

```
lm-brokerage-logistics/
├── src/
│   ├── app/
│   │   ├── page.tsx          # Homepage (assembles all sections)
│   │   ├── layout.tsx        # Root layout with fonts/metadata
│   │   ├── globals.css       # Theme colors, fonts, utilities
│   │   └── favicon.ico       # Site favicon
│   ├── components/
│   │   ├── layout/
│   │   │   ├── Header.tsx    # Navigation header
│   │   │   └── Footer.tsx    # Site footer
│   │   ├── sections/
│   │   │   ├── Hero.tsx      # Hero section with headline
│   │   │   ├── Services.tsx  # 10 service cards
│   │   │   ├── WhyChooseUs.tsx
│   │   │   ├── Stats.tsx     # Company statistics
│   │   │   ├── Testimonial.tsx
│   │   │   ├── Locations.tsx # Office addresses
│   │   │   └── CTA.tsx       # Contact form
│   │   └── ui/
│   │       └── InteractiveBackground.tsx  # Animated routes
│   └── data/
│       └── content.ts        # ALL EDITABLE CONTENT HERE
├── public/
│   └── logo.png              # Company logo
├── package.json
├── next.config.ts
├── tailwind.config.ts
└── tsconfig.json
```

### Where to Edit Content

**All text content is centralized in one file:**

```
src/data/content.ts
```

This file contains:
- Company name, phone, email, hours
- Office addresses
- All 10 services with descriptions
- Client testimonial
- Navigation links
- Statistics

To update any text on the website, edit this file and the changes will reflect everywhere.

---

## Local Development

### Prerequisites
- [Node.js](https://nodejs.org/) version 18.17 or higher
- npm (comes with Node.js)

### Setup

```bash
# 1. Clone the repository
git clone https://github.com/jorgearmentat/lm-brokerage-logistics.git
cd lm-brokerage-logistics

# 2. Install dependencies
npm install

# 3. Start development server
npm run dev

# 4. Open in browser
# http://localhost:3000
```

### Available Commands

| Command | Description |
|---------|-------------|
| `npm run dev` | Start development server with hot reload |
| `npm run build` | Create production build |
| `npm run start` | Run production build locally |
| `npm run lint` | Check for code issues |

---

## Deployment Guide

### Step 1: Deploy to Vercel (Recommended)

Vercel is the easiest and recommended way to deploy Next.js applications.

#### Option A: Deploy via Vercel Dashboard (No CLI needed)

1. Go to [vercel.com](https://vercel.com) and sign up/login with GitHub
2. Click **"Add New Project"**
3. Select **"Import Git Repository"**
4. Find and select `lm-brokerage-logistics` repository
5. Click **"Deploy"**
6. Wait 1-2 minutes for build to complete
7. Your site is live at `https://lm-brokerage-logistics.vercel.app`

#### Option B: Deploy via CLI

```bash
# Install Vercel CLI
npm install -g vercel

# Login to Vercel
vercel login

# Deploy (from project directory)
vercel

# For production deployment
vercel --prod
```

### Step 2: Connect Custom Domain

After deploying to Vercel:

1. Go to your project in [Vercel Dashboard](https://vercel.com/dashboard)
2. Click **"Settings"** → **"Domains"**
3. Click **"Add Domain"**
4. Enter your domain: `lmchb.com` or `www.lmchb.com`
5. Vercel will show DNS records to add

#### DNS Configuration at Your Registrar

Add these DNS records at your domain registrar (GoDaddy, Namecheap, etc.):

**For apex domain (lmchb.com):**
```
Type: A
Name: @
Value: 76.76.21.21
```

**For www subdomain:**
```
Type: CNAME
Name: www
Value: cname.vercel-dns.com
```

6. Wait 1-48 hours for DNS propagation
7. Vercel will automatically provision SSL certificate

### Step 3: Environment Variables (If Needed)

For sensitive configuration, use Vercel Environment Variables:

1. Go to Project → **Settings** → **Environment Variables**
2. Add variables like:
   - `CONTACT_FORM_EMAIL` - Email to receive form submissions
   - `SMTP_HOST` - Email server host
   - `SMTP_USER` - Email username
   - `SMTP_PASS` - Email password

---

## Connecting the Contact Form

The contact form currently shows a success message but doesn't actually send emails. Here are options to make it functional:

### Option A: Formspree (Easiest - No Code Changes)

1. Sign up at [formspree.io](https://formspree.io)
2. Create a new form
3. Get your form endpoint (e.g., `https://formspree.io/f/xyzabc`)
4. Update `src/components/sections/CTA.tsx`:

```tsx
const handleSubmit = async (e: React.FormEvent<HTMLFormElement>) => {
  e.preventDefault();
  const formData = new FormData(e.currentTarget);

  if (!validateForm(formData)) return;

  setFormState("submitting");

  try {
    const response = await fetch("https://formspree.io/f/YOUR_FORM_ID", {
      method: "POST",
      body: formData,
      headers: { Accept: "application/json" },
    });

    if (response.ok) {
      setFormState("success");
    } else {
      setFormState("error");
    }
  } catch {
    setFormState("error");
  }
};
```

### Option B: Email via API Route (More Control)

1. Install nodemailer: `npm install nodemailer`
2. Create `src/app/api/contact/route.ts`:

```tsx
import { NextResponse } from "next/server";
import nodemailer from "nodemailer";

export async function POST(request: Request) {
  const data = await request.json();

  const transporter = nodemailer.createTransport({
    host: process.env.SMTP_HOST,
    port: 587,
    auth: {
      user: process.env.SMTP_USER,
      pass: process.env.SMTP_PASS,
    },
  });

  await transporter.sendMail({
    from: process.env.SMTP_USER,
    to: "info@lmchb.com",
    subject: `New Contact Form: ${data.name}`,
    html: `
      <h2>New Contact Form Submission</h2>
      <p><strong>Name:</strong> ${data.name}</p>
      <p><strong>Email:</strong> ${data.email}</p>
      <p><strong>Company:</strong> ${data.company}</p>
      <p><strong>Phone:</strong> ${data.phone}</p>
      <p><strong>Service:</strong> ${data.service}</p>
      <p><strong>Message:</strong> ${data.message}</p>
    `,
  });

  return NextResponse.json({ success: true });
}
```

3. Update form to call `/api/contact`

### Option C: Third-Party Services

- [Resend](https://resend.com) - Modern email API
- [SendGrid](https://sendgrid.com) - Enterprise email
- [Mailgun](https://mailgun.com) - Transactional email

---

## Adding Backend/Intranet Login

To add a customer portal or employee intranet:

### Option A: NextAuth.js (Recommended)

```bash
npm install next-auth
```

1. Create `src/app/api/auth/[...nextauth]/route.ts`
2. Configure providers (credentials, Google, etc.)
3. Create protected dashboard pages under `src/app/dashboard/`

**Documentation:** [next-auth.js.org](https://next-auth.js.org)

### Option B: Clerk (Easiest)

```bash
npm install @clerk/nextjs
```

1. Sign up at [clerk.com](https://clerk.com)
2. Add environment variables
3. Wrap app in `<ClerkProvider>`
4. Use `<SignIn>`, `<SignUp>`, `<UserButton>` components

**Documentation:** [clerk.com/docs](https://clerk.com/docs)

### Option C: Connect to Existing Backend

If you have an existing authentication system:

1. Create API routes that proxy to your backend
2. Store session tokens in cookies
3. Use middleware for route protection

---

## Adding Analytics

### Google Analytics

1. Create property at [analytics.google.com](https://analytics.google.com)
2. Get Measurement ID (G-XXXXXXXXXX)
3. Install: `npm install @next/third-parties`
4. Add to `src/app/layout.tsx`:

```tsx
import { GoogleAnalytics } from "@next/third-parties/google";

export default function RootLayout({ children }) {
  return (
    <html>
      <body>{children}</body>
      <GoogleAnalytics gaId="G-XXXXXXXXXX" />
    </html>
  );
}
```

### Vercel Analytics (Alternative)

```bash
npm install @vercel/analytics
```

```tsx
// src/app/layout.tsx
import { Analytics } from "@vercel/analytics/react";

export default function RootLayout({ children }) {
  return (
    <html>
      <body>
        {children}
        <Analytics />
      </body>
    </html>
  );
}
```

---

## Adding New Pages

To add a new page (e.g., `/about` or `/services/import`):

1. Create the file in the `app` directory:
   - `/about` → `src/app/about/page.tsx`
   - `/services/import` → `src/app/services/import/page.tsx`

2. Basic page template:

```tsx
export default function AboutPage() {
  return (
    <main>
      <h1>About Us</h1>
      <p>Page content here...</p>
    </main>
  );
}
```

---

## Updating Styles

### Brand Colors

Colors are defined in `src/app/globals.css`:

```css
@theme inline {
  --color-lm-red: #E31837;      /* Primary red */
  --color-lm-red-dark: #B8132C; /* Hover state */
  --color-deep-navy: #0D1B2A;   /* Dark text */
  /* ... */
}
```

### Fonts

The site uses three fonts:
- **Bebas Neue** - Headlines (display)
- **Space Grotesk** - Section titles (heading)
- **Inter** - Body text

To change fonts, update the Google Fonts import in `globals.css`.

---

## Troubleshooting

### Build Errors

```bash
# Clear cache and reinstall
rm -rf node_modules .next
npm install
npm run build
```

### Images Not Loading

External images must be whitelisted in `next.config.ts`:

```ts
const nextConfig = {
  images: {
    remotePatterns: [
      { protocol: "https", hostname: "images.unsplash.com" },
      { protocol: "https", hostname: "your-domain.com" },
    ],
  },
};
```

### Form Not Submitting

Check browser console for errors. Ensure:
1. Form action is correctly configured
2. CORS is not blocking requests
3. Environment variables are set in Vercel

---

## Support & Resources

- **Next.js Docs:** [nextjs.org/docs](https://nextjs.org/docs)
- **Vercel Docs:** [vercel.com/docs](https://vercel.com/docs)
- **Tailwind CSS:** [tailwindcss.com/docs](https://tailwindcss.com/docs)
- **Framer Motion:** [framer.com/motion](https://www.framer.com/motion/)

---

## Changelog

### v1.0.0 (January 2026)
- Initial release
- Complete landing page redesign
- Mobile responsive design
- Contact form with validation
- Interactive service cards
- Animated background

---

## License

This project is proprietary software for LM Brokerage & Logistics Inc.

---

## Built By

<table>
<tr>
<td>

### Jorge Armenta

**Custom Web Development & Design**

I build modern, high-performance websites and landing pages for B2B companies. Specializing in:

- Custom landing pages & marketing sites
- Next.js / React web applications
- Website redesigns & modernization
- Mobile-responsive design
- Backend integrations & APIs

**Let's work together:**
- Email: [jorgeandresarmentat@gmail.com](mailto:jorgeandresarmentat@gmail.com)
- GitHub: [@jorgearmentat](https://github.com/jorgearmentat)

</td>
</tr>
</table>
