# Orion AI

Çok formatlı dosya okuma, otomatik özetleme, quiz/flashcard üretimi ve
Google Calendar entegreli çalışma planı oluşturan AI destekli çalışma platformu.

## Özellikler

- PDF, DOCX, PPTX, TXT, EPUB ve görsel (OCR) dosyalarını okuma
- Yüklenen içeriklerden otomatik özet çıkarma
- Konuya özel quiz ve flashcard (spaced repetition) üretimi
- Google Calendar entegreli otomatik çalışma planı

## Kurulum

```bash
python -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env          # .env dosyasındaki değerleri doldur
alembic upgrade head
uvicorn app.main:app --reload
```

## Klasör Yapısı

| Klasör | Amaç |
|---|---|
| `app/models` | SQLAlchemy tablo tanımları |
| `app/schemas` | Pydantic request/response modelleri |
| `app/routers` | API endpoint'leri |
| `app/services` | İş mantığı (dosya parse, LLM çağrıları, quiz üretimi vb.) |
| `app/tasks` | Celery arka plan görevleri |
| `app/core` | Config, güvenlik, Celery app |

## Teknolojiler

FastAPI · PostgreSQL · SQLAlchemy · Celery + Redis · Chroma (vector DB) · Anthropic API
