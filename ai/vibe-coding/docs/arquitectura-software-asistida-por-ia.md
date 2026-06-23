# Arquitectura de Software Asistida por Inteligencia Artificial

## Introducción

La ingeniería de software moderna ya no consiste únicamente en escribir código.

En la era de los agentes autónomos y los entornos AI-Native, el valor profesional reside en diseñar sistemas, especificar comportamientos y controlar la ejecución automatizada.

La Inteligencia Artificial puede multiplicar la productividad de un equipo, pero también puede amplificar errores arquitectónicos, deuda técnica y vulnerabilidades de seguridad.

Por este motivo, el desarrollo profesional asistido por IA requiere un enfoque estructurado basado en:

- Especificaciones precisas.
- Reglas arquitectónicas explícitas.
- Contexto controlado.
- Herramientas de integración.
- Supervisión humana.

Esta guía describe el flujo recomendado para construir software profesional mediante agentes de IA.

---

# Paso 1: Redactar las Especificaciones del Proyecto (Spec-Driven Development)

Antes de interactuar con cualquier modelo de IA para generar código, el arquitecto u orquestador debe crear documentos de requerimientos detallados.

La metodología **Spec-Driven Development (SDD)** establece que la especificación es el activo principal del proyecto.

La especificación funciona como:

- Fuente de verdad.
- Contrato técnico.
- Contexto compartido.
- Mecanismo anti-alucinación.

### Principio Fundamental

> La IA no debe decidir qué construir.
> La IA debe ejecutar una especificación previamente definida.

---

## Objetivos de la Especificación

La documentación debe describir de forma explícita:

### Problema de Negocio

- Qué problema resuelve el software.
- Quién es el usuario.
- Qué valor aporta.

### Stack Tecnológico

- Frontend.
- Backend.
- Base de datos.
- Infraestructura.
- Testing.
- CI/CD.

### Requerimientos Funcionales

- Casos de uso.
- Flujos de usuario.
- Restricciones.
- Reglas de negocio.

### Requerimientos Técnicos

- Arquitectura.
- Patrones.
- Seguridad.
- Escalabilidad.

### Lista de Tareas

- Funcionalidades.
- Dependencias.
- Criterios de aceptación.

---

## Beneficio Principal

Una especificación bien diseñada entrega un contexto cerrado.

Esto evita que la IA:

- Invente funcionalidades.
- Asuma requisitos inexistentes.
- Modifique comportamientos inesperados.
- Rompa restricciones arquitectónicas.

---

# Paso 2: Centralizar las Reglas de Arquitectura en un Archivo AGENTS.md

La IA no debe programar guiándose por intuición.

Toda decisión técnica debe estar respaldada por reglas explícitas almacenadas en un archivo central.

Archivo recomendado:

```text
AGENTS.md
```

o

```text
agent.md
```

Este documento actúa como la constitución técnica del proyecto.

---

## Información Obligatoria

### Stack Tecnológico

Ejemplo:

```text
Frontend: Next.js 15
Backend: NestJS
Base de datos: PostgreSQL
ORM: Prisma
```

---

### Convenciones de Código

Ejemplo:

```text
- TypeScript Strict Mode
- ESLint obligatorio
- Prettier obligatorio
- Nombres descriptivos
```

---

### Patrones Arquitectónicos

Ejemplo:

```text
- Clean Architecture
- Vertical Slice
- CQRS
- Dependency Injection
```

---

### Restricciones Técnicas

Ejemplo:

```text
- No lógica de negocio en controladores.
- No acceso directo a base de datos desde dominio.
- No librerías sin aprobación.
```

---

### Flujo de Trabajo

Ejemplo:

```text
1. Planificar.
2. Aprobar.
3. Implementar.
4. Testear.
5. Revisar.
```

---

## Beneficio Principal

Mantener a todos los agentes alineados con las mismas reglas.

Sin reglas:

```text
Cada agente improvisa.
```

Con reglas:

```text
Todos los agentes trabajan bajo el mismo marco arquitectónico.
```

---

# Paso 3: Modularizar el Contexto Mediante Skills

Uno de los principales problemas del desarrollo asistido por IA es la pérdida progresiva de contexto.

A medida que aumenta el tamaño del proyecto:

- Crecen las instrucciones.
- Crece la documentación.
- Aumenta el ruido contextual.

Esto puede provocar:

- Olvido de reglas.
- Inconsistencias.
- Alucinaciones.
- Comportamientos contradictorios.

---

## Solución: Skills

Las Skills permiten dividir el conocimiento en módulos especializados.

Cada Skill contiene instrucciones específicas para una tarea concreta.

Ejemplos:

```text
skills/
├── frontend-ui.md
├── pull-request.md
├── testing.md
├── security-review.md
├── database-design.md
└── deployment.md
```

---

## Función del AGENTS.md

El archivo principal no debe contener toda la información.

