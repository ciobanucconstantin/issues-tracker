# Issue Tracker Web App

A lightweight, client-side web application for tracking issues using a 500-cell grid interface. Built with HTML, CSS, and JavaScript, it uses `localStorage` to persist data in the browser, making it easy to manage tasks without server dependencies. Features include tabbed organization, urgency-based coloring, responsive tooltips, and JSON import/export for data portability.

## Features

- **Grid-Based Interface**: 500-cell grid (50x10) to organize issues, with click-to-edit and hover-to-view details.
- **Tabbed Organization**: Create, rename, and deactivate tabs to group issues, with indicators (🟠🔴) for urgent issues.
- **Issue Management**:
  - Add/edit issues with title, description, due date, action date, and up to six links (case, quote, workorder, three additional).
  - Urgency colors: Green (>7 days), Orange (≤7 days or action date reached), Red (≤1 day or overdue).
  - Mark issues as completed to hide them from the grid.
- **Responsive Tooltips**: Hover over cells (3 seconds) to view issue details, with positioning adjusted to stay fully visible at screen edges.
- **Data Persistence**: Stores tabs and issues in `localStorage` as JSON, with import/export functionality for backups or sharing.
- **Modals**:
  - Issue modal for adding/editing issues with URL validation.
  - Tab Options modal for renaming tabs, viewing stats (total/green/orange/red/completed issues), and deactivating tabs.
  - AI Chat modal placeholder for future integration.
- **Navbar**: Quick access to import/export JSON and external links (e.g., "Buy Me a Coffee").
- **Responsive Design**: Adapts to various screen sizes, with scrollable grid and wrapping tabs.
- **Accessibility**: Semantic HTML and language tags (`lang="en"`) to prevent translation prompts.

## Installation

No server or build tools are required since the app runs entirely in the browser.

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/issue-tracker.git
   cd issue-tracker
   ```

2. **Open the App**:
   - Open `issue-tracker.html` in a modern browser (e.g., Chrome, Firefox, Edge).
   - Alternatively, serve the file locally using a simple HTTP server:
     ```bash
     python -m http.server 8000
     ```
     Then navigate to `http://localhost:8000/issue-tracker.html`.

## Usage

1. **Launch the App**:
   - Open `issue-tracker.html` in your browser.
   - The app initializes with one tab ("Tab 1") and an empty 500-cell grid.

2. **Manage Tabs**:
   - Click "+ Add Tab" to create new tabs.
   - Click a tab to switch; double-click to open the Tab Options modal for renaming or deactivation.
   - Tabs show 🟠 (orange issues) or 🔴 (red issues) indicators based on issue urgency.
   - Note: The last active tab cannot be deactivated.

3. **Manage Issues**:
   - Click a grid cell to open the Issue modal:
     - Fill in title, description, due date, action date, and optional links (case, quote, workorder, additional links 1–3).
     - URLs must start with `http://` or `https://` or be empty.
     - Save to add or update the issue.
     - For existing issues, use "Mark as Completed" to archive them.
   - Hover over a cell for 3 seconds to view a tooltip with issue details (title, description, dates, links).
     - Tooltips adjust position to stay visible at screen edges (left, right, bottom).

4. **Import/Export Data**:
   - Click "Import JSON" in the navbar to upload a `.json` file with tabs and issues.
   - Click "Export JSON" to download the current tabs and issues as `issue-tracker.json`.
   - JSON format: `{ tabs: [{ id, name, deactivated }], issues: [{ id, title, description, dueDate, actionDate, gridPosition, tabId, completed, caseLink, quoteLink, workorderLink, additionalLink1, additionalLink2, additionalLink3 }] }`.

5. **Troubleshooting**:
   - If tooltips are misaligned, ensure the browser is updated and test with different screen sizes.
   - If Chrome prompts for translation, clear `localStorage` (F12 → Application → Local Storage → Clear `tabs`, `issues`, `activeTabId`).
   - For issues, check the browser console (F12 → Console) for errors.

## Project Structure

```
issue-tracker/
└── issue-tracker.html  # Single HTML file with embedded CSS and JavaScript
```

- **HTML**: Semantic structure with grid, tab bar, navbar, and modals.
- **CSS**: Flexbox for layout, responsive design with media-implied adaptability, and custom styling for tooltips and urgency colors.
- **JavaScript**: Handles grid rendering, tab management, issue CRUD, tooltip positioning, and JSON import/export using `localStorage`.

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/YourFeature`).
3. Commit changes (`git commit -m 'Add YourFeature'`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Open a Pull Request with a clear description of changes.

### Suggested Improvements
- Implement the "Ask AI" modal functionality for issue analysis.
- Add ARIA attributes for better accessibility (e.g., `aria-describedby` for tooltips).
- Enhance tooltips with arrows or shadows for visual clarity.
- Add keyboard navigation for grid and modals.
- Support drag-and-drop for reordering tabs or moving issues.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Built with vanilla JavaScript, HTML, and CSS for simplicity and portability.
- Inspired by project management tools like Trello and Jira, adapted for lightweight, offline use.
- Special thanks to contributors (add your name or GitHub handle if applicable).

## Contact

For questions or feedback, open an issue on GitHub

---

[Support the project by buying me a coffee!](https://buymeacoffee.com/utools)
