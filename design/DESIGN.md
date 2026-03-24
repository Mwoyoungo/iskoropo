# Design System Strategy: Hyperlocal Editorial

## 1. Overview & Creative North Star
**Creative North Star: "The Urban Tactile"**
This design system moves away from the sterile, "flat" aesthetic of traditional utility apps. Instead, it adopts a high-end editorial approach that blends "Chunky Minimalism" with "Gen Z Vibrancy." We treat the interface as a physical neighborhood—spacious, layered, and deeply touchable. 

By breaking the rigid grid through intentional asymmetry (e.g., oversized typography bleeding off-center) and replacing borders with tonal shifts, we create a premium feel that is "Township-Friendly" yet sophisticated. It is a system designed to feel like a high-end streetwear brand: bold, confident, and unapologetically spacious.

---

## 2. Colors: Tonal Depth & The "No-Line" Rule
The color palette avoids high-contrast harshness, opting instead for a "Deep Sea & Sunset" interaction between the primary dark and the accent orange.

*   **Primary Dark (#181c27):** Used for "On-Surface" elements and high-authority headers. It provides the grounding weight for the system.
*   **Primary Accent Orange (#f77622):** Reserved for "Moments of Joy"—CTAs, active states, and critical notification badges.
*   **The "No-Line" Rule:** Designers are strictly prohibited from using 1px solid borders for sectioning. Structural separation must be achieved through background shifts. For example, a `surface-container-low` card sitting on a `surface` background creates a natural boundary without the "boxed-in" feel of a stroke.
*   **Surface Hierarchy & Nesting:** Treat the UI as stacked sheets of matte paper.
    *   **Level 0 (Base):** `surface` (#f9f9f9)
    *   **Level 1 (Cards/Sections):** `surface-container-low` (#f3f3f3)
    *   **Level 2 (Active Elements):** `surface-container-highest` (#e2e2e2)
*   **Signature Textures:** Use subtle linear gradients for primary buttons—transitioning from `secondary` (#9d4300) to `secondary-container` (#fe7b27) at a 135-degree angle. This adds "soul" and a tactile, 3D quality to the interaction.

---

## 3. Typography: The Editorial Voice
We use a high-contrast pairing of **Plus Jakarta Sans** for authority and **Manrope** for utility.

*   **Display & Headlines (Plus Jakarta Sans):** These are the "shouting" elements. Use `display-lg` and `headline-lg` with tight letter-spacing (-0.02em) to create a chunky, "Gen Z" editorial look. Headlines should be the most prominent element on the screen.
*   **Body & Labels (Manrope):** These are the "whispering" elements. Designed for extreme readability in the field. Use `body-lg` for service descriptions and `label-sm` for metadata.
*   **Hierarchy Note:** Always lead with a `headline-lg`. If a screen feels "generic," increase the typography scale. The goal is "Authority through Scale."

---

## 4. Elevation & Depth: The Layering Principle
We reject the standard Material Design shadow. Depth is achieved through "Tonal Layering" and "Ambient Softness."

*   **Layering Principle:** Instead of shadows, use the spacing scale (`spacing-4` or `spacing-6`) and background shifts to imply hierarchy. A card doesn't need to "pop" if the background color behind it recedes.
*   **Ambient Shadows:** If a floating element (like a FAB or Top Sheet) is required, use a shadow with a blur of `40px` and an opacity of `6%` using the `on-primary-fixed-variant` color (#434653). It should look like a soft glow, not a dark smudge.
*   **The "Ghost Border" Fallback:** If accessibility requires a border (e.g., in high-glare outdoor settings), use `outline-variant` at 15% opacity. Never use a 100% opaque border.
*   **Glassmorphism:** For bottom sheets and top navigation bars, use `surface-container-lowest` with a 70% opacity and a `20px` backdrop-blur. This allows the "neighborhood map" background to bleed through, maintaining a sense of place.

---

## 5. Components

### Buttons & Inputs
*   **Primary Button:** Full pill-shaped (`rounded-full`). Height: `3.5rem`. Use the signature orange gradient. Text must be `title-sm` in `on-secondary`.
*   **Input Fields:** Use `rounded-xl` (30px). Background: `surface-container-low`. No borders. The active state is indicated by a 2px `secondary` bottom-bar only, keeping the "chunky" look clean.

### Chips & Tags
*   **Status Chips:** Always `rounded-full`. Use `secondary-fixed` with `on-secondary-fixed` text for high-energy statuses (e.g., "Request Live"). Use `primary-fixed` for passive states.

### Cards & Lists
*   **No Dividers:** Forbid the use of 1px lines between list items. Use `spacing-3` of vertical white space or alternate background colors between `surface-container-low` and `surface-container-lowest`.
*   **Service Cards:** Large `rounded-lg` (32px) corners. Content should be padded with `spacing-6` to ensure the "chunky, spacious" feel.

### Hyperlocal Map Background
*   **The Map Layer:** The map is not a widget; it is the floor. Use a desaturated "Calm" style. Service requests should appear as oversized, rounded markers that use `secondary` orange to pop against the muted gray background.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** use extreme white space. If you think there is enough padding, add `spacing-2` more.
*   **Do** overlap elements. Let a service card partially "peek" over a bottom sheet to show depth.
*   **Do** use "Chunky" touch targets. Every button should feel like it was designed for a thumb, not a cursor.

### Don’t:
*   **Don’t** use pure black (#000000). Always use `on-primary-fixed` for the heaviest darks.
*   **Don’t** use sharp corners. If a corner is less than 16px, it’s too sharp for this system.
*   **Don’t** use "Empty States" that are just icons. Use a `display-sm` headline that speaks the local township vernacular to build emotional warmth.