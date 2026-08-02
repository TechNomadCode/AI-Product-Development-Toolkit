## PRIMARY OBJECTIVE:
Generate visually striking, modern, and highly polished frontend components and page structures based on the defined scope. Prioritize aesthetics, creative layout, sophisticated styling, and smooth micro-interactions where specified. Structure the code with good separation of concerns to facilitate future development.

---

## MODULE 1: OVERALL THEME & MOOD
*   **Describe the core feeling:** `[e.g., "Minimalist & Sophisticated", "Futuristic & Techy", "Playful & Organic", "Luxurious & Premium", "Clean & Trustworthy"]`
*   **Visual Inspiration (Optional):** `[e.g., "linear.app dark gradients", "stripe.com whitespace", "brutalist web design elements"]`

---

## MODULE 2: LAYOUT & SPACING
*   **Layout Approach:** `[e.g., "Asymmetrical grid", "Standard centered content within full-width sections", "Heavy use of negative space", "Overlapping elements", "Broken grid", "Sidebar navigation layout"]`
*   **Section/Component Separation:** `[e.g., "Clear visual dividers", "Seamless transitions", "Use distinct background colors/textures"]`
*   **Content Width:** `[e.g., "Mostly contained width (max-w-screen-xl)", "Some full-bleed elements", "Edge-to-edge content"]`
*   **Spacing Scale (Whitespace):** `[e.g., "Generous whitespace (large padding/margins)", "Tight and compact", "Standard Tailwind spacing"]`

---

## MODULE 3: COLOR PALETTE
*   **Background (Base):** `[e.g., "#FFFFFF", "#1A1A1A (Dark)", "#F8F8F8 (Off-white)"]`
*   **Text (Base):** `[e.g., "#111827 (Near Black)", "#E5E7EB (Light Gray for dark mode)"]`
*   **Primary Accent / Brand Color:** `[e.g., "#3B82F6 (Blue)", "#EC4899 (Pink)", "Electric Blue (#00FFFF)"]` (Used for primary CTAs, highlights)
*   **Secondary Accent (Optional):** `[e.g., "#10B981 (Green)", "#F59E0B (Amber)"]` (Used for secondary buttons, tags, icons)
*   **Gradient Usage (Optional):** `[e.g., "Subtle gradients on buttons", "Hero background gradient from #FF00FF to #00FFFF", "No gradients"]`
*   *(Specify Hex/RGB/HSL codes for precision. Describe general usage if needed.)*

---

## MODULE 4: TYPOGRAPHY
*   **Headline Font:** `[e.g., "Geist Sans (Default)", "Serif (e.g., Playfair Display)", "Monospace (e.g., JetBrains Mono)"]`
    *   **Headline Style:** `[e.g., "Bold weight", "Large size", "Uppercase", "Letter spacing: wide"]`
*   **Body Font:** `[e.g., "Geist Sans (Default)", "Clean Sans-Serif (e.g., Inter)"]`
    *   **Body Style:** `[e.g., "Normal weight", "Readable size (text-base)", "Line height: relaxed"]`
*   **Hierarchy:** `[e.g., "Strong visual hierarchy using size and weight", "Minimalist hierarchy"]`

---

## MODULE 5: IMAGERY & ICONS
*   **Image Style:** Use placeholders (`/placeholder.svg?width={w}&height={h}`), but describe the intended style: `[e.g., "Abstract 3D renders", "Clean product screenshots in device mockups", "High-quality lifestyle photos", "Geometric patterns", "Gradients"]`
*   **Icon Style (lucide-react):** `[e.g., "Standard stroke width", "Thin stroke width (adjust via props/CSS if possible)", "Filled style (if applicable icons exist)", "Consistent size (e.g., size={20})"]`

---

## MODULE 6: INTERACTIVITY & ANIMATION (Visual Focus)
*   **Hover Effects:** `[e.g., "Subtle scale/brightness changes on cards/buttons", "Underline effects on links", "Color transitions"]`
*   **Scroll Animations:** `[e.g., "Gentle fade-in/slide-up for sections", "Subtle parallax on background elements", "No scroll animations"]` (Apply where appropriate based on page structure)
*   **Button Interactions:** `[e.g., "Clear visual feedback on click (scale down/color change)"]`
*   **Loading States (Visual Only):** `[Optional: Describe visual placeholders if needed, e.g., "Skeleton loaders for cards/lists"]`
*   **State Transitions:** `[Optional: Describe visual transitions between states if specified in UX, e.g., "Smooth fade between tabs"]`

---

