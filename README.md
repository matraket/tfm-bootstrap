<p align="center">
  <img src="assets/banner-tfm-bootstrap.png" alt="tfm-bootstrap banner" width="100%" />
</p>

# tfm-bootstrap

### Máster de Desarrollo con IA de BIG School - Trabajo de Fin de Máster

---

Mi nombre es Adrián Cester. Soy *"Pseudo-Ingeniero de Software"* en la *España vaciada* desde el 13 de junio de 2008, día en el que entré en mi empresa a cursar 6 créditos optativos. Fundada en 1987, lleva casi 40 años solucionando problemas reales de sus clientes con solvencia demostrable. Eso sí, anclada en el *legacy first* y con sus trabajadores manejando con soltura todo tipo de anti-patrones:

- **Napkin-Driven Development (NDD):** la especificación del sistema vive en una servilleta de bar, fotografiada con el móvil y compartida por WhatsApp. Si se pierde, se pierde el proyecto.
- **Folklore-Driven Development (FDD):** las reglas de negocio no están en el código, están en la memoria de quien lleva aquí desde 2009. Qué risas cuando está de vacaciones.
- **Hot-Driven Development (HDD):** no hay tests, no hay staging, no hay red de seguridad. Todo se despliega en caliente, directamente a producción. Si funciona, es mérito del equipo. Si no, antes era culpa del servidor; ahora, de ChatGPT.

El resultado se parece a un Ferrari: corre casi tanto, gusta casi tanto, impacta casi tanto. Pero no le abras el capó, porque lo que encontrarás es un motor de seiscientos lleno de alambres y chicles al más puro estilo *"MacGyver"*.

Quizás es momento de cambiar ese rumbo. Pues ya sabéis qué hago aquí. MaDIA es el punto de inflexión.

---

## Qué es este repositorio

Este no es un repositorio de código. Es el **punto de entrada** a un ecosistema de cuatro repositorios que, en conjunto, constituyen mi Trabajo de Fin de Máster.

Mi TFM no es una aplicación. Es una **metodología de desarrollo de software asistido por IA**, implementada a través de herramientas reales y validada contra un producto real. El producto podría haber sido cualquier otro - lo que importa es el flujo, las herramientas y el proceso.

---

## El problema que abordé

Durante el máster se trataron los fundamentos del desarrollo de software en profundidad, y eso fue enormemente valioso. Donde encontré una carencia fue en la aplicación de la inteligencia artificial al ciclo completo de desarrollo: muchas herramientas, todas interesantes, pero ninguna metodología transversal que las articulara.

No era un defecto del máster - era una consecuencia del momento. El ecosistema tampoco tenía respuestas claras.

Así que decidí buscar las mías. *My way.*

---

## El ecosistema

Cuatro repositorios. Un flujo. Una metodología.

```mermaid
graph LR
    A["seedspec<br/><em>Especificación trazable</em>"] --> B["doc-spec-pipeline<br/><em>Atomización para agentes</em>"]
    B --> C["Associated<br/><em>Producto real</em>"]
    D["docflow-skills<br/><em>Documentación automatizada</em>"] --> C

    C -->|"sesiones, cambios,<br/>releases"| D
    B -->|"spec navegable<br/>por agentes"| C

    style A fill:#5B7682,stroke:#3D5E6C,color:#fff
    style B fill:#5B7682,stroke:#3D5E6C,color:#fff
    style C fill:#27343E,stroke:#1A2329,color:#fff
    style D fill:#5B7682,stroke:#3D5E6C,color:#fff
```

### 1. seedspec - Planta una propuesta, cosecha un sistema

Metodología de expansión documental trazable: de la semilla del problema al MVP listo para implementar. Una propuesta inicial germina a través de 11 artefactos encadenados (requisitos funcionales, RNF, modelo de dominio, ADRs, stack, user stories, casos de uso) hasta convertirse en una especificación completa con trazabilidad de extremo a extremo.

