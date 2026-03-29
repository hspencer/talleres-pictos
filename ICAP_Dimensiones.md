status:: draft
public:: false
lang:: es
tags:: #ICAP #rubrica #proyecto
 type:: proyecto

- # ICAP – Dimensiones y automatización (borrador)
  > Nota: completar con definiciones oficiales desde rúbrica ICAP del repo. Aquí se listan 7 dimensiones tentativas y posibles automatizaciones.
- ## 1) Claridad (complejidad visual)
- Propósito: legibilidad a tamaños pequeños, sin exceso de detalle ni ambigüedad.
- Automatización: `scripts/icap_complexity.sh` (densidad de bordes); futuros checks de contraste/fondo.
- ## 2) Consistencia visual / Estilo
- Propósito: coherencia de trazo, paleta, proporciones entre símbolos de un set.
- Automatización: extracción de paleta dominante, grosor de línea, proporciones de bounding boxes; comparación con un símbolo “ancla”.
- ## 3) Adecuación semántica
- Propósito: correspondencia símbolo–significado en vocabulario y ontología.
- Automatización: usar NLU + ontología (nlu-schema) para mapear a conceptos; chequear presencia de convenciones (negación, plural, etc.) y roles (ICAP/NLU).
- ## 4) Adecuación contextual / Cultural
- Propósito: ajuste a contexto de uso (edad, cultura, situación, dominio).
- Automatización: checklist de metadatos (contexto, público, dominio) + detección de elementos contextuales (ropa, entorno) vía tagger/vision y comparación con reglas.
- ## 5) Accesibilidad / Legibilidad funcional
- Propósito: comprensibilidad en condiciones de tamaño, color, contraste, daltonismo.
- Automatización: simulación de daltónica (prot/deut/trit) y verificación de contraste; test de legibilidad a tamaños 32/64 px; opcional: iconografía monocroma.
- ## 6) Documentación / Trazabilidad
- Propósito: registrar decisiones, variantes, razones de aceptación/rechazo.
- Automatización: validar presencia de metadatos (status, rationale, style params, versión); generar diff visual y changelog.
- ## 7) Iconicidad
- Propósito: maximizar correspondencia visual-referente para usuarios con lenguaje receptivo limitado.
- Referencia: Hartley & Allen (2015) [[iconicidad]].
- Automatización (idea): medir “iconicity score” relativo (p.ej., CLIP similarity con fotos de referencia o percentil de transparencia) y priorizar versiones más icónicas para ciertos perfiles.
- ## Pendientes
- Traer definiciones y rúbricas exactas del repo ICAP.
- Asociar cada dimensión con tests concretos (scripts) y ejemplos de datos de entrada/salida.
- Integrar con pipelines Pictos/MediaFranca (nlu-schema, mf-svg-schema, ICAP).