## MODULE 7: FILE STRUCTURE & COMPONENT STRATEGY (Separation of Concerns)
*   **Goal:** Structure the code for maintainability and easier future integration with logic/data.
*   **Directory Structure:** Organize components logically within `components/`. Suggestion:
    *   `components/layout/`: Shared layout components (e.g., AppLayout, SettingsLayout, Header, Footer, Sidebar).
    *   `components/views/` or `components/pages/`: Components specific to a particular page/view defined in Module 9 (e.g., DashboardSummary, ProfileForm). These compose smaller common/UI components.
    *   `components/ui/`: (Implicitly for shadcn components).
    *   `components/common/`: Small, reusable visual elements shared across multiple views (e.g., CustomStyledButton, IconBadge, DataCard, UserAvatar).
*   **Component Granularity:** Break down large page views (from Module 9) into smaller, focused presentational components. Example: A `ProfileForm` component might import common `Input` and `Button` components.
*   **Client Components:** Add `'use client'` directive *only* where essential for visual interactivity (e.g., dropdowns, toggles, visual carousels, accordions, form interactions). Keep structural components (layouts, page containers) as Server Components where possible.
*   **Props:** Define clear `interface` or `type` for component props (even with placeholder data) to establish component contracts.

---

## MODULE 8: COMPONENT STYLING NOTES (Optional Specifics)
*   **Buttons (shadcn/ui):** `[e.g., "Sharp corners (no border-radius)", "Pill-shaped", "Gradient background", "Subtle shadow"]`
*   **Cards (shadcn/ui):** `[e.g., "No border, distinct background color", "Thin border", "Heavy shadow", "Glassmorphism effect (background blur)"]`
*   **Inputs (Placeholders):** `[e.g., "Minimalist underline style", "Standard bordered input"]`
*   **Tables (Visual):** `[e.g., "Striped rows", "Hover effect on rows", "Minimal borders"]`
*   **Modals (Visual):** `[e.g., "Specific width", "Overlay style"]`
*   *(Add any other specific styling directions for base components based on UX Specs)*

---

## MODULE 9: REQUIRED PAGES/VIEWS (MVP Scope)
*   **Instruction:** Generate the necessary page files (e.g., `app/dashboard/page.tsx`, `app/settings/profile/page.tsx`) and associated view-specific components (`components/views/` or `components/pages/`) based on the definitions below. These definitions are derived from the UX Specifications (Input 1) and scoped by the MVP Definition (Input 2). Apply the overall theme, layout, styling, and component strategy defined in other modules. Use shared layout components where specified. Use placeholder data/text/links (`#`, `Lorem Ipsum`).

*   **Structure to use for each Page/View defined below:**
    *   **Page/View Name:** `[Name of the page/view (Ref UX Spec Section)]`
    *   **Intended Route/Path:** `[URL path for this page/view]`
    *   **Primary Layout Component:** `[Name of shared layout component, e.g., <AppLayout> (Ref UX Spec Section)]` (Specify if applicable)
    *   **Key Components/Sections within this page:**
        *   `[Component/Section Name (Ref UX Spec X.Y)]`: `[Brief description of content/purpose and key styling notes from UX Spec]`
        *   *(Repeat for all major components/sections on this page/view)*
    *   **Specific Notes:** `[Any overriding styles, interactions, states, or critical notes specific to this page/view from the UX Spec]`

---
*(The filler prompt will generate entries following the structure above, replacing the placeholder below)*

`[ <<< Entries for each required Page/View will be dynamically generated here by the filler prompt >>> ]`

---

## MODULE 10: TECHNICAL IMPLEMENTATION NOTES (For v0):
*   Generate within a single `<CodeProject id="[product-name]-visual-design-mvp">`.
*   Use **Next.js App Router** structure. Create page files (e.g., `app/dashboard/page.tsx`, `app/settings/profile/page.tsx`) corresponding to the routes defined in Module 9.
*   Create shared layout components (e.g., `components/layout/AppLayout.tsx`) as specified in Module 9 and apply them in the respective `layout.tsx` or page files.
*   Use `tsx` files, kebab-case filenames.
*   Use **shadcn/ui** components as a base, style heavily via **Tailwind CSS** according to Modules 1-8 and specific notes in Module 9.
*   Use **`lucide-react`** for icons, styled as per Module 5.
*   Implement **responsive design** visually based on UX Specs or standard practices if unspecified.
*   Ensure basic **accessibility** structure (semantic HTML).
*   **Structure:** Follow the separation of concerns strategy outlined in Module 7 (directory structure, component granularity, `'use client'` placement, prop types).
*   Use placeholder data (`Lorem Ipsum`) and placeholder external links (`#`). For **internal navigation** between pages defined in Module 9, use functional **Next.js `<Link>` components** with the correct `href` based on the defined routes. Avoid other functional logic (data fetching, state management, API calls).
*   Use `import type` for type imports.