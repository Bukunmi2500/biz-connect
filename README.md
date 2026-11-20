# Biz Connect AI upgrade

This version runs the website and AI endpoints from one Render Node.js Web Service.

## Files
- `index.html` — frontend; chat and Prompt Studio call the backend.
- `server.js` — Express backend; the OpenAI key stays on the server.
- `package.json` — Node.js dependencies and start command.

## Render Web Service settings
- Runtime: Node
- Build command: `npm install`
- Start command: `npm start`
- Add `OPENAI_API_KEY` in the Render Environment settings.
- Optional: set `OPENAI_MODEL` to a model available to your API project. Default: `gpt-6.2-astra`.

Never put the API key in `index.html`, `server.js`, GitHub, or a public `.env` file.

## Endpoints
- `GET /api/health`
- `POST /api/chat` with JSON `{ "message": "..." }`
- `POST /api/prompt` with JSON fields `mode`, `idea`, `subject`, `style`, `mood`.

The AI endpoints have a basic per-IP request limit. This is an early prototype safeguard, not a substitute for user accounts, stronger abuse prevention, and usage monitoring before a public launch.
