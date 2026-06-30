# Studia

Studia zet cursusmateriaal om in een actieve leeromgeving met conceptuitleg, flashcards, toetsen en gespreide herhaling.

## Snel starten

Vereisten: Node.js 22+, Python 3.12+ en optioneel Docker.

```bash
cp .env.example .env
npm install
npm run dev
```

Open `http://localhost:3000`. De interface bevat demo-inhoud zodat alle kernschermen zonder API-sleutel bruikbaar zijn.

## API

```bash
cd backend
python -m venv .venv
.venv/Scripts/pip install -r requirements.txt
.venv/Scripts/uvicorn app.main:app --reload
```

Swagger is beschikbaar op `http://localhost:8000/docs`. Voor de volledige stack: `docker compose up --build`.

## Architectuur

- `src/app`: Next.js App Router schermen
- `src/components`: gedeelde productcomponenten
- `backend/app`: FastAPI, validatie en asynchrone verwerking
- PostgreSQL met pgvector via Docker Compose

De MVP gebruikt een in-memory jobqueue als heldere servicegrens. Vervang deze in productie door ARQ/Celery, object storage en database-persistentie. Supabase- en OpenAI-variabelen staan klaar in `.env.example`.

