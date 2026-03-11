# Paso 5 — Decidir que el proyecto arranca como workspace de Cargo

## Estado
Hecho.

## Objetivo de este paso
Decidir y dejar fijado que zenoverso-app arranca desde el principio como un workspace de Cargo, aunque inicialmente solo exista un crate funcional.

## Contexto ya fijado
- El proyecto ya existe como repositorio Git real
- La raíz canónica del proyecto es el Git root del repositorio
- El nombre oficial del proyecto es `zenoverso-app`
- La documentación futura debe referenciar por defecto rutas relativas al repo root

## Base técnica de esta decisión
Cargo define un workspace como una colección de uno o más paquetes gestionados juntos.

Las ventajas clave que interesan para este proyecto son:
- comandos comunes sobre todos los miembros
- `Cargo.lock` compartido en la raíz
- directorio `target` compartido en la raíz
- posibilidad de crecer a varios crates sin migración estructural brusca

## Decisiones cerradas en este paso

### 1. Forma del workspace en la raíz
Se adopta esta opción:

**Opción A — Workspace virtual**

Esto significa que:
- la raíz del repositorio contendrá un `Cargo.toml` con `[workspace]`
- la raíz del repositorio no será un paquete compilable
- los crates reales vivirán en subdirectorios del repositorio

### 2. Nombre y ubicación del primer crate funcional
Se adopta esta opción:

**Opción A**
- ruta prevista: `crates/zenoverso-app`
- nombre del paquete/binario funcional previsto: `zenoverso-app`

## Resultado estructural al cierre del paso
A partir de este punto queda fijado que:
- zenoverso-app arrancará formalmente como workspace de Cargo desde el día 1
- la raíz del repositorio usará un workspace virtual
- el primer crate funcional previsto vivirá en `crates/zenoverso-app`
- la raíz del repositorio no quedará atada a un crate concreto desde el arranque
- esta decisión deja preparado el terreno para que el proyecto pueda crecer más adelante hacia varios crates sin migración estructural brusca

## Consecuencias prácticas de esta decisión
- la documentación futura podrá hablar del repo root sin mezclarlo con un crate raíz
- será más fácil introducir en el futuro crates como `core`, `api`, `infra`, `xtask` u otros
- el árbol del repositorio queda mejor preparado para crecimiento por hitos
- la estructura encaja bien con una filosofía de separación progresiva entre interfaz, núcleo y adaptadores

## Qué no se hace todavía en este paso
- todavía no se crea el `Cargo.toml` real del workspace
- todavía no se crea el primer crate
- todavía no se define la estructura completa de `crates/`
- todavía no se crea `AGENTS.md`
- todavía no se configura `.codex/config.toml`

## Resultado documental de este paso
Se considera oficialmente cerrado el paso 5: zenoverso-app arrancará como workspace virtual de Cargo desde la raíz del repositorio, y el primer crate funcional previsto se ubicará en `crates/zenoverso-app` con nombre `zenoverso-app`.