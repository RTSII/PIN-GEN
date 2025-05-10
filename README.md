```markdown
# RTS-PIN - Rental PIN Generator

RTS-PIN is a single-page web application designed to generate unique 5-digit PIN codes for rental units. It allows users to select specific date ranges (by month and year) and rental units (organized by company) to generate secure and non-conflicting PINs. The application features a dark mode interface with royal blue and neon green accents, a responsive design for desktop and mobile (iOS optimized), and PWA capabilities for "Add to Home Screen" functionality.

## Features

*   **Date Selection:** Choose month and year for PIN generation.
*   **Unit Selection:**
    *   Units organized by rental company.
    *   Select individual units or all units for a specific company.
    *   Global "Select All" and "Clear All Selections" options.
*   **PIN Generation:**
    *   Generates unique 5-digit PINs.
    *   Avoids PINs starting with a predefined list of 4-digit forbidden prefixes (owner account numbers).
    *   Option to generate PINs for all available units or only selected units.
*   **Results Display:**
    *   Displays generated PINs in a clear, sortable table format (Date Range, Unit, PIN).
    *   Copy-to-clipboard functionality for individual PINs.
*   **Data Persistence:**
    *   Uses `localStorage` to remember generated PINs, selected units, and the last used month/year for a seamless experience.
*   **Export Options:**
    *   Export generated PINs as a CSV file.
    *   "iPhone Screenshot View" for a clean, shareable image of the PIN table.
*   **User Interface & Experience:**
    *   Dark mode theme with royal blue and neon green accents.
    *   Responsive design for desktop (including split-screen) and mobile devices (iOS optimized).
    *   Collapsible sections for organized information display (accordion style for main content).
    *   Visual loading indicator (Matrix-style animation).
    *   Interactive "RS" logo for quick application state reset.
*   **PWA Ready:**
    *   Includes a manifest and service worker setup allowing users to "Add to Home Screen" for an app-like experience (requires HTTPS hosting).

## Technology Stack

*   **HTML5:** Structure of the application.
*   **CSS3:** Styling, responsiveness, and theme.
    *   Flexbox and Grid for layout.
    *   Custom CSS variables for theming.
    *   Animations for loading states and UI elements.
*   **JavaScript (ES6+):** Core application logic.
    *   DOM manipulation.
    *   Event handling.
    *   `localStorage` for data persistence.
    *   PapaParse library for CSV export (though currently implemented via direct string generation).
*   **SVG:** For the animated "RS" logo.

## Setup & Usage

### Option 1: Online (Recommended for Full Functionality)

The application is designed to be hosted on a web server that supports HTTPS (required for `localStorage` in many modern browser contexts and for PWA features).

1.  **Deploy:**
    *   Host the `PIN-GEN.html` file on a static web hosting service like:
        *   [Vercel](https://vercel.com/) (recommended, easy Git integration)
        *   [Netlify](https://www.netlify.com/)
        *   [GitHub Pages](https://pages.github.com/)
        *   Cloudflare Pages
    *   If using a Git-based deployment (e.g., Vercel with GitHub), simply push the `PIN-GEN.html` file to your repository. Vercel will automatically build and deploy. No build commands are necessary as it's a single static file.

2.  **Access:**
    *   Open the provided URL (e.g., `https://your-project-name.vercel.app/PIN-GEN.html`) in your web browser on desktop or mobile.

### Option 2: Local Usage (Limited Functionality)

Opening the `PIN-GEN.html` file directly from your local file system (`file:///` URL) will have limitations:

*   **`localStorage` may not work reliably or at all** due to browser security restrictions. This means generated PINs, selected units, and date preferences will not be saved between sessions.
*   **PWA "Add to Home Screen" will not function.**

For local testing where `localStorage` is needed, you can run a simple local HTTP server:
1.  Navigate to the directory containing `PIN-GEN.html` in your terminal.
2.  If you have Python 3: `python -m http.server`
3.  If you have Node.js and `npx`: `npx http-server`
4.  Then open `http://localhost:8000/PIN-GEN.html` (or the port shown by the server) in your browser.

## How to Use

1.  **Select Date (Step 1):**
    *   Use the dropdown menus to choose the desired **Month** and **Year**.
    *   Use the `‹` and `›` buttons for quick month navigation.
    *   This card is usually expanded by default.

2.  **Select Rental Units (Step 2):**
    *   This card contains a grid of rental companies.
    *   Click on a company name to open a modal displaying its units.
    *   In the modal, check the boxes next to the units you want to select PINs for.
    *   Use the "Select all units for this company" checkbox within the modal for bulk selection.
    *   Alternatively, in the main "Rental Units" card, you can use the checkbox next to each company's name to select/deselect all units for that company directly.
    *   Use the "Select/Deselect All Units" checkbox at the top of this section to manage all units across all companies.
    *   Click "Clear All Selections" to uncheck all units.
    *   The "(Selected: X)" count updates in real-time.

3.  **Generate PINs (Step 3):**
    *   **Generate PINs for All Units:** Generates PINs for every unit defined in the system for the selected date.
    *   **Generate PINs for Selected Units:** Generates PINs only for the units you explicitly selected in Step 2.
    *   A loading animation will appear during generation.
    *   Status messages will indicate success or any issues.

4.  **View Generated PINs (Results Card):**
    *   This card automatically appears and expands when PINs are generated.
    *   PINs are displayed in a table with Date Range, Unit, and PIN.
    *   Click the copy icon next to a PIN to copy it to your clipboard.
    *   If a PIN could not be generated (due to too many collisions or restrictions), it will be marked as "Failed".

5.  **Export:**
    *   **iPhone Screenshot:** Prepares a clean, table-only view suitable for taking a screenshot on an iPhone. Includes the selected Month and Year.
    *   **Export CSV:** Downloads a CSV file of the currently displayed PINs.

6.  **Reset Application State:**
    *   Clicking the rotating "RS" logo in the left sidebar will clear all generated PINs, deselect all units, and reset the UI to its initial state for the currently selected month/year. This is a quick way to start over without refreshing the page.

## Forbidden PIN Prefixes

The application maintains a hardcoded list of 4-digit prefixes that are disallowed for the start of any generated 5-digit PIN. This is to avoid conflicts with owner account numbers. This list is within the JavaScript code in the `FORBIDDEN_PIN_PREFIXES` constant.

## Future Considerations / Potential Enhancements

*   User-manageable list of forbidden PIN prefixes (via UI and `localStorage`).
*   Manual PIN override in the results table.
*   More detailed logging or error reporting for PIN generation failures.
*   Theme customization options.

## Contributing

This is a personal/internal tool. For modifications, edit the `PIN-GEN.html` file directly.

---

*This README was generated based on the features and functionality of the RTS-PIN application.*
```

