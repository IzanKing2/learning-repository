# Guía Maestra: Estructuración de Proyectos para Spec-Driven Development

## Introducción

En el ecosistema tecnológico de 2026, la ingeniería de software ha dejado de ser una disciplina de escritura para convertirse en una disciplina de **orquestación estratégica**.

El programador _Old School_, centrado en la sintaxis y el picado de líneas, es hoy un perfil de alto riesgo para la escalabilidad de cualquier sistema.

Como Ingeniero Principal, la función ha evolucionado:

> Ya no escribes código.
> Diseñas especificaciones que agentes autónomos ejecutan.

Sin embargo, esta potencia agéntica es un arma de doble filo. Se rige por una ley matemática inmutable:

```text
0 x 100 = 0
```

Si tus fundamentos de ingeniería son nulos, no importa que la IA multiplique tu productividad por cien: el resultado seguirá siendo cero.

Esta guía establece el estándar para evitar el colapso arquitectónico y dominar el flujo profesional de desarrollo.

---

## 1. El Cambio de Paradigma: Del Programador al Orquestador

El auge del **Vibe Coding**, es decir, programar basándose en intuiciones y prompts vagos, ha inundado el mercado de lo que denominamos **Cacware** o **Sheetware**:

> Software que funciona a primera vista, pero que esconde una deuda técnica catastrófica y una rotura arquitectónica inminente.

El orquestador profesional rechaza el azar.

Mientras que el aficionado vibra con el código, el arquitecto mitiga riesgos mediante una estructura determinista.

### Beneficios del flujo profesional SDD

- **Mitigación de la deuda técnica**
  La IA sigue patrones de diseño rigurosos, no atajos temporales.

- **Determinismo arquitectónico**
  El sistema se construye bajo una visión global, no como una acumulación de parches.

- **Optimización de recursos**
  Reducción del desperdicio de tokens y prevención de alucinaciones mediante el control de la ventana de contexto.

- **Escalabilidad profesional**
  Capacidad de gestionar millones de líneas de código sin que el sistema se vuelva inmanejable por amnesia agéntica.

Este cambio exige que los artefactos documentales dejen de ser un extra para convertirse en el núcleo del desarrollo.

---

## 2. El Flujo de Trabajo SDD: Ciclo de Vida del Desarrollo Agéntico

El **Spec-Driven Development**, o **SDD**, profesional se divide en tres estados de madurez.

El objetivo final es alcanzar el **Spec as Source**, donde el humano solo interviene en la especificación y la IA se encarga de la totalidad del código, tratándolo como un subproducto automático.

### Estados de madurez del SDD

| Estado             | Descripción                                                                         |
| ------------------ | ----------------------------------------------------------------------------------- |
| **Spec First**     | Definición exhaustiva de requisitos antes de invocar cualquier modelo.              |
| **Spec Anchor**    | Sincronización bidireccional entre la documentación y el código generado.           |
| **Spec as Source** | La especificación es la única fuente de verdad; el código es un artefacto derivado. |

---

## El Ciclo Agéntico Moderno

Para maximizar la eficiencia de costes y precisión, debemos separar el razonamiento de la ejecución.

### 1. Fase de Planificación: Plan Mode

Utilizar modelos razonadores para analizar la arquitectura.

Ejemplos:

- Claude 3.7
- o1
- Modelos orientados a razonamiento profundo

En esta etapa, el agente puede desplegar sub-agentes efímeros que exploran el codebase sin modificarlo.

Objetivo:

- Comprender el sistema.
- Detectar dependencias.
- Identificar riesgos.
- Proponer un plan antes de tocar archivos.

### 2. Fase de Ejecución: Act Mode

Una vez validado el plan, se delega en modelos más rápidos y económicos para realizar los cambios físicos en los archivos.

Objetivo:

- Modificar código.
- Crear archivos.
- Ejecutar comandos.
- Aplicar refactors.
- Implementar tareas atómicas.

### 3. Validación y Refactor

Los agentes autoevalúan su salida mediante tests automáticos antes de presentar el cambio al humano.

Este flujo mantiene al humano dentro del proceso mediante el enfoque:

> **Human-in-the-loop**

---

## 3. El Documento de Especificaciones: Project DNA

La especificación es el ancla que previene la lobotomía de la IA en sesiones largas.

Este documento debe obligar al agente a seguir patrones sólidos como:

- Clean Architecture
- Vertical Slice
- Separación de responsabilidades
- Testing preventivo
- Seguridad por diseño

---

## Plantilla Maestra de Especificación

Archivo recomendado:

```text
spec.md
```

