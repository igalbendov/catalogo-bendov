# Catálogo · Bendov Clínica Estética

Sitio estático (un solo `index.html`) publicado en Vercel. Cada commit en `main` se publica solo.

## Cómo editar contenido (sin programar)
1. Abre `index.html` en GitHub → lápiz ✏️ (Edit).
2. Busca el bloque que necesitas (están al final del archivo, dentro de `<script>`):
   - `const DOCS` — médicos: nombre, rol, bio, foto (`img/...`).
   - `const PROCS` — un renglón por procedimiento:
     `name` (nombre), `desc` (descripción), `cat` (`facial` / `corporal` / `gineco` / `hormonal`),
     `tipo` (`Q` quirúrgico · `MI` mínimamente invasivo · `NQ` sin cirugía),
     `doc` (`bendov` / `colodro` / `ambos`), `hl: true` para destacarlo en "Más solicitados",
     `dur` / `rec` / `res` (duración, recuperación, resultado en la ficha),
     `tags` (palabras para el recomendador y el buscador).
   - `const JOURNEYS` — los tres "Me hice…" para pacientes: textos, procedimientos recomendados (`recs`), botón y mensaje de WhatsApp.
   - `const RECO` — preguntas del recomendador "Es mi primera vez".
3. *Commit changes*. En ~30 s está publicado. Si algo sale mal: Vercel → Deployments → versión anterior → *Promote to Production*.

Regla de oro: respeta comillas y comas. Para agregar un procedimiento, copia un renglón completo y cámbiale `id` (único), textos y campos.

## Medición
- **Vercel Analytics**: activar en el proyecto (Settings → Analytics).
- **GA4**: reemplazar `G-XXXXXXXXXX` (2 veces en `index.html`) por el ID de medición. Marcar `whatsapp_click` como conversión. Dimensiones personalizadas de evento: `origen`, `procedimiento`, `categoria`, `ubicacion`, `journey`, `modo`, `zona`, `inquietud`, `preferencia`.
- Eventos: `origen`, `modo`, `journey_click`, `procedimiento_abierto`, `tab_click`, `busqueda`, `recomendacion_resultado`, `whatsapp_click`, `scroll`, `tiempo_en_pagina`.

## Links por canal
| Uso | Link |
|---|---|
| Pantalla sala de espera | `https://catalogo.clinicabendov.cl/#pantalla` |
| Carteles salas post | `https://catalogo.clinicabendov.cl/#salapost` |
| Plantillas WhatsApp (Vambe) | `https://catalogo.clinicabendov.cl/#wsp` · `#post-lipo` · `#post-facial` · `#post-lifechip` |
| Isabel (bot) | `https://catalogo.clinicabendov.cl/#isabel` |
| Instagram / Meta Ads (modo primera vez) | `https://catalogo.clinicabendov.cl/#nuevo` |
| Ficha directa | `https://catalogo.clinicabendov.cl/#p-endolaser-facial` (cualquier `id` de PROCS) |

## Dominio
Vercel → Settings → Domains → `catalogo.clinicabendov.cl`. DNS: CNAME `catalogo` → `cname.vercel-dns.com`.
