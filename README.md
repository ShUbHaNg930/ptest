# PHOENIX — Canvas Protocol Build

PHOENIX is an interactive open-source revival experience: explore archived projects, help bring them back to life, leave tributes, manage revival tasks, and share project ideas.

This build adapts the app to the **Code Variant · Build 01 — The Canvas Protocol** challenge. Primary actions are performed by dragging a data card into a matching action zone, rather than by pressing a Submit/Save/Publish/Revive-style button.

## Run locally

The app is static HTML/CSS/JavaScript. Extract the ZIP, open a terminal in this directory, then run:

```bash
python -m http.server 8000
```

Open <http://localhost:8000> in your browser. You can also use VS Code's Live Server extension. Avoid opening `index.html` as a `file://` URL because some browser features and remote assets expect HTTP.

## Using the Canvas Protocol

1. Open a section such as **Graveyard**, **Community**, or **World Cemetery**.
2. Prepare or select a data card (project, community question, project submission, message, revival task, or settings draft).
3. Drag the card onto the matching zone in the gold-edged **THE CANVAS PROTOCOL** dock. On touch devices, press and drag a card to a zone.
4. Read the live status message in the dock to confirm the action or correct missing information.

The action zones are **Revive**, **Support**, **Needs Work**, **Leave Flower**, **Save**, **Publish**, **Add Project**, **Connect**, **Import**, **Complete Task**, and **Send Message**. The zones accept matching card types; invalid combinations show feedback instead of silently doing the wrong action.

Examples:
- Drag a project card to **Revive**, **Support**, or **Needs Work**.
- Fill the community form and drag the generated question card to **Publish**.
- Complete the required project details and coordinates, then drag the unlocked project submission card to **Add Project**.
- Type a Phoenix AI message, then drag its message card to **Send Message**.
- Drag a revival task card to **Complete Task**; drag profile/settings drafts or bookmarks to **Save**.

## Demo mode and backend

The app works in local demo mode without Supabase. Demo project submissions, project status updates, flower counts, saved bookmarks, and revival task progress are kept in browser storage on the current device. The GitHub connect/import flow uses clearly labelled sample repositories; it is not a real OAuth integration.

To enable shared project submissions, configure the Supabase URL and public anon key in `supabase-config.js`, then apply the schema in `supabase/schema.sql`. Keep service-role secrets out of frontend files. More setup detail is in `SUPABASE_SETUP.md`.

## Included project files

- `index.html` — app structure and Canvas Protocol dock
- `style.css`, `canvas-protocol.css`, `revival-enhancements.css` — base styles and drag/drop UI
- `script.js`, `revival-enhancements.js` — app behavior, local demo data, drag/drop action routing
- `assets/`, `frames/`, `world-map.svg` — visuals and cinematic intro assets
- `supabase/`, `supabase-config.js`, `SUPABASE_SETUP.md` — optional backend setup

## Notes

Project-health scores, AI responses, GitHub repositories, imported repositories, and sample revival plans are illustrative demo content unless you connect and implement the required external services. The Canvas Protocol provides a real drag/drop interaction path for the app's primary actions, with native HTML drag/drop and a touch pointer-drag fallback.