> **[github.com/matraket/seedspec](https://github.com/matraket/seedspec)**

### 2. doc-spec-pipeline - Pipeline documental para agentes de IA

32.600 líneas de especificación no caben en una ventana de contexto. Este repositorio resuelve ese problema: transforma especificaciones extensas en fragmentos atómicos y navegables mediante dos skills complementarios (`doc-spec-generator` + `doc-spec-manager`). Generación determinista, sin dependencia de LLM, idempotente.

> **[github.com/matraket/doc-spec-pipeline](https://github.com/matraket/doc-spec-pipeline)**

### 3. docflow-skills - Documentación automatizada del desarrollo

Cadena de 3 skills que cierra el ciclo por el otro extremo: `session-manager` registra lo que ocurre en cada sesión de trabajo con IA, `changelog-updater` agrupa los cambios, y `release-generator` cierra versiones con trazabilidad completa. Porque si el agente no documenta lo que hace, nadie lo hará.

> **[github.com/matraket/docflow-skills](https://github.com/matraket/docflow-skills)**

### 4. Associated - El vehículo

ERP ligero para asociaciones culturales, cofradías, clubes deportivos y peñas festeras españolas. Es el proyecto donde converge todo: especificado con seedspec, consumido por agentes a través de doc-spec-pipeline, y documentado automáticamente con docflow-skills. Monolito modular, DDD, Clean Architecture, 6 Bounded Contexts.

> **[github.com/appassociated-dev/tfm-associated](https://github.com/appassociated-dev/tfm-associated)**

---

## En números

| Dimensión | Cifra |
|:----------|------:|
| Repositorios | 4 |
| Skills para agentes | 5 |
| Artefactos de especificación | 11 |
| Requisitos funcionales | 221 |
| Requisitos no funcionales | 66 |
| User Stories | 202 |
| Casos de uso | 76 |
| ADRs | 12 |
| Bounded Contexts | 6 |
| Líneas de especificación | ~32.600 |
| Referencias cruzadas entre documentos | ~1.800 |

---

## El flujo completo

```mermaid
graph TD
    S["Semilla<br/><em>Problema de negocio</em>"] --> SPEC["seedspec<br/><em>Expansión documental</em>"]
    SPEC --> CORPUS["Corpus completo<br/><em>221 RF · 66 RNF · 202 US · 76 UC</em>"]
    CORPUS --> PIPE["doc-spec-pipeline<br/><em>Atomización</em>"]
    PIPE --> REFS["Referencias navegables<br/><em>Fragmentos atómicos + índices</em>"]
    REFS --> DEV["Associated<br/><em>Desarrollo asistido</em>"]
    DEV --> FLOW["docflow-skills<br/><em>Sesiones · Changelog · Releases</em>"]
    FLOW -->|"trazabilidad"| DEV

    style S fill:#8CA1AA,stroke:#7A939E,color:#fff
    style SPEC fill:#5B7682,stroke:#3D5E6C,color:#fff
    style CORPUS fill:#3D5E6C,stroke:#27343E,color:#fff
    style PIPE fill:#5B7682,stroke:#3D5E6C,color:#fff
    style REFS fill:#3D5E6C,stroke:#27343E,color:#fff
    style DEV fill:#27343E,stroke:#1A2329,color:#fff
    style FLOW fill:#5B7682,stroke:#3D5E6C,color:#fff
```

---

## Reflexión

Lo que empecé buscando era un flujo de trabajo para mi día a día. En el proceso descubrí que no estaba solo: enfoques como *Spec-Driven Development* han ido materializando ideas muy similares. Lo que yo construí no es SDD - es mi camino hacia las mismas preguntas, recorrido desde la trinchera de una empresa de casi 40 años anclada en el legacy.

¿Es perfecto? No. ¿Es reproducible? Sí. ¿Me ha cambiado la forma de trabajar? Completamente.

> La historia completa, el contexto del máster, por qué tomé este camino y qué aprendí en el proceso está en el [Manifiesto](MANIFIESTO.md).

---

## Entregables

| Recurso | Enlace |
|:--------|:-------|
| Código | [github.com/appassociated-dev/tfm-associated](https://github.com/appassociated-dev/tfm-associated) |
| Despliegue | *Pendiente de enlace* |
| Presentación | *Pendiente de enlace* |

---

## Agradecimientos

Nada de esto habría pasado sin el claustro de MaDIA. Llegué al máster con 18 años de inercia profesional, convencido de que "lo que funciona no se toca". Me habéis obligado a cuestionarlo todo - y eso no tiene precio.

Gracias por el conocimiento, por la exigencia y por demostrar que se puede enseñar desarrollo de software sin dogmas.

A cada uno de vosotros, unas palabras:

- [Carta a Fulanito](cartas/fulanito.md)
- [Carta a Menganito](cartas/menganito.md)

---

> **Adrián Cester** · IPGSoft · MaDIA 2025–2026