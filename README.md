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
* **Reader Testing (Onboarding Friendly):** Actúa como un filtro de legibilidad. La skill detecta "conocimiento tribal" o asunciones complejas y añade aclaraciones para que cualquier desarrollador nuevo entienda la documentación sin ayuda externa.

### 📊 Documentación Viva (C4 Model)
Mantiene la visión global del sistema. Si añades servicios o cambias flujos de datos, la skill genera o actualiza diagramas **Mermaid.js** basados en el estándar **C4 Model** (Nivel 2/3).

### 🛡️ Seguridad y Robustez (Security First)
* **Zero Leak Policy:** Monitorea cambios en variables de entorno. Nunca documenta secretos reales; genera automáticamente archivos `.env.example` con valores ficticios.
* **Flexibilidad Visual:** No se limita a C4. Prioriza **Diagramas de Secuencia o Estado** para lógicas de negocio complejas cuando aportan más claridad.

### 🛠️ Excelencia en Git (Conventional Commits)
* Genera mensajes bajo el estándar **Conventional Commits** (feat, fix, perf, refactor).
* **Commits Atómicos:** Si detecta un commit que mezcla lógicas distintas (ej: fix + feat) o es demasiado grande, sugerirá dividirlo antes de proceder.
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

1.  **Observación:** Analiza los cambios en tu *staging area*, busca posibles fallos de seguridad o mezclas de lógica (anti-patterns).
2.  **Dry Run (Validación):** Te presenta un resumen de los ADRs, diagramas y la **Guía de Pruebas**. En este paso, aplica el **Reader Testing** para asegurar que el contenido sea auto-explicativo.
3.  **Ejecución:** Tras tu confirmación, persiste los archivos o usa el **Modo Fallback** (genera el código con la ruta comentada si no hay permisos de escritura).

---

## 📖 Ejemplo de Uso Real

**Contexto:** Has optimizado un fetch de datos en el Dashboard para evitar un problema de N+1 y has añadido una variable de entorno para la API Key.

**Salida de la Skill:**
> "He detectado una migración a *Bulk Data Fetching* y una nueva configuración de entorno. He actualizado el `.env.example` con valores ficticios para proteger tus secretos.
> 
> **ADR-001 Propuesto:**
> - **Decisión:** Implementación de Fetching Masivo en Dashboard.
> - **Trade-off:** Reducción del 95% en carga HTTP vs. aumento del acoplamiento en componentes padre.
> 
> **👥 Reader Testing:** He añadido una nota aclaratoria sobre el origen de la `DASHBOARD_API_KEY` para que un desarrollador nuevo sepa que debe solicitarla al equipo de Infraestructura, evitando 'conocimiento tribal'.
> 
> **Cómo Probar:** > 1. Configurar la clave ficticia en el `.env` local. 
> 2. Abrir la pestaña *Network* y verificar que solo se realiza una petición al cargar el Dashboard.
> 
> **Commit Sugerido (Anti-Pattern Check: OK):**
> (git commit -m "perf(dashboard): migrate to bulk data fetching to fix N+1. Ref: ADR-001")"

---

## 📂 Estructura Generada

La skill organiza el conocimiento de tu repositorio de forma estandarizada:

* /docs/adr/: Registro histórico de decisiones técnicas.
* /docs/changelog/: Diario técnico incremental (no solo de versión, sino de lógica).
* `/docs/architecture/`: Diagramas visuales (C4, Secuencia, Estados).
* `.env.example`: Plantilla segura de configuraciones del proyecto.

---

## 🤝 Contribuciones

Si quieres mejorar las plantillas de documentación o añadir soporte para un stack específico (Java, Rust, Go, etc.), los Pull Requests son bienvenidos.

---

**Desarrollado para impulsar la cultura de ingeniería.** 🚀

---

Edited by GLaDOS. 🦾