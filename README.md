# Legalize AD

### Legislació andorrana consolidada en Markdown, versionada amb Git.

Cada llei és un fitxer. Cada reforma és un commit.

**Font oficial:** [BOPA](https://www.bopa.ad) — Butlletí Oficial del Principat d'Andorra

Forma part del projecte [Legalize](https://github.com/legalize-dev/legalize) · [legalize.dev](https://legalize.dev)

> **Fase inicial** — Aquest dipòsit està en desenvolupament actiu. L'estructura dels fitxers, l'historial de commits i el contingut poden canviar significativament, incloent regeneracions completes.

## Inici ràpid

```bash
# Clonar la legislació andorrana
git clone https://github.com/legalize-dev/legalize-ad.git

# Cercar a la Llei de caça
grep -A 5 "Article 1" ad/BOPA-L-2024-18.md

# Historial de modificacions d'una llei
git log --oneline -- ad/BOPA-L-2024-18.md

# Llegir la Constitució del Principat d'Andorra
less ad/BOPA-C-1993.md
```

## Estructura

```
ad/
  BOPA-C-1993.md         — Constitució del Principat d'Andorra
  BOPA-L-2024-18.md      — Llei 18/2024, de caça
  BOPA-D-2024-501.md     — Decret 501/2024, d'aprovació del Reglament...
  BOPA-LD-{any}-{n}.md   — Legislació delegada
  ...
```

L'estructura del fitxer és **plana** — un sol directori per país, sense subdirectoris per rang. El tipus de norma està al frontmatter YAML de cada fitxer:

| Prefix | Tipus |
|---|---|
| `BOPA-L-` | Llei (organisme 02. Consell General) |
| `BOPA-LD-` | Legislació delegada (organisme 03. Govern) |
| `BOPA-D-` | Decret aprovant un Reglament (organisme 03. Govern) |
| `BOPA-C-` | Constitució del Principat d'Andorra |

## Format

Cada fitxer és Markdown amb frontmatter YAML:

```yaml
---
title: "Llei 18/2024, del 19 de desembre, de caça"
identifier: "BOPA-L-2024-18"
country: "ad"
rank: "llei"
publication_date: "2025-01-14"
last_updated: "2025-01-14"
status: "in_force"
source: "https://www.bopa.ad/bopa/037004/Pagines/CGL_2025_01_08_10_50_58.aspx"
department: "Govern del Principat d'Andorra"
signature_date: "2024-12-19"
bopa_issue: "BOPA 4/2025"
bopa_document_id: "CGL_2025_01_08_10_50_58"
---
```

Els tipus de commit són: `[bootstrap]` (publicació original), `[reforma]` (modificació) i `[correccion]` (correcció d'errata).

## Font

Les dades provenen de l'API pública de BOPA (Azure Functions + Blob Storage), que des de la Llei 25/2014 és la versió oficial i autèntica del Butlletí Oficial del Principat d'Andorra. No s'utilitzen fonts privades de tercers.

## Llicència

[MIT](LICENSE) — el contingut de les normes és de domini públic, el codi del pipeline és MIT.

---

Generat pel pipeline [legalize-pipeline](https://github.com/legalize-dev/legalize-pipeline).
