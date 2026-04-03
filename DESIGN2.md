# Design System Specification: Editorial Authentication

## 1. Overview & Creative North Star
The "Creative North Star" of this design system is **The Digital Curator**. 

Authentication is often treated as a utilitarian hurdle, but this system reimagines it as an invitation into a premium, editorial space. We move beyond the "standard" sign-in by utilizing intentional asymmetry—placing the brand narrative on the left and the interaction model on the right. This creates a balanced tension that feels sophisticated rather than templated. The experience is defined by breathable white space, high-contrast typography, and a "tonal-first" approach to depth, ensuring the interface feels like fine paper layered on a pristine digital desk.

---

## 2. Colors
Our palette is rooted in a spectrum of sophisticated neutrals, punctuated by an authoritative, saturated blue.

### Core Palette
- **Primary (`#0041a2`):** The engine of the system. Used for high-priority actions.
- **Primary Container (`#0b57d0`):** Used for deep-tonal buttons and hover states.
- **Surface (`#f6faff`):** The canvas. A cool-tinted white that reduces eye strain.
- **Surface-Container-Lowest (`#ffffff`):** Reserved for the focal interaction card to provide maximum "lift."
- **Secondary (`#5c5f5e`):** For instructional text that guides without shouting.

### The "No-Line" Rule
To achieve a high-end editorial feel, **prohibit the use of 1px solid borders for sectioning.** Boundaries must be defined through background color shifts. For example, a `surface-container-low` section sitting against a `surface` background creates a clean, architectural break without the visual "noise" of a line.

### Surface Hierarchy & Nesting
Treat the UI as physical layers. 
- **Layer 0 (Background):** `surface` (`#f6faff`)
- **Layer 1 (The Main Vessel):** `surface-container-lowest` (`#ffffff`) 
- **Layer 2 (Embedded Elements):** `surface-container` (`#eaeef3`) for subtle inputs or secondary areas.

### The "Glass & Gradient" Rule
For primary CTAs, avoid flat color. Use a subtle linear gradient from `primary` (`#0041a2`) to `primary_container` (`#0b57d0`). For floating overlays or tooltips, apply a 20px backdrop-blur to a semi-transparent `surface_container_low` to create a "frosted glass" effect, integrating the component into the environment.

---

## 3. Typography
The system uses a pairing of **Plus Jakarta Sans** for authority and **Inter** for utility.

- **Display (Plus Jakarta Sans):** Used for hero moments. Large scale (3.5rem) and wide tracking convey a premium, spacious feel.
- **Headline (Plus Jakarta Sans):** The "Sign In" moment. Set at `headline-lg` (2rem) to establish clear hierarchy.
- **Body (Inter):** The workhorse. `body-md` (0.875rem) provides maximum legibility for instructions and links.
- **Labels (Inter):** High-contrast, small-scale (0.75rem) text for inputs, ensuring that utility does not distract from the editorial flow.

---

## 4. Elevation & Depth
We eschew traditional drop shadows in favor of **Tonal Layering**.

- **The Layering Principle:** Depth is achieved by "stacking." A `surface-container-lowest` card placed on a `surface` background creates a soft, natural lift.
- **Ambient Shadows:** When a "floating" effect is necessary (e.g., for the main sign-in vessel), use an extra-diffused shadow: `0 24px 48px rgba(23, 28, 32, 0.05)`. This mimics soft, ambient room light.
- **The "Ghost Border" Fallback:** If an input or container requires a boundary for accessibility, use a **Ghost Border**: `outline-variant` (`#c3c6d6`) at 20% opacity. **Never use 100% opaque borders.**
- **Glassmorphism:** For dropdowns or language selectors, use a blur of 12px with a `surface_variant` background at 80% opacity to maintain the "frosted glass" aesthetic.

---

## 5. Components

### Buttons
- **Primary:** Rounded-full (9999px). Background: Gradient of `primary` to `primary_container`. Text: `on_primary` (White). 
- **Tertiary (Text-only):** No background. Text: `primary`. Used for "Create account" to maintain a low-friction visual weight.

### Input Fields
- **Container:** Rounded-sm (0.5rem). 
- **Border:** Ghost Border (20% opacity `outline-variant`). On focus, transition to 100% `primary`.
- **Label:** Floating label pattern using `body-md` that scales down to `label-md` on focus.

### The Focal Vessel (Main Card)
- **Geometry:** Large roundedness (`lg` or `2rem`).
- **Layout:** Two-column asymmetric split. Left side for brand (Logo + Headline + Subhead). Right side for interaction (Input + Action Group). 
- **Spacing:** Use `xl` (3rem) internal padding to ensure the content "breathes."

### Language & Footer Links
- **Style:** `body-sm` (0.75rem) in `secondary` color. 
- **Interaction:** On hover, shift to `on_surface` (Darker grey) with a subtle underline.

---

## 6. Do's and Don'ts

### Do
- **Do** use white space as a structural element. If an element feels cramped, increase the padding to the next tier in the scale.
- **Do** align the Google Logo with the "Sign in" headline on the vertical axis to create a strong left-hand margin.
- **Do** use the `primary` blue for links and CTAs to maintain a clear path to completion.

### Don't
- **Don't** use black (`#000000`) for text. Use `on_surface` (`#171c20`) to maintain a softer, premium contrast.
- **Don't** use standard 1px borders to separate the "Sign in" card from the background. Let the color shift and ambient shadow do the work.
- **Don't** use sharp corners. Every container must follow the roundedness scale (`sm` for inputs, `lg` for cards, `full` for buttons) to maintain the "Soft Minimalist" feel.