```markdown
# Especificación Técnica: [Nombre del Módulo]

## 1. Contexto y Comportamiento Esperado

- **Problema:** [Descripción detallada del problema]
- **Objetivo:** [Resultado esperado]
- **User Flow:** [Pasos exactos del usuario]
- **Criterios de éxito:** [Condiciones verificables]

## 2. Arquitectura y Patrones

- **Patrón principal:** Clean Architecture / Vertical Slice
- **Estructura:** Separación clara entre Dominio, Aplicación e Infraestructura
- **Contexto global:** Vincular con `agent.md` para convenciones del proyecto

## 3. Stack Tecnológico

- **Frontend:** [Framework y versión]
- **Backend:** [Framework y versión]
- **Persistencia:** [Base de datos, ORM y esquema]
- **Testing:** [Frameworks de testing]
- **Infraestructura:** [Docker, CI/CD, cloud, etc.]

## 4. Funcionalidades Detalladas

- [ ] Requerimiento A
  - Criterio de aceptación técnica:
  - Casos borde:
  - Tests requeridos:

- [ ] Requerimiento B
  - Criterio de aceptación técnica:
  - Casos borde:
  - Tests requeridos:

## 5. Restricciones Técnicas

- Ningún archivo debe exceder las 500 líneas.
- No se permite lógica de negocio en controladores.
- No se permite acceso directo a infraestructura desde dominio.
- No se permite introducir librerías externas sin aprobación previa.

## 6. Seguridad

- Uso obligatorio de Argon2 para hashes.
- JWT con rotación.
- Validación estricta de inputs.
- No exponer secretos en logs.
- No hardcodear credenciales.

## 7. Definition of Done

- [ ] Tests unitarios creados.
- [ ] Tests de integración creados.
- [ ] Linter ejecutado.
- [ ] Build exitoso.
- [ ] Documentación actualizada.
- [ ] Revisión de seguridad completada.
```

---

## 4. Gestión de Tareas y Ventana de Contexto

El contexto de un millón de tokens puede ser engañoso.

> Es como gasolina dentro de una casa: si no se gestiona, genera ruido, calor y finalmente un incendio de alucinaciones.

Para evitar esto, se utilizan dos estrategias principales:

- Fragmentación de tareas.
- Git Worktrees.

---

## Git Worktrees para Orquestación Paralela

El uso de **Git Worktrees** permite aislar a diferentes agentes o sub-agentes en carpetas físicas separadas que apuntan a distintas ramas.

Esto evita:

- Colisiones entre agentes.
- Mezcla de contextos.
- Conflictos innecesarios.
- Degradación del razonamiento.
- Cambios cruzados difíciles de revisar.

Ejemplo conceptual:

```text
project/
├── main/
├── worktree-auth-agent/
├── worktree-security-review/
└── worktree-frontend-agent/
```

---

## Task List Agéntico

Archivo recomendado:

```text
tasks.md
```

```markdown
# Task List Agéntico

| Estado | ID   | Tarea Técnica             | Ficheros              | Verificación                     |
| ------ | ---- | ------------------------- | --------------------- | -------------------------------- |
| 🚧     | T-01 | Implementar Auth Provider | `auth.service.ts`     | Test unitario con cobertura >90% |
| ⏳     | T-02 | Crear validación JWT      | `jwt.validator.ts`    | Tests de expiración y firma      |
| ⏳     | T-03 | Añadir endpoint login     | `login.controller.ts` | Test de integración exitoso      |
| ✅     | T-04 | Crear modelo de usuario   | `user.entity.ts`      | Build y tests correctos          |
```

### Estados recomendados

| Estado | Significado                    |
| ------ | ------------------------------ |
| ⏳     | Pendiente                      |
| 🚧     | En progreso                    |
| 👀     | En revisión                    |
| ✅     | Completado                     |
| ❌     | Bloqueado                      |
| 🔐     | Requiere revisión de seguridad |

---

## 5. Estrategias de Prompting: Chain of Thought

En 2026, el prompting básico ha muerto.

Los modelos razonadores requieren un enfoque basado en análisis, descomposición y validación.

No pedimos:

```text
Haz un login.
```

Exigimos:

```text
Analiza los riesgos, diseña la solución, valida restricciones y luego implementa.
```

---

## Ejemplo de Prompt Maestro

```text
Actúa como un Senior Security Engineer.

Realiza un análisis para implementar un sistema de autenticación.

Objetivos:

1. Analiza los riesgos de inyección, sesión y autorización en el stack [X].
2. Diseña un esquema de validación utilizando JWT y Argon2.
3. Genera el código siguiendo el patrón Vertical Slice definido en `spec.md`.
4. Separa la lógica de hashing en un servicio de infraestructura independiente.
5. Añade tests unitarios y de integración.
6. No modifiques archivos fuera del alcance definido en `tasks.md`.
7. Antes de implementar, presenta un plan técnico para aprobación.
```

---

## 6. Configuración del Archivo `agent.md`: El Índice de la Verdad

El archivo `agent.md` es el ADN operativo del proyecto.

No es una lista de deseos. Es un registro de ejecución que actúa como **Index of Truth** para el agente.

Conecta al agente con:

- Reglas del proyecto.
- Convenciones técnicas.
- Comandos válidos.
- Herramientas externas.
- MCPs disponibles.
- Skills activas.
- Memoria persistente.

---

## Plantilla de `agent.md`

````markdown
# Reglas del Proyecto: [Nombre]

## 1. Estándares de Ingeniería

- TypeScript Strict Mode obligatorio.
- No side effects en funciones de dominio.
- No lógica de negocio en controladores.
- No acceso directo a base de datos desde la capa de dominio.
- Mantener archivos por debajo de 500 líneas.
- Preferir composición sobre herencia.

