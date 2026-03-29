status:: draft
public:: false
lang:: es
type:: note

- Para un Technical Paper en ASSETS, el outline suele funcionar cuando deja claro: (i) problema de accesibilidad situado, (ii) artefacto y decisiones de diseño, (iii) evidencia con personas representativas del proceso (en tu caso, profesionales de AAC), y (iv) contribuciones redactadas como cosas observables (interfaz, representación, método, resultados). En ASSETS’26 la CFP explicita que buscan contribuciones en diseño, sistemas y herramientas, y que recomiendan validación con usuarios representativos cuando sea posible, aunque también aceptan aportes principalmente técnicos. [Assets 2026](https://assets26.sigaccess.org/call_for_papers.html)
- Front matter (según plantilla ACM)
	- Título:
		- # Control Points for Generative AAC Pictogram Authoring: Designing Inspectable Generation for Professional Practice
	- abstract:
		-
		- AAC professionals routinely need pictograms that standard libraries do not contain — symbols for personal routines, local contexts, and situated vocabulary that no finite collection can anticipate. Generative AI can produce pictogram-like images from text, but current tools treat generation as a single opaque step: the professional receives a finished image with no way to inspect what the system interpreted, edit the pictogram's structure, or document why the result is adequate for a specific person.
		- This paper introduces the concept of _control points_ — interface locations where professionals can review, correct, and record decisions during generative pictogram authoring. We describe pictos.net, a design probe that stages the path from a natural-language phrase to a structured SVG pictogram through inspectable intermediate steps: intent interpretation, scene composition, and image generation. Each stage produces a representation the professional can examine and modify before proceeding.
		- The design is grounded in formative interviews with ten AAC professionals in Chile who support autistic young adults in independent-living transitions. We report preliminary findings from co-design workshops on which controls professionals used, which they skipped, and what they needed to document. We contribute design knowledge about how generative AAC tools can preserve professional authorship and accountability.
			- **Abstract viejo**: This paper reports a practice-oriented design research study on explainability as an interface property in generative authoring of augmentative and alternative communication (AAC) pictograms. The study focuses on AAC professionals who create and adapt pictograms for autistic adolescents and young adults (16–26) working towards independent-living routines in central Chile. We present Pictos.net, a proof-of-concept design probe that generates draft pictograms from short text prompts and exposes a set of interface “control points” where professionals can inspect the system’s interpretation, edit the graphic, and record decisions. Explainability is treated as work: views and records that professionals can contest and revise. The system treats a structured SVG file as the canonical artefact, carrying scene structure, stable element identifiers, and a change log that links edits to short rationales. We conducted semi-structured interviews and iterative workshops with speech-language therapists, special educators, psychologists, linguists, and designers. Participants completed authoring tasks using the probe and discussed criteria for pictogram quality, acceptable ambiguity, and accountability in reuse. We report which explanations supported judgement, which controls matched existing practice, and what records were needed to justify adaptations. The paper contributes an interface-level account of explainability for AAC pictogram generation and design implications for traceable professional authoring workflows.
	- CCS Concepts:
		- Human-centered computing → Accessibility
		- Human-centered computing → Interaction design
		- Human-centered computing → Participatory design
		- Computing methodologies → Artificial intelligence
		- Computing methodologies → Explainable AI
	- keywords:
		- augmentative and alternative communication (AAC)
		- pictograms
		- authoring tools
		- explainable AI (XAI)
		- co-design / participatory design
		- cognitive accessibility
- Introduction (1–1.5 páginas)
	- Plantea una situación concreta de trabajo: cuándo un equipo necesita un pictograma que no está en la biblioteca, por qué adaptar uno existente toma tiempo, y qué riesgos aparecen si se usa generación sin mecanismos de revisión. Define el foco: authoring profesional para jóvenes autistas en transición a vida independiente (16–26) en Chile central. Cierra con contribuciones enumeradas (3–5 ítems), formuladas como “presentamos / describimos / reportamos”.
- Background and Related Work (1.5–2 páginas)
	- Tres bloques, cada uno termina con “qué falta para este trabajo”.
		- a) AAC pictograms y prácticas de autoría/validación (quién decide, cómo se adapta, criterios).
			- [[Decision and adaptation criteria for AAC pictograms]]
		- b) Generative systems en herramientas de accesibilidad y en producción visual (sin prometer autonomía o resultados clínicos).
		- c) Explainable AI (XAI) en HCI/accesibilidad: define XAI en términos de “representaciones que permiten inspección y juicio”, no como taxonomía de técnicas.
- Research aim and scope (½ página)
	- Una frase con la pregunta. Ejemplo: “The paper asks: what interface control points and representations allow AAC professionals to review, edit, and document generative pictograms for independent-living routines?” Delimita qué evalúas y qué no (por ejemplo, no mides efectos comunicativos en usuarios finales en este paper, si no tendrás esos datos aún).
		- Quiero explorar las distintas configuraciones del "reasoning pipeline", es decir cómo se conceptualiza, desde el enfoque profesional, la lógica del pictograma como una "visual phrase"
		- Dentro de esto, cuáles son los "nodos más significativos" dentro de este pipeline (hasta el momento tengo definidos conceptualmente 3: comprender, componer y producir)
