## What this app does

Lume AI Software Catalog is a small web app that helps users discover AI tools. It lets visitors browse tools by category, search across the catalog, view detailed pages for each tool, and jump to a randomly selected “wildcard” recommendation. The “Ask AI” page also provides quick recommendations based on keyword matching and optional filters such as free, browser-based, or open-source software.

## How it works

- **Single-page catalog experience:** The home page loads the software data (sourced from GitHub API), indexes it by category and source, and renders category cards. Selecting a category or a tool re-renders the main content area without a full page reload. Breadcrumbs reflect the navigation state. Related tools are suggested by matching category first and source second. 
- **Fast client-side search:** The search box filters the in-memory dataset by tool name or description, caps results for performance, and displays a grid of matches with counts and empty-state messaging.
- **Wildcard discovery:** The wildcard page draws a random tool, favoring categories with enough entries to improve variety, and re-picks on demand.
- **Recommendations on the Ask page:** The Ask workflow loads the same dataset, extracts keywords from a user prompt, scores matches against names/descriptions/categories, and boosts scores based on checkbox filters before rendering the top matches.
- **Optional AI backend:** A lightweight Express server can serve an AI-powered search endpoint by sending the catalog data and a user query to a local Ollama model, returning the model’s response when available.

