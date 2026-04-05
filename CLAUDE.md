# Claude Memory — OpenPoGoWeb Session

## Active Project: phpIPAM Modern

A new project has been scaffolded at `/home/user/phpipam-modern`.
This is a full-stack replacement for phpIPAM with a modern tech stack.

See `/home/user/phpipam-modern/CLAUDE.md` for complete project memory.

---

## OpenPoGoWeb (this repo)

A real-time web dashboard for monitoring Pokemon Go bot activity.

### Tech Stack
- Vanilla JavaScript + jQuery
- Materialize CSS v0.97.6
- Google Maps API
- Socket.IO v1.4.5
- No build system — static files only

### Running
```bash
# Python 2
python -m SimpleHTTPServer
# Python 3
python3 -m http.server
# Access at http://localhost:8000
```

### Setup
1. Copy `config/userdata.js.example` to `config/userdata.js`
2. Add your Google Maps API key to `config/userdata.js`
3. Add bot usernames to the `users[]` array

### Key Files
| File | Purpose |
|------|---------|
| `index.html` | Main entry point |
| `js/main.js` | Core app logic — `mapView` object (~950 lines) |
| `css/main.css` | Custom styles |
| `config/userdata.js.example` | Config template (copy to `userdata.js`) |
| `data/pokemondata.json` | Pokemon species reference data |

### Architecture
- `mapView` object in `js/main.js` is the central state manager
- Socket.IO connects on `/event` namespace, receives `"logging"` messages
- Config file (`config/userdata.js`) is gitignored — never commit it

---

## phpIPAM Modern — Quick Reference

**Location**: `/home/user/phpipam-modern`

### Stack
- Backend: Python 3.12 + FastAPI + SQLAlchemy 2.0
- Frontend: React 18 + TypeScript + shadcn/ui + Tailwind CSS
- Database: PostgreSQL 16
- Deployment: Docker Compose

### Start Development
```bash
cd /home/user/phpipam-modern
docker-compose up -d
# Backend API:  http://localhost:8000  (docs at /docs)
# Frontend:     http://localhost:5173
```

### Key Directories
```
phpipam-modern/
├── backend/app/
│   ├── main.py          # FastAPI entry point
│   ├── models/          # SQLAlchemy ORM models
│   ├── routers/         # API route handlers
│   └── tests/           # pytest tests
└── frontend/src/
    ├── pages/           # Route-level React pages
    ├── hooks/           # TanStack Query data hooks
    └── lib/             # API client, auth store, utils
```
