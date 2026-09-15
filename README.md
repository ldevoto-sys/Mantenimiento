# Sistema de Gestión de Mantenimiento — HidroTécnica SPA

Sistema propio de gestión de mantenimiento, alternativo a Fracttal, para automatizar el ciclo de órdenes de trabajo, informes, cotizaciones y portal de clientes de HidroTécnica SPA.

Plan de proyecto completo (contexto de negocio, stack, modelos de datos, metodología y hoja de ruta): [`docs/plan-de-proyecto.docx`](docs/plan-de-proyecto.docx).

Especificación de integración con el CRM Comercial (Ventas → Operaciones — cómo esta app consulta y reporta el estado de una Orden de Trabajo): [`docs/HT-DO-XX-Especificacion-Integracion-Mantenimiento-v1.0.md`](docs/HT-DO-XX-Especificacion-Integracion-Mantenimiento-v1.0.md). Es un requerimiento nuevo, no contemplado en el plan de proyecto original — hay que incorporarlo al levantamiento de requerimientos de la Etapa 1 antes de avanzar a Maquetas.

## Estado actual

**Etapa 1 — Requerimientos** (en curso). Levantamiento de requerimientos con los usuarios (Luis, Andrea, Melannie, técnicos).

Este repositorio contiene por ahora solo el andamiaje de carpetas — sin código funcional. No se avanza a Etapa 2 (Maquetas en Figma) ni a desarrollo hasta cerrar el documento de requerimientos con casos de uso definidos.

## Stack tecnológico

| Componente | Tecnología |
|---|---|
| Backend / API | Python + FastAPI |
| Base de datos | SQLite (dev) → PostgreSQL (producción) |
| Frontend | React + Vite |
| Estilos | Tailwind CSS |
| PDFs (informes) | WeasyPrint |
| ORM | SQLAlchemy |
| Autenticación | JWT |
| Deploy | Railway o Render — recién en Fase 4 de desarrollo, cuando haya un flujo de OT funcional que mostrar |

## Estructura de carpetas

```
backend/
├── main.py           # Entry point FastAPI
├── models.py         # Modelos SQLAlchemy (tablas)
├── schemas.py        # Validación con Pydantic
├── routers/          # Endpoints por módulo
│   ├── ots.py
│   ├── clientes.py
│   ├── tecnicos.py
│   └── reportes.py
└── utils/
    └── pdf.py         # Generación de PDFs

frontend/
├── src/
│   ├── pages/         # Una carpeta por vista
│   ├── components/    # Componentes reutilizables
│   └── api/           # Llamadas al backend
└── public/

docs/
└── plan-de-proyecto.docx
```

## Hoja de ruta (resumen)

1. Requerimientos (sem 1–2) — **en curso**
2. Maquetas en Figma (sem 3–4)
3. Desarrollo — 4 fases (sem 5–16)
4. Pruebas (sem 17–18)
5. Correcciones (sem 19–20)
6. Documentación (sem 21–22)
7. Capacitación (sem 23–24)

Detalle completo de cada etapa en `docs/plan-de-proyecto.docx`.
