# Paso 2 — Entorno Rust local

## Estado
Hecho.

## Objetivo de este paso
Dejar operativo el entorno Rust local hasta poder trabajar con Cargo sin fricción y validar que la base de desarrollo queda funcional antes de continuar con la preparación del proyecto.

## Decisiones cerradas en este paso
- El gestor oficial del toolchain local será `rustup`.
- El canal base de trabajo local será `stable`.
- Dado que el equipo local no dispone de permisos de administrador, el toolchain base adoptado para Windows en esta fase será `stable-x86_64-pc-windows-gnu`.
- El entorno debe quedar preparado para trabajar con `cargo` sin fricción.
- La validación mínima obligatoria del paso incluye:
  - disponibilidad de `rustup`
  - disponibilidad de `rustc`
  - disponibilidad de `cargo`
  - disponibilidad de `rustfmt`
  - disponibilidad de `clippy`
  - ejecución satisfactoria de una prueba local mínima con Cargo
- En este paso todavía no se definirán targets adicionales de cross-compilación.
- En este paso todavía no se configura IDE, editor, CI ni repositorio.

## Contexto que llevó a esta decisión
Inicialmente se había planteado usar la familia `stable-msvc` en Windows.

Sin embargo:
- el equipo local no dispone de permisos de administrador
- la instalación por la vía MSVC requería prerrequisitos de compilación de Windows que no se podían instalar en este contexto
- se adoptó por tanto la vía `gnu`, válida para uso básico sin privilegios de administrador

## Resultado real obtenido
El entorno Rust local quedó instalado correctamente en modo usuario.

Se verificó correctamente todo lo siguiente:
- `rustup -V`
- `rustc -V`
- `cargo -V`
- `rustup show`
- `rustup component add rustfmt clippy`
- `rustup component list --installed`

Además, se ejecutó con éxito una comprobación real con Cargo mediante un proyecto temporal `__rust-preflight`:

- `cargo check`
- `cargo run`
- `cargo test`
- `cargo fmt --check`
- `cargo clippy -- -D warnings`
- `cargo doc --no-deps`

Y al final:
- el directorio temporal `__rust-preflight` fue eliminado correctamente
- apareció el mensaje final esperado:
  - `PRE-FLIGHT OK (GNU): Rust y Cargo han quedado operativos sin permisos de administrador.`

## Toolchain local adoptado al cierre del paso
- host: `x86_64-pc-windows-gnu`
- canal: `stable`
- gestor: `rustup`

## Criterio operativo adoptado a partir de aquí
A efectos del desarrollo inicial del proyecto, se considera que el entorno local Rust en Windows ha quedado operativo y listo para continuar con los siguientes pasos de preparación.

## Nota importante para el futuro
Este paso queda cerrado con la vía GNU porque el entorno local no dispone de permisos de administrador.

Esto es válido para arrancar y trabajar en uso básico. Aun así, conviene dejar registrado desde ahora que:
- algunos crates podrían requerir más adelante una instalación más completa de MSYS2/MinGW
- si en fases posteriores el proyecto necesita integraciones o compilación más alineada con el ecosistema estándar de Windows, podría ser conveniente migrar en el futuro a `stable-msvc`

## Qué no se decide todavía en este paso
- versión mínima de Rust del proyecto
- edición de Rust del proyecto
- estructura del workspace
- crates del proyecto
- configuración de Codex
- AGENTS.md
- reglas de ejecución
- testing avanzado
- CI/CD

## Resultado documental de este paso
Se considera oficialmente validado el entorno Rust local de zenoverso-app para continuar con el paso 3.