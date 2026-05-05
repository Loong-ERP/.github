<div align="center">

# 🐉 Loong

**Plataforma fintech para pequenos negócios — gestão financeira pelo WhatsApp, com IA.**

[![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)](https://python.org)
[![Django](https://img.shields.io/badge/Django-092E20?style=flat&logo=django&logoColor=white)](https://djangoproject.com)
[![React](https://img.shields.io/badge/React-20232A?style=flat&logo=react&logoColor=61DAFB)](https://react.dev)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)](https://docker.com)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=flat&logo=postgresql&logoColor=white)](https://postgresql.org)
[![Celery](https://img.shields.io/badge/Celery-37814A?style=flat&logo=celery&logoColor=white)](https://docs.celeryq.dev)
[![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat&logo=redis&logoColor=white)](https://redis.io)
[![Stripe](https://img.shields.io/badge/Stripe-626CD9?style=flat&logo=stripe&logoColor=white)](https://stripe.com)

</div>

---

## O que é o Loong

O Loong é uma plataforma de gestão financeira pensada para pequenos negócios brasileiros. A premissa é simples: a melhor interface de controle financeiro é uma que o usuário já usa todo dia — o WhatsApp.

O sistema permite registrar uma despesa com `+50 gasolina`, mandar a foto de um boleto para processar automaticamente via OCR, pedir um resumo financeiro e receber um gráfico de gastos por categoria — tudo sem abrir nenhum app.

Por trás disso, uma API Django robusta com autenticação JWT, assinaturas recorrentes via Stripe, tarefas assíncronas com Celery e Redis, multi-tenancy por workspace e 10 camadas de segurança.

**Premiado na FETEPS 16ª Edição** — maior feira de tecnologia das ETECs e FATECs do Estado de São Paulo.

---

## Stack

| Camada | Tecnologias |
|--------|-------------|
| **API** | Django 6 · Django REST Framework · Python 3.12 |
| **Auth** | SimpleJWT · 2FA/TOTP · Argon2 |
| **Async** | Celery · Redis · Celery Beat |
| **Banco** | PostgreSQL (prod) · SQLite (dev) |
| **Pagamentos** | Stripe (webhooks + assinaturas recorrentes) |
| **WhatsApp** | Meta Cloud API · Bot com parser regex + LLM |
| **IA** | Groq / LLaMA 3.3 70B · Google Gemini |
| **OCR** | pytesseract · pyzbar · PyMuPDF |
| **Infra** | Docker · Docker Compose · Nginx · Gunicorn |
| **Monitoramento** | Sentry · Logging estruturado |
| **Testes de carga** | Locust |

---

## Repositórios

| Repo | Descrição | Status |
|------|-----------|--------|
| [`loong-api-docs`](https://github.com/loong-erp/loong-api-docs) | Arquitetura, módulos, endpoints e decisões de design | Público |

> O código-fonte da API é privado por razões de segurança — chaves de integração, webhooks e lógica de negócio em produção. A documentação técnica cobre a arquitetura completa.

---

## Arquitetura em uma linha

```
WhatsApp → Meta Webhook → Django → Parser → [Celery + Redis] → Resposta
                                        ↓
                              LLM (Groq/LLaMA) — perguntas abertas
                              OCR (Tesseract)   — fotos de boleto
                              Stripe Webhooks   — pagamentos
```

→ Documentação completa: [loong-api-docs](https://github.com/loong-erp/loong-api-docs)

---

<div align="center">

Desenvolvido por [Caio Fiori Martins](https://linkedin.com/in/caiofiorimartins) · [github.com/fiorionrails](https://github.com/fiorionrails)

</div>