- Design rationale and requirements (1 página)
	- Lista corta de requisitos derivados de tu estudio formativo (entrevistas/talleres) y de la literatura: inspección del intento comunicativo, edición estructural, registro de cambios y razones, y mecanismos para comparar variantes. Aquí introduces el concepto de “control points” como unidades de interfaz observables.
- System overview: Pictos.net as a design probe (1–1.5 páginas)
	- Arquitectura a alto nivel (figura). Módulos principales (entrada textual, interpretación/expansión, generación, editor, registro). Define “design probe” en una frase y explica por qué Pictos.net sirve como “sitio de indagación” (en el sentido metodológico, no como producto final).
- Explainability as interface: the control points (núcleo del paper, 2–3 páginas)
	- Una subsección por control point. Cada una con: qué muestra, qué decisión soporta, qué acción permite, qué se registra. Por ejemplo:
		- a) Intent interpretation view (cómo el sistema entendió la frase).
		- b) Scene/role breakdown (actores/objetos/acción/contexto en forma legible).
		- c) Generation preview with alternatives (variantes, comparación).
		- d) Structured editing (edición del pictograma sin perder estructura).
		- e) Quality checks / evaluation prompts (si ICAP entra, que sea como instrumento de revisión, no como validación clínica).
		- f) Change log (quién cambió qué y por qué).
- SVG as “single source of truth” (1–1.5 páginas, subordinado al punto 7)
	- Aquí lo mantienes en foco si lo presentas como infraestructura de explicabilidad y trazabilidad. Define “single source of truth” como: el mismo artefacto contiene (i) la versión editable del pictograma, (ii) metadatos mínimos del caso, y (iii) el historial de cambios. Describe una extensión mínima, con ejemplos breves (sin volverte un paper de estándares):
		- – Identificadores estables por elemento/grupo.
		- – Roles semánticos simples (persona/objeto/acción/contexto, u otros que emerjan del trabajo profesional).
		- – Metadatos de procedencia (autor/fecha/idioma/contexto de uso).
		- – Registro de cambios y razones (en metadatos o bloque separado).
		- En ASSETS conviene que esta sección termine con una afirmación evaluable: “este esquema permitió X tipos de edición y Y tipos de revisión en las sesiones”.
- Implementation (½–1 página)
	- Stack, decisiones de despliegue, almacenamiento (por ejemplo local storage si aplica), límites prácticos, y cómo gestionas datos sensibles (aunque no almacenes datos de usuarios finales). Esta sección puede ir antes de la 8 si te queda más claro.
- Methods (1–1.5 páginas)
	- Describe el enfoque como investigación desde el diseño / research-through-design, con ciclos de: construir → probar con profesionales → revisar. Detalla participantes (roles), tareas, materiales, y qué datos recoges. ASSETS suele valorar la conexión entre método y contribución técnica. ([Assets 2026](https://assets26.sigaccess.org/call_for_papers.html))
- Study design / evaluation (1–2 páginas)
	- Especifica qué “evidencia” aportas. Para tu caso suele funcionar una evaluación en dos capas:
	  a) Formativa (entrevistas + talleres con escenarios de autoría).
	  b) Tareas comparativas acotadas (p. ej., crear/adaptar N pictogramas con y sin control points; o con dos variantes de interfaz).
	  Define medidas realistas: tiempo, número/tipo de ediciones, acuerdos/desacuerdos entre profesionales, y tipos de justificación registrados.
- Results / findings (1.5–2.5 páginas)
	- Organiza por hallazgos sobre control points, no por “temas generales”. Un esquema que suele leerse bien:
		- – Qué explicaciones piden y en qué momento.
		- – Qué controles usan para corregir y qué queda fuera de control.
		- – Qué necesitan registrar para poder responder por el resultado (accountability).
		  Incluye 2–3 viñetas de casos (micro-casos), con capturas/figuras.
- Discussion (1–1.5 páginas)
	- Interpreta implicaciones de diseño para herramientas generativas en AAC: dónde ubicar explicaciones, granularidad, riesgos de sobrecarga, y condiciones bajo las cuales el registro aporta al trabajo. Evita generalizaciones sobre inclusión o bienestar si no están respaldadas por datos en este paper.
- Limitations and future work (½–1 página)
	- Delimita: muestra, sitio, ausencia de evaluación directa con personas AAC usuarias (si aplica), y lo que necesitas para el siguiente paso (p. ej., pilot con usuarios finales mediado por profesionales).
- Conclusion (½ página)
	- Tres frases: problema, artefacto + control points, y contribución principal.
	- Apuntes prácticos de formato ASSETS (para planificar extensión, sin fijarlo como regla de 2026)
	  En ediciones recientes, los Technical Papers suelen caer en el rango de 7,500–10,000 palabras (short: 4,000–5,000), sin contar referencias, y se pide un PDF accesible para revisión. [ASSETS '24](https://assets24.sigaccess.org/authors/call-for-papers/technical-papers/?utm_source=chatgpt.com)