Debe actuar como índice.

Ejemplo:

```text
Si se modifica la base de datos:
→ cargar database-design.md

Si se genera una PR:
→ cargar pull-request.md

Si se crean tests:
→ cargar testing.md
```

---

## Beneficios

- Menor consumo de contexto.
- Mejor precisión.
- Menos ruido.
- Mayor escalabilidad.
- Menos amnesia agéntica.

---

# Paso 4: Conectar la IA al Entorno Real Usando MCP

La IA suele alucinar cuando necesita interactuar con servicios externos que no están presentes en el repositorio local.

Ejemplos:

- Bases de datos remotas.
- APIs.
- Sistemas SaaS.
- Documentación corporativa.

---

## Solución: Model Context Protocol (MCP)

El MCP funciona como un puente entre la IA y los sistemas externos.

Permite acceso en tiempo real a:

- Bases de datos.
- APIs.
- Notion.
- GitHub.
- Supabase.
- Documentación técnica.

---

## Beneficios

### Información Actualizada

La IA consulta datos reales.

### Menos Alucinaciones

No necesita inventar esquemas o contratos.

### Mejor Calidad

El código generado se ajusta al entorno real.

---

## Ejemplo

Sin MCP:

```text
La IA supone cómo es la tabla users.
```

Con MCP:

```text
La IA consulta la tabla users real antes de escribir código.
```

---

# Paso 5: Utilizar el Modo Plan para Validar Antes de Ejecutar

Un orquestador profesional nunca permite que un agente modifique archivos sin validación previa.

La fase más importante es:

```text
Plan Mode
```

---

## Qué Hace el Plan Mode

Antes de escribir código, la IA debe:

1. Analizar el proyecto.
2. Comprender dependencias.
3. Revisar arquitectura.
4. Detectar riesgos.
5. Proponer un plan.

---

## Flujo Recomendado

```text
Solicitud
    ↓
Plan Mode
    ↓
Validación Humana
    ↓
Agent Mode
    ↓
Implementación
```

---

## Beneficio Principal

Detectar errores antes de modificar el sistema.

---

## Ejemplo de Salida Esperada

```text
Plan:

1. Crear servicio AuthService.
2. Implementar JWT Provider.
3. Crear tests unitarios.
4. Añadir endpoint login.
5. Ejecutar pipeline.
```

Solo tras la aprobación humana:

```text
Agent Mode → Ejecutar.
```

---

# Paso 6: Gobernar el Acceso a los Modelos de IA Según la Tarea

No todas las tareas requieren el mismo nivel de razonamiento.

Asignar el modelo adecuado a cada actividad mejora:

- Calidad.
- Costes.
- Velocidad.
- Seguridad.

---

## Modelos de Arquitectura

Utilizar modelos especializados para:

- Diseño.
- Arquitectura.
- Seguridad.
- Planificación.

Ejemplos:

```text
Claude Sonnet
OpenAI Codex
Modelos de razonamiento profundo
```

---

## Modelos de Ejecución

Utilizar modelos más rápidos para:

- Refactors simples.
- Creación de tests.
- Documentación.
- Modificaciones repetitivas.

---

## Gobernanza Empresarial

En entornos corporativos se recomienda:

### Control de Modelos

Definir qué modelos pueden utilizarse.

### BYOK (Bring Your Own Key)

Uso de claves corporativas propias.

### Políticas de Seguridad

Aplicar restricciones organizacionales.

### Auditoría

Registrar qué modelo generó cada cambio.

---

## Beneficios

- Costes controlados.
- Calidad consistente.
- Cumplimiento normativo.
- Mayor trazabilidad.

---

# Arquitectura Recomendada del Repositorio

```text
project/
│
├── AGENTS.md
├── spec.md
├── tasks.md
│
├── skills/
│   ├── frontend-ui.md
│   ├── testing.md
│   ├── security-review.md
│   └── deployment.md
│
├── docs/
│   ├── architecture.md
│   ├── decisions.md
│   └── diagrams.md
│
├── src/
│
├── tests/
│
└── .github/
    └── workflows/
```

---

# Conclusión

La Inteligencia Artificial no elimina la necesidad de arquitectura.

La amplifica.

Cuanto más poder tienen los agentes, más importante se vuelve la especificación, la gobernanza y el control del contexto.

El desarrollo profesional asistido por IA se fundamenta en seis pilares:

1. Especificaciones rigurosas.
2. Reglas arquitectónicas centralizadas.
3. Skills especializadas.
4. Integración mediante MCP.
5. Validación previa con Plan Mode.
6. Gobernanza de modelos.

La IA puede generar código.

Pero la responsabilidad de construir sistemas sostenibles, seguros y escalables sigue perteneciendo al arquitecto.

> El software profesional no nace de prompts mágicos.
> Nace de especificaciones claras, arquitectura sólida y supervisión constante.
