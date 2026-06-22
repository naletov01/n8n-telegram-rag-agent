# Telegram AI Agent with RAG — n8n

AI агент в Telegram который отвечает на вопросы 
по базе знаний компании и записывает лидов в Google Sheets.

## Что умеет

- Отвечает на вопросы клиентов через RAG (Pinecone база знаний)
- Помнит контекст разговора (Window Buffer Memory)
- Записывает данные лидов в Google Sheets автоматически
- Обрабатывает ошибки и присылает уведомления

## Архитектура

[Telegram Trigger] → [AI Agent] → [Telegram: Send Message]
                          ↓
                    Tools:
                    - Pinecone (поиск по базе знаний)
                    - Google Sheets (запись лидов)
                    Memory: Window Buffer (по chat.id)

## Стек

- n8n (оркестрация)
- OpenAI gpt-4o-mini
- Pinecone (векторная БД)
- Google Sheets (CRM)
- Telegram Bot API

## Как запустить

1. Импортируй `workflow.json` в n8n
2. Подключи credentials: OpenAI, Pinecone, Google Sheets, Telegram
3. Загрузи документы в Pinecone index
4. Активируй workflow

## Скриншоты

<img width="1003" height="466" alt="workwlow" src="https://github.com/user-attachments/assets/eca05fd5-304d-4af6-b83c-b32d852fe0c0" />
<img width="439" height="459" alt="telegram_ dialogue" src="https://github.com/user-attachments/assets/1b3db95b-c042-43b6-9feb-7bfa9b37bc6e" />
