# HelpDigital App Hub

## Overview
HelpDigital App Hub is a showcase portal for franchise applications. It displays a collection of digital solutions available to HelpDigital franchisees, with filtering capabilities and detailed app information modals.

## Project Architecture
- **Frontend**: React + Vite with TypeScript
- **Styling**: Tailwind CSS with custom theme tokens
- **UI Components**: shadcn/ui component library
- **Routing**: wouter for client-side routing

## Color Scheme
- **Primary (Dark Blue)**: #1e3a5f - Used in Hero/CTA section backgrounds
- **Accent (Green)**: #10b981 - Primary action color (buttons, highlights)
- **Background**: Light/white base with cards

## Key Features
1. **Header** - Sticky navigation with logo, nav links, and contact CTA
2. **Hero Section** - Impactful headline with app statistics counters
3. **App Grid** - Filterable grid of application cards
4. **Filter System** - Filter by status (All, Available, In Development, Coming Soon)
5. **App Modal** - Detailed view of each application with action buttons
6. **About Section** - Value proposition and benefits explanation
7. **CTA Section** - Call-to-action for franchise prospects
8. **Footer** - Copyright and legal links

## File Structure
```
client/src/
├── components/
│   ├── Header.tsx       # Navigation header
│   ├── Hero.tsx         # Hero section with stats
│   ├── AppGrid.tsx      # App cards grid with filters
│   ├── AppCard.tsx      # Individual app card component
│   ├── AppModal.tsx     # App detail modal
│   ├── AboutSection.tsx # Why HelpDigital section
│   ├── CTASection.tsx   # Call-to-action section
│   └── Footer.tsx       # Footer with links
├── lib/
│   └── apps-data.ts     # Mock data and utility functions
├── pages/
│   └── home.tsx         # Home page composing all sections
└── App.tsx              # Main app with routing
```

## App Data Structure
```typescript
interface App {
  id: number;
  nome: string;
  descricao: string;
  descricaoCompleta: string;
  categoria: string;
  status: "disponivel" | "desenvolvimento" | "embreve";
  icone: string; // Lucide icon name
}
```

## Running the Project
The workflow `Start application` runs `npm run dev` which starts:
- Express server (backend)
- Vite dev server (frontend)
- Both served on port 5000

## Recent Changes (January 2025)
- Initial implementation of HelpDigital App Hub portal
- All sections implemented with responsive design
- Filter functionality for app status
- Modal dialogs for app details
- SEO meta tags added for Open Graph sharing

## User Preferences
- Language: Portuguese (Brazilian)
- Design: Modern, professional with subtle gradients
- Responsive: Mobile-first approach
