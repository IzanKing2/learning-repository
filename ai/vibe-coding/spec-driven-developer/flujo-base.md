# Flujo Base de Desarrollo con Spec-Driven Development + Vibe Coding

![Portada](https://framerusercontent.com/images/qBfGDRPfKupvBRH01Bwds8.png?width=1080&height=843)

> Objetivo: convertir una idea en una funcionalidad implementada, documentada y validada mediante un proceso repetible apoyado por IA.

---

# Índice

- [Filosofía](#filosofía)
- [Roles](#roles)
- [Flujo General](#flujo-general)
- [Paso 1. Product Brief](#paso-1-product-brief)
- [Paso 2. Arquitectura](#paso-2-arquitectura)
- [Paso 3. Specifications](#paso-3-crear-las-specifications)
- [Paso 4. Reglas para la IA](#paso-4-definir-las-reglas-para-la-ia)
- [Paso 5. Planificación](#paso-5-planificar-antes-de-programar)
- [Paso 6. Implementación](#paso-6-implementación)
- [Paso 7. Testing](#paso-7-testing)
- [Paso 8. Review](#paso-8-review)
- [Paso 9. Documentación](#paso-9-documentación)
- [Paso 10. Commit](#paso-10-commit)
- [Checklist](#checklist-de-una-feature)
- [Estructura recomendada](#estructura-recomendada)
- [Principios](#principios)
- [Referencias](#referencias)

---

# Filosofía

La IA **no sustituye** al análisis ni a la toma de decisiones.

El desarrollador es responsable de:

- Definir el problema.
- Diseñar la solución.
- Validar la implementación.
- Garantizar la calidad.

La IA actúa como un acelerador del desarrollo.

Puede ayudar a:

- Analizar requisitos.
- Diseñar arquitectura.
- Implementar código.
- Refactorizar.
- Detectar problemas.
- Crear documentación.
- Generar pruebas.
- Revisar código.

---

# Roles

| Desarrollador              | IA                   |
| -------------------------- | -------------------- |
| Define el problema         | Analiza el contexto  |
| Diseña la arquitectura     | Propone soluciones   |
| Escribe las Specifications | Implementa código    |
| Decide                     | Automatiza tareas    |
| Revisa                     | Detecta mejoras      |
| Aprueba cambios            | Genera documentación |

---

# Flujo General

> **Fuente:** Nitor Infotech – _Steps to Start with Spec-Driven Development_.

<p align="center">
  <img
    src="https://www.nitorinfotech.com/wp-content/uploads/2025/12/steps-to-start-with-spec-driven-development-956x1024.webp"
    alt="Steps to Start with Spec-Driven Development"
    width="600"
  />
</p>

```text
Idea
    ↓
Product Brief
    ↓
Arquitectura
    ↓
Specification
    ↓
Plan de implementación
    ↓
Implementación
    ↓
Testing
    ↓
Review
    ↓
Documentación
    ↓
Commit
```

---

# Paso 1. Product Brief

Crear:

```
docs/00-product-brief.md
```

Contenido mínimo:

```md
# Nombre del proyecto

## Problema

¿Qué problema resuelve?

## Usuarios

¿Quién utilizará el sistema?

## Objetivo

¿Qué debe conseguir el usuario?

## MVP

Lista de funcionalidades mínimas.

## Fuera de alcance

Qué NO se implementará todavía.

## Riesgos

- Técnicos
- Seguridad
- Escalabilidad
- Legales
```

El objetivo es tener una visión clara antes de escribir una sola línea de código.

---

# Paso 2. Arquitectura

Crear:

```
docs/architecture.md
```

Ejemplo:

```md
# Arquitectura

## Stack

- Backend
- Frontend
- Base de datos
- Testing

## Organización

Controllers
Services
Repositories
Models
Policies
Middleware
Requests
Jobs

## Convenciones

- Controladores delgados
- Validaciones mediante Form Requests
- Servicios para lógica de negocio
- Tests obligatorios
```

Toda implementación deberá respetar esta arquitectura.

---

# Paso 3. Crear las Specifications

Cada funcionalidad importante debe tener una Specification independiente.

```
docs/specs/
```

Ejemplo:

```
docs/specs/

001-auth.md
002-users.md
003-dashboard.md
004-reports.md
```

Cada Specification debería contener:

```md
# Objetivo

# Requisitos funcionales

# Requisitos técnicos

# Casos de uso

# Casos límite

# Casos de prueba

# Criterios de aceptación
```

Nunca implementar una funcionalidad sin una Specification.

---

# Paso 4. Definir las reglas para la IA

Crear:

```
AGENTS.md
```

o

```
.cursor/rules/project.md
```

Ejemplo:

```md
Trabaja siguiendo Spec-Driven Development.

Antes de modificar código:

1. Leer la Specification.
2. Leer la Arquitectura.
3. Proponer un plan.
4. Implementar en pequeños pasos.
5. Añadir tests.
6. Ejecutar pruebas.
7. Documentar cambios.

Reglas:

- No duplicar lógica.
- No introducir deuda técnica.
- No modificar arquitectura sin justificarlo.
- Mantener los controladores simples.
- Mantener los tests en verde.
```

---

# Paso 5. Planificar antes de programar

No pedir:

> Implementa esta funcionalidad.

Pedir:

```
Lee la documentación del proyecto.

Resume la Specification.

Propón un plan de implementación.

Indica qué archivos modificarás.

Explica posibles riesgos.

No escribas código todavía.
```

Cuando el plan sea correcto:

```
Implementa el plan paso a paso.

Después ejecuta los tests.

Finalmente resume todos los cambios realizados.
```

---

# Paso 6. Implementación

La IA implementa respetando:

- Arquitectura
- Convenciones
- Specifications
- Tests

Cada cambio debe ser:

- pequeño
- verificable
- reversible

---

# Paso 7. Testing

Toda funcionalidad debería incluir:

- Tests unitarios
- Tests de integración
- Casos negativos
- Casos límite

Objetivo:

✅ Suite completamente en verde.

---

# Paso 8. Review

Antes del commit revisar:

- Código duplicado
- Complejidad
- Seguridad
- Rendimiento
- Arquitectura
- Cobertura de tests
- Convenciones

---

# Paso 9. Documentación

Actualizar cuando sea necesario:

```
README.md

docs/

ADR/

CHANGELOG
```

La documentación forma parte del desarrollo.

---

# Paso 10. Commit

Realizar commits pequeños.

Ejemplos:

```
feat(auth): implement login flow

refactor(users): extract validation to Form Requests

test(applications): add mutator regression tests

docs(spec): update validation specification
```

---

# Checklist de una Feature

Antes de dar por terminada una funcionalidad:

- [ ] Product Brief actualizado
- [ ] Specification creada
- [ ] Arquitectura revisada
- [ ] Plan validado
- [ ] Implementación completada
- [ ] Tests añadidos
- [ ] Suite en verde
- [ ] Review realizada
- [ ] Documentación actualizada
- [ ] Commit realizado

---

# ADR (Architecture Decision Records)

Toda decisión importante debería registrarse.

Ejemplo:

```
docs/decisions/

ADR-001-use-laravel.md

ADR-002-authentication.md

ADR-003-cache-strategy.md
```

Un ADR explica:

- Contexto
- Problema
- Alternativas
- Decisión
- Consecuencias

---

# Estructura recomendada

```
project/

docs/
│
├── 00-product-brief.md
├── architecture.md
├── specs/
├── decisions/
├── changelog/
└── diagrams/

AGENTS.md

README.md

src/

tests/
```

---

# Principios

- No programar sin una Specification.
- La arquitectura guía el desarrollo.
- La IA implementa; el desarrollador decide.
- Todo cambio debe ser verificable.
- Los tests forman parte de la implementación.
- La documentación evoluciona junto con el código.
- Cada sprint debe dejar el proyecto mejor que antes.

---

# Diagrama de referencia

<p align="center">
  <em>Figura 1. Flujo general de trabajo en Spec-Driven Development.</em>
</p>

<p align="center">
  <img
    src="https://miro.medium.com/v2/resize:fit:1400/1*JFkQec4-3IlKbn-TnVxWgQ.png"
    alt="Spec-Driven Development Workflow"
    width="900"
  />
</p>

---

# Recursos recomendados

## Artículos

- Nitor Infotech – Steps to Start with Spec-Driven Development

## Vídeos

### Vibe Coding

[![Vibe Coding](https://img.youtube.com/vi/uquw8yUKaYM/maxresdefault.jpg)](https://www.youtube.com/watch?v=uquw8yUKaYM)

---

# Referencias

- https://www.nitorinfotech.com/
- https://medium.com/
- https://www.youtube.com/watch?v=uquw8yUKaYM

---

<div align="center">

## Izan Carlo Celis Afonso

**Learning Repository**

_Software Engineering • AI-Assisted Development • Spec-Driven Development_

📚 Living Document • Continuously Updated

Última revisión: 2026-06-25

</div>
