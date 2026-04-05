# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Spendly is a personal expense tracking web application built with Flask. It allows users to log expenses, view spending patterns by category, and manage their financial data.

## Tech Stack

- **Backend**: Flask (Python)
- **Database**: SQLite (via `database/db.py`)
- **Frontend**: Jinja2 templates, vanilla CSS, vanilla JavaScript
- **Testing**: pytest, pytest-flask

## Commands

```bash
# Run the development server
python app.py

# Run tests
pytest
```

## Architecture

### Backend (`app.py`)

Flask application with the following route structure:

- **Public routes**: `/` (landing), `/register`, `/login`, `/terms`, `/privacy`
- **Protected routes** (to be implemented): `/logout`, `/profile`
- **Expense CRUD** (to be implemented): `/expenses/add`, `/expenses/<id>/edit`, `/expenses/<id>/delete`

### Database (`database/`)

- `db.py` — Database utilities (students implement `get_db()`, `init_db()`, `seed_db()`)
- Uses SQLite with row_factory and foreign keys enabled

### Frontend

- **Templates** (`templates/`): Jinja2 templates extending `base.html`
  - `base.html` — Base layout with navbar and footer
  - `landing.html` — Homepage with hero, features, CTA, and video modal
  - `terms.html`, `privacy.html` — Legal pages
  - `login.html`, `register.html` — Auth pages

- **Static assets** (`static/`):
  - `css/style.css` — All styles (CSS variables, components, responsive)
  - `js/main.js` — Client-side JavaScript (currently empty, features added as needed)

## Patterns

- All templates extend `base.html` using Jinja2 blocks (`title`, `content`, `head`, `scripts`)
- CSS uses CSS variables for theming (colors, fonts, spacing)
- No JavaScript frameworks — vanilla JS only
- Video modal in landing page uses iframe with src cleared on close to stop playback
