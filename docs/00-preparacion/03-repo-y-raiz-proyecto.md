# Paso 3 — Repositorio Git y decisión de encaje

## Estado
En curso.

## Objetivo de este paso
Crear el repositorio Git desde el minuto cero y decidir correctamente cómo se encaja zenoverso-app en GitHub.

## Interpretación correcta fijada en este paso
zenoverso-app:
- no será un monorepo
- no vivirá dentro de un repositorio ya existente
- no será un subdirectorio funcional dentro de otro proyecto mayor

La decisión correcta es esta:

**zenoverso-app será un repositorio nuevo e independiente, creado bajo la cuenta de GitHub existente del usuario: `zen0-s4ma`.**

## Contexto ya fijado
- Nombre oficial del proyecto: `zenoverso-app`
- Ruta local actual de preparación: `C:\Users\joaquin.rincon\Desktop\temp\zenoverso-app`
- Superficie principal con agente: Codex web dentro de ChatGPT Plus
- Desarrollo y pruebas locales: Windows
- Objetivo del producto: multiplataforma
- Cuenta de GitHub existente del usuario: `zen0-s4ma`

## Decisiones cerradas en este paso
- el proyecto se almacenará en GitHub bajo la cuenta existente `zen0-s4ma`
- se creará un repositorio nuevo e independiente llamado `zenoverso-app`
- la carpeta local actual será la base del repositorio
- este paso no se considera cerrado hasta que exista el remoto y se haya realizado el primer push

## Progreso real ya completado
En local ya se ha dejado hecho todo esto:
- Git está instalado y operativo
- la identidad global de Git ha sido configurada
- la carpeta local actual ya ha sido inicializada con `git init`
- la rama principal ya ha sido fijada como `main`

## Qué tiene que hacer el usuario para cerrar este paso

### 1. Crear en GitHub el repositorio remoto
Crear un repositorio nuevo con estas características:
- owner: `zen0-s4ma`
- nombre: `zenoverso-app`

Y no inicializarlo con:
- README
- `.gitignore`
- licencia

### 2. Decidir la visibilidad del repositorio
Queda pendiente elegir una de estas dos opciones:
- público
- privado

### 3. Conectar el remoto
Desde la carpeta del proyecto:

```powershell
Set-Location C:\Users\joaquin.rincon\Desktop\temp\zenoverso-app
git remote add origin https://github.com/zen0-s4ma/zenoverso-app.git
git remote -v