# Backend (Django)

This is a minimal Django project scaffold for local development.

Quick start:

1. Create and activate a virtual environment (macOS / zsh):

```bash
python3 -m venv .venv
source .venv/bin/activate
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

### Vector database configuration

Set the following environment variables to enable Supabase vector storage and embeddings:

- `GEMINI_API_KEY` - Google API key for generating embeddings.
- `SUPABASE_URL` - Supabase project URL.
- `SUPABASE_KEY` - Supabase service role key.
- `SUPABASE_VECTOR_TABLE` - Target table name for vector rows (defaults to `documents`).
- `SUPABASE_QUERY_NAME` - Supabase function used for similarity search (defaults to `<table>_match`).

### Document uploads and ingestion

PDF upload handling and Supabase vector ingestion are isolated in the `uploads` app
(`backend/uploads`). Deck endpoints import serializers and services from that package to
keep document processing concerns separate from the `cards` app.

3. Run migrations and start the dev server:

```bash
python manage.py migrate
python manage.py runserver
```

Open http://127.0.0.1:8000/ to see the minimal backend response.
