# Senior Doc Architect 🏛️

**Senior Doc Architect** es una skill de IA diseñada para operar como un **Staff Software Engineer** en tu entorno de desarrollo. Su misión es eliminar la "burocracia técnica" automatizando la creación de documentación de arquitectura, registros de decisiones (ADR) y mensajes de commit de alta calidad.

> "El código dice *qué*, pero esta skill explica el *por qué*."

---

## ✨ Características Principales

### 🧠 Mentalidad de Arquitecto (ADR)
Detecta cambios estructurales y propone la creación de **Architecture Decision Records (ADR)** siguiendo la plantilla de Michael Nygard. Analiza automáticamente:
* **Contexto de negocio:** Justifica el cambio frente a necesidades del producto.
* **Trade-offs técnicos:** Identifica honestamente lo que ganamos vs. lo que sacrificamos (acoplamiento, complejidad, latencia).
* **Impacto a largo plazo:** Evalúa la mantenibilidad futura.

### 📊 Documentación Viva (C4 Model)
Mantiene la visión global del sistema. Si añades servicios o cambias flujos de datos, la skill genera o actualiza diagramas **Mermaid.js** basados en el estándar **C4 Model** (Nivel 2/3).

### 🛠️ Excelencia en Git (Conventional Commits)
* Genera mensajes bajo el estándar **Conventional Commits** (feat, fix, perf, refactor).
* Vincula automáticamente los commits con sus respectivos ADRs (Ref: ADR-XXX).
* Redacta descripciones de Pull Request con impacto técnico y guía de pruebas.

### 🚀 DevEx & Onboarding
Monitoriza cambios en .env.example, package.json o Dockerfile y mantiene actualizado el CONTRIBUTING.md para que el setup de nuevos desarrolladores sea siempre funcional.

---

## 🛠️ Instalación

Si utilizas el CLI de skills.sh, puedes añadir esta habilidad a tu agente local:

```npx skills add https://github.com/Zugarramurdi/senior-doc-architect```

---

## 📋 Flujo de Trabajo (Workflow)

La skill opera en tres fases para garantizar que siempre tengas el control total:

1.  **Observación:** Analiza los cambios en tu *staging area* o sesión actual.
2.  **Dry Run (Validación):** Te presenta un resumen de los ADRs y cambios documentales **antes** de escribirlos en disco. Validarás los trade-offs aquí.
3.  **Ejecución:** Tras tu confirmación (Sí), persiste los archivos .md y prepara los comandos de Git.

---

## 📖 Ejemplo de Uso Real

**Contexto:** Has optimizado un fetch de datos en el Dashboard para evitar un problema de N+1.

**Salida de la Skill:**
> "He detectado una migración de *Client Fetching* a *Bulk Data Fetching* en el Server Component.
> 
> **ADR-001 Propuesto:**
> - **Positivo:** Reducción del 95% en carga HTTP.
> - **Negativo:** Aumento del acoplamiento entre la página padre y el componente AddToListButton.
> 
> **Commit Sugerido:**
> (git commit -m "perf(wishlist): migrate to bulk data fetching. Ref: ADR-001")"

---

## 📂 Estructura Generada

La skill organiza el conocimiento de tu repositorio de forma estandarizada:

* /docs/adr/: Registro histórico de decisiones técnicas.
* /docs/changelog/: Diario técnico incremental (no solo de versión, sino de lógica).
* /docs/architecture.md/: Diagramas visuales en Mermaid.

---

## 🤝 Contribuciones

Si quieres mejorar las plantillas de documentación o añadir soporte para un stack específico (Java, Rust, Go, etc.), los Pull Requests son bienvenidos.

---

**Desarrollado para impulsar la cultura de ingeniería.** 🚀