## 2. Arquitectura

- Usar Clean Architecture.
- Usar Vertical Slice para nuevas funcionalidades.
- Separar Dominio, Aplicación e Infraestructura.
- Cada caso de uso debe tener tests asociados.

## 3. Comandos del Proyecto

- Instalar dependencias:

```bash
npm install
```
````

- Ejecutar tests:

```bash
npm run test
```

- Ejecutar linter:

```bash
npm run lint
```

- Ejecutar build:

```bash
npm run build
```

## 4. Registro de Capacidades

- **MCPs conectados:** Supabase, Notion, GitHub.
- **Skills activas:** `TDD-Skill`, `Security-Audit-Skill`.
- **Memoria:** Consultar `Engram` antes de proponer cambios arquitectónicos.

## 5. Prohibiciones

- No instalar dependencias sin aprobación.
- No cambiar arquitectura global sin registrar decisión.
- No ignorar tests fallidos.
- No modificar secretos, `.env` o credenciales.
- No generar código sin actualizar documentación asociada.

## 6. Definition of Done Global

- Tests verdes.
- Linter correcto.
- Build exitoso.
- Documentación actualizada.
- Sin secretos expuestos.
- Cambios alineados con `spec.md`.

````

---

## 7. Integraciones Avanzadas: MCP, Skills y Engram

Para resolver la amnesia entre sesiones, el orquestador utiliza herramientas de persistencia de conocimiento.

### Model Context Protocol

El **Model Context Protocol**, o **MCP**, actúa como puente hacia las fuentes de verdad.

Permite que la IA consulte información real en tiempo de ejecución.

Ejemplos:

- Esquemas reales en Supabase.
- Requerimientos en Notion.
- Issues en GitHub.
- Documentación externa.
- Estado de APIs.
- Datos del producto.

### Skills

Las **Skills** son comportamientos arquitectónicos reutilizables.

Ejemplos:

- Skill de TDD.
- Skill de auditoría de seguridad.
- Skill de diseño frontend.
- Skill de refactorización.
- Skill de documentación técnica.
- Skill de revisión de arquitectura.

### Engram

**Engram** funciona como cerebro persistente del proyecto.

No almacena únicamente acciones pasadas, sino el razonamiento detrás de las decisiones.

Debe registrar:

- Decisiones arquitectónicas.
- Errores aprendidos.
- Patrones aprobados.
- Prohibiciones históricas.
- Causas raíz de bugs.
- Motivos de elección tecnológica.

Ejemplo:

```text
Decisión:
Usar Argon2 para hashing de contraseñas.

Motivo:
Mejor resistencia frente a ataques de fuerza bruta que algoritmos rápidos.

Implicación:
Todo servicio de autenticación debe delegar hashing en infraestructura.
````

---

## 8. Calidad y Producción: Seguridad y CI/CD

La responsabilidad final es humana.

Un flujo profesional de CI/CD debe incluir a la IA no solo como creadora, sino también como auditora.

---

## Flujo Profesional Recomendado

### 1. Human-in-the-loop

Toda Pull Request requiere revisión humana.

La IA puede validar:

- Sintaxis.
- Tests.
- Cobertura.
- Vulnerabilidades.
- Consistencia documental.

El humano valida:

- Lógica de negocio.
- Arquitectura.
- Riesgos.
- Impacto real.
- Coherencia estratégica.

### 2. Security Review Agéntico

Integrar agentes en GitHub Actions para realizar auditorías automáticas en cada commit.

Deben buscar:

- Secretos expuestos.
- Dependencias vulnerables.
- Patrones inseguros.
- Falta de validación de inputs.
- Problemas de autorización.
- Inyecciones.
- Exposición de datos sensibles.

### 3. Release Please

Automatizar versionado y generación de notas de lanzamiento.

Objetivo:

- Crear changelogs semánticos.
- Traducir cambios técnicos a lenguaje de negocio.
- Mantener trazabilidad.
- Reducir errores manuales en releases.

---

## 9. Conclusión: La Ingeniería en la Era del Slop

El futuro del desarrollo no es la desaparición del programador, sino la extinción del picacódigo mediocre.

El mercado se está inundando de **Slop**:

> Código basura generado por IA sin supervisión, sin intención arquitectónica y sin criterio técnico.

En este contexto, el valor del ingeniero reside en su capacidad para ser el filtro de calidad.

El éxito en esta nueva era se resume en una máxima:

> El mejor programador con IA es aquel que posee los conocimientos suficientes para no necesitarla, pero la sabiduría necesaria para utilizarla como multiplicador de fuerza.

Domina la especificación.

Controla el contexto.

Nunca cedas el volante de la arquitectura.

---

## Resumen Final

El Spec-Driven Development no consiste en escribir prompts mejores.

Consiste en construir un sistema donde:

- La especificación guía.
- La arquitectura limita.
- Los agentes ejecutan.
- Los tests protegen.
- La memoria persiste.
- El humano decide.

> La IA puede escribir código.
> El orquestador diseña sistemas.
