# Paso 6 — Definir la estructura de alto nivel del repositorio sin rellenarla todavía

## Estado
Hecho.

## Objetivo de este paso
Definir la estructura de alto nivel del repositorio de zenoverso-app sin empezar todavía a rellenarla con implementación real.

## Contexto ya fijado
- El proyecto ya existe como repositorio Git real
- La raíz canónica del proyecto es el Git root del repositorio
- El proyecto arrancará como workspace virtual de Cargo
- El primer crate funcional previsto será `crates/zenoverso-app`

## Base técnica de esta decisión
En un workspace de Cargo:
- la raíz del workspace centraliza la definición del workspace
- los miembros reales pueden vivir en subdirectorios
- el workspace comparte `Cargo.lock` y `target` en la raíz

Además, para Codex:
- la raíz del proyecto se detecta normalmente en el directorio que contiene `.git`
- desde esa raíz se localizarán después `AGENTS.md` y `.codex/`

## Decisiones cerradas en este paso

### 1. Alcance de la estructura inicial del repositorio
Se adopta esta opción:

**Opción B — amplia desde el principio**

El árbol de alto nivel reservado del repositorio queda fijado así:

- `crates/`
- `docs/`
- `tests/`
- `benches/`
- `scripts/`
- `.codex/`
- `.github/workflows/`
- `adjuntos/`

### 2. Estructura interna de docs/
Se adopta que `docs/` quedará ya separado por dominios.

La estructura reservada queda fijada así:

- `docs/00-preparacion/`
- `docs/vision/`
- `docs/architecture/`
- `docs/decisions/`
- `docs/testing/`
- `docs/operations/`
- `docs/milestones/`

### 3. Estructura reservada dentro de crates/
Se adopta esta opción:

**Opción B — reservar desde ya varios crates previstos**

Las rutas reservadas quedan fijadas así:

- `crates/zenoverso-app/`
- `crates/core/`
- `crates/api/`
- `crates/infra/`
- `crates/xtask/`

## Resultado estructural al cierre del paso
A partir de este punto queda fijado que:
- la estructura de alto nivel del repositorio será amplia desde el principio
- `docs/` quedará separado por dominios desde esta fase preparatoria
- `crates/` reservará desde ya varios espacios de crecimiento futuro
- la estructura base del repositorio queda congelada antes de empezar a crear manifests, crates reales, AGENTS o configuración de Codex

## Árbol oficial reservado del repositorio
```text
zenoverso-app/
├─ .codex/
├─ .github/
│  └─ workflows/
├─ adjuntos/
├─ benches/
├─ crates/
│  ├─ zenoverso-app/
│  ├─ core/
│  ├─ api/
│  ├─ infra/
│  └─ xtask/
├─ docs/
│  ├─ 00-preparacion/
│  ├─ vision/
│  ├─ architecture/
│  ├─ decisions/
│  ├─ testing/
│  ├─ operations/
│  └─ milestones/
├─ scripts/
└─ tests/