# Guía para proyectos Front-end y Back-end

Documento de referencia académica para estudiantes de programación. Este material está diseñado para ser utilizado como apoyo permanente durante el desarrollo de proyectos, tanto individuales como grupales, siguiendo estándares profesionales usados en la industria.

---

## Índice

* [1. Introducción](#1-introducción)
* [2. Estructura profesional del repositorio](#2-estructura-profesional-del-repositorio)
* [3. Control de versiones con Git y GitHub](#3-control-de-versiones-con-git-y-github)
* [4. Convención de commits (Conventional Commits)](#4-convención-de-commits-conventional-commits)
* [5. Tipos de commits y ejemplos](#5-tipos-de-commits-y-ejemplos)
* [6. Flujo de commits en proyectos Front-end](#6-flujo-de-commits-en-proyectos-front-end)
* [7. Flujo de commits en proyectos Back-end](#7-flujo-de-commits-en-proyectos-back-end)
* [8. Uso de scopes en commits](#8-uso-de-scopes-en-commits)
* [9. Cambios importantes (BREAKING CHANGE)](#9-cambios-importantes-breaking-change)
* [10. Fundamentos y ayudas para Front-end](#10-fundamentos-y-ayudas-para-front-end)
* [11. Fundamentos y ayudas para Back-end](#11-fundamentos-y-ayudas-para-back-end)
* [12. Flujo de trabajo con ramas](#12-flujo-de-trabajo-con-ramas)
* [13. Buenas prácticas para Pull Requests](#13-buenas-prácticas-para-pull-requests)
* [14. Comandos esenciales de Git](#14-comandos-esenciales-de-git)
* [15. Ejemplos profesionales de commits](#15-ejemplos-profesionales-de-commits)
* [16. Recomendaciones finales](#16-recomendaciones-finales)

---

## 1. Introducción

En el desarrollo de software profesional, no basta con que el código funcione. Es fundamental que el proyecto sea entendible, mantenible y escalable. Esta guía busca enseñar a los estudiantes a trabajar como lo harían en un entorno real de trabajo.

Aquí se abordan:

* Organización correcta de proyectos
* Uso profesional de Git y GitHub
* Escritura de commits claros y útiles
* Separación y fundamentos de Front-end y Back-end

---

## 2. Estructura profesional del repositorio

Una estructura clara permite que cualquier persona pueda entender el proyecto sin explicaciones adicionales.

```text
/frontend
  /src
  /public
  package.json
  README.md

/backend
  /src
  /tests
  package.json | requirements.txt
  README.md

/docs
  arquitectura.md
  endpoints.md
  modelo-datos.md

.gitignore
README.md
```

Buenas prácticas:

* Front-end y Back-end deben poder ejecutarse por separado.
* Cada carpeta debe tener su propio README.
* Los contratos entre Front-end y Back-end deben estar documentados.

---

## 3. Control de versiones con Git y GitHub

Git permite llevar un historial de cambios. GitHub permite colaboración, revisión de código y control del proyecto.

Principios clave:

* Commits pequeños y frecuentes.
* Nunca subir código roto a la rama principal.
* Cada commit debe explicar claramente qué se hizo.

---

## 4. Convención de commits (Conventional Commits)

Formato estándar:

```text
type(scope opcional): mensaje breve en presente
```

Ejemplo:

```text
feat(auth): add login with JWT
```

Ventajas:

* Historial legible
* Facilita revisiones
* Permite automatizar versiones

---

## 5. Tipos de commits y ejemplos

### feat

Nueva funcionalidad.

```text
feat(frontend): add dashboard page
```

### fix

Corrección de errores.

```text
fix(api): handle null user response
```

### docs

Cambios de documentación.

```text
docs(readme): update setup instructions
```

### style

Cambios de formato sin modificar lógica.

```text
style(frontend): format code with prettier
```

### refactor

Reorganización del código sin cambiar comportamiento.

```text
refactor(service): extract validation logic
```

### perf

Mejoras de rendimiento.

```text
perf(db): add index to users table
```

### test

Pruebas.

```text
test(api): add authentication tests
```

### build

Configuración o dependencias.

```text
build(frontend): update build config
```

### ci

Integración continua.

```text
ci: add github actions workflow
```

### chore

Mantenimiento.

```text
chore: update gitignore
```

### revert

Revertir commits.

```text
revert: revert "feat(api): add payments"
```

---

## 6. Flujo de commits en proyectos Front-end

Ejemplo realista:

```text
build(frontend): setup project structure
feat(frontend): add routing and layout
feat(ui): implement login form
fix(ui): handle invalid credentials
refactor(components): split large components
test(frontend): add unit tests
```

---

## 7. Flujo de commits en proyectos Back-end

Ejemplo realista:

```text
build(backend): setup server base
feat(api): add authentication endpoints
feat(db): create initial schema
fix(auth): validate token expiration
perf(db): optimize frequent queries
test(api): add integration tests
```

---

## 8. Uso de scopes en commits

El scope indica la parte afectada del proyecto.

Front-end:

* frontend
* ui
* components
* pages
* state

Back-end:

* backend
* api
* auth
* db
* service

Ejemplo:

```text
feat(api): create user profile endpoint
```

---

## 9. Cambios importantes (BREAKING CHANGE)

Se utilizan cuando un cambio rompe compatibilidad.

```text
feat(api): change user response format

BREAKING CHANGE: /users now returns data.user
```

---

## 10. Fundamentos y ayudas para Front-end

Conceptos esenciales:

* Componentes con responsabilidad única.
* Estado como única fuente de verdad.
* Separar lógica de presentación.

Checklist mental:

* Manejar loading, error y empty states.
* No asumir datos válidos.
* Evitar componentes demasiado grandes.

---

## 11. Fundamentos y ayudas para Back-end

Conceptos esenciales:

* Arquitectura por capas.
* Validación de datos.
* Manejo correcto de errores.
* Seguridad básica.

Checklist mental:

* Respuestas consistentes.
* Uso correcto de códigos HTTP.
* Logs útiles para depuración.

---

## 12. Flujo de trabajo con ramas

Ramas recomendadas:

* main
* develop (opcional)
* feature/nombre
* fix/nombre

Buenas prácticas:

* Una funcionalidad por rama.
* Pull Requests pequeños.

---

## 13. Buenas prácticas para Pull Requests

Un Pull Request debe incluir:

* Qué se hizo.
* Por qué se hizo.
* Cómo probarlo.
* Riesgos si existen.

---

## 14. Comandos esenciales de Git

```text
git status
git log --oneline
git checkout -b feature/nombre
git add .
git commit -m "feat: mensaje claro"
git push -u origin feature/nombre
```

---

## 15. Ejemplos profesionales de commits

Front-end:

```text
feat(ui): add responsive navbar
fix(frontend): prevent crash on empty list
refactor(components): extract modal logic
```

Back-end:

```text
feat(api): add health check endpoint
fix(auth): handle invalid token
perf(db): add index to orders table
```

---

## 16. Recomendaciones finales

Un proyecto profesional no solo funciona: se entiende, se mantiene y evoluciona.

El uso correcto de commits, estructura clara y fundamentos sólidos distingue un proyecto académico común de uno con nivel profesional.

Este documento debe ser consultado durante todo el desarrollo del proyecto.
