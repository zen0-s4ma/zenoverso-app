# Paso 4 — Raíz real del proyecto, carpeta exacta, nombre definitivo y convención de rutas

## Estado
Hecho.

## Objetivo de este paso
Fijar de forma explícita:
- cuál es la raíz real del proyecto
- cuál es la carpeta exacta de trabajo en este momento
- cuál es el nombre definitivo del proyecto y del repositorio
- cuál será la convención oficial de rutas a partir de este punto

## Contexto ya fijado
- Nombre actual del proyecto/aplicación: `zenoverso-app`
- Cuenta de GitHub: `zen0-s4ma`
- Repositorio remoto oficial: `https://github.com/zen0-s4ma/zenoverso-app`
- Rama principal: `main`
- Ruta local actual del repositorio: `C:\Users\joaquin.rincon\Desktop\temp\zenoverso-app`

## Decisiones cerradas en este paso

### 1. Naturaleza de la carpeta local actual
La ruta local actual:

`C:\Users\joaquin.rincon\Desktop\temp\zenoverso-app`

queda definida como una **ruta temporal de trabajo/preparación**, no como la ubicación local definitiva del proyecto.

### 2. Definición canónica de la raíz del proyecto
La raíz canónica del proyecto queda definida de forma estable como:

**el Git root del repositorio `zenoverso-app`**

Esto significa que:
- la raíz oficial del proyecto no dependerá de una ruta absoluta concreta de Windows
- la documentación futura debe asumir como base el directorio raíz del repositorio
- cualquier clon futuro del repositorio mantendrá la misma definición de raíz canónica

### 3. Convención oficial de rutas
La convención oficial de rutas queda fijada así:

- usar rutas **relativas al repo root** como convención principal en la documentación
- reservar rutas absolutas de Windows solo para operaciones locales reales
- usar `/` en documentación general y técnica
- usar rutas Windows reales en ejemplos de PowerShell cuando haga falta

### 4. Confirmación final del nombre oficial
Quedan congelados formalmente estos tres nombres:

- nombre de la app/proyecto: `zenoverso-app`
- nombre del repositorio GitHub: `zenoverso-app`
- slug GitHub: `zen0-s4ma/zenoverso-app`

## Resultado estructural al cierre del paso
A partir de este punto queda fijado que:
- la carpeta local actual es solo una ubicación temporal válida de trabajo
- la identidad canónica del proyecto no depende de esa ruta
- la raíz oficial del proyecto será siempre el directorio raíz del repositorio Git
- toda la documentación futura debe escribirse pensando en el repo root como referencia principal

## Consecuencias prácticas de esta decisión
- se evita atar la documentación a una ruta local temporal
- se facilita mover o reclonar el proyecto más adelante sin tener que rehacer documentación base
- se alinea la documentación con el comportamiento esperado de Codex y con la estructura natural del repositorio Git
- prepara correctamente el terreno para crear después `AGENTS.md`, `.codex/config.toml`, el workspace de Cargo y el resto de la estructura

## Qué no se decide todavía en este paso
- workspace Cargo definitivo
- crates del proyecto
- AGENTS.md
- configuración de Codex
- reglas de ejecución
- CI/CD
- contenido del primer hito

## Resultado documental de este paso
Se considera oficialmente cerrado el paso 4: la ruta local actual queda definida como temporal, la raíz canónica del proyecto queda fijada como el Git root del repositorio, la convención oficial de rutas queda aprobada, y los nombres oficiales del proyecto y del repositorio quedan congelados.