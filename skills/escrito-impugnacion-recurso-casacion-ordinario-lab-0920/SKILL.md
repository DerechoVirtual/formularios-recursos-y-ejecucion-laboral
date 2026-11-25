---
name: escrito-impugnacion-recurso-casacion-ordinario-lab-0920
description: "Escrito de impugnación del recurso de casación ordinario. Lo redacta con los datos del caso y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Escrito de impugnación del recurso de casación ordinario

> Formulario **LAB-0920** del plugin **Recursos, ejecución y resoluciones en el proceso laboral** (`formularios-recursos-y-ejecucion-laboral`) · Laboral › Proceso laboral (conciliación, demandas, recursos y ejecución) · normativa revisada el 25-11-2026.

## Qué es

Es un modelo de tipo **escritos de trámite y otros**, en su versión revisada y actualizada a la normativa vigente.

## Para qué sirve

Para obtener, en pocos minutos, un borrador completo de «Escrito de impugnación del recurso de casación ordinario» adaptado a tu caso y a la normativa vigente, en Word y listo para revisar. Claude no se limita a copiar el modelo: te pide los datos, decide contigo las opciones, redacta las partes que dependen de los hechos y comprueba en el BOE cada norma que cita.

## Cómo se usa

1. **Pídelo con tus palabras**, por ejemplo: «Prepárame el documento “Escrito de impugnación del recurso de casación ordinario” para mi caso». También puedes invocarla directamente con `/formularios-recursos-y-ejecucion-laboral:escrito-impugnacion-recurso-casacion-ordinario-lab-0920`.
2. **Dale los datos del caso** cuando te los pida (abajo tienes la lista para tenerlos a mano). Lo que no sepas queda como hueco visible.
3. **Resuelve las opciones** que te plantee (las marcadas [ELEGIR] y [OPCIONAL] en el modelo).
4. **Recibe el documento en Word, tal cual es el formulario**: empieza por su primera línea (por ejemplo «En [LOCALIDAD], a [FECHA]» o «A LA SECCIÓN…»), sin títulos ni notas añadidas, en Times New Roman 11, interlineado 1,15 y texto justificado. Lo pendiente, las normas comprobadas y el plazo te los dice en el chat.

Si no estás seguro de que este sea el formulario que necesitas, usa el índice del plugin: `/formularios-recursos-y-ejecucion-laboral:indice`.

## Qué contiene esta skill

- `SKILL.md` (este fichero): qué es el formulario, para qué sirve, cómo se usa, los datos que pide, las normas que cita, los avisos de actualización y las instrucciones para Claude.
- `assets/formulario.md`: el formulario seco, tal cual, desde su primera línea hasta la firma, con sus campos [EN MAYÚSCULAS] y sus opciones [ELEGIR…] / [OPCIONAL…]. Es el texto que se rellena; no lleva explicaciones.
- `../indice/marco.md` (en la skill `indice` del plugin): la guía del tema (Recursos, ejecución y resoluciones en el proceso laboral) con las normas, órganos y plazos vigentes que Claude lee antes de redactar.

## Datos que conviene tener a mano

- [ ] COMPLETAR (5 veces)
- [ ] LOCALIDAD (4 veces)
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Nº
- [ ] Nº DE PROCEDIMIENTO
- [ ] NÚMERO
- [ ] ÓRGANO O PERSONA

## Normas que cita el formulario

- No cita artículos concretos; Claude localizará las normas aplicables con Jurisprudenciator si el documento las necesita.

## Instrucciones para Claude

### Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

### Avisos de actualización (0) — se aplican en el texto, nunca se copian en el documento

- Ninguno.

### Notas de uso del formulario — orientan la redacción, nunca se copian en el documento

La fase de impugnación del recurso de casación es la última que tramita el Tribunal Superior de Justicia o, en su caso, la Audiencia Nacional, antes de remitir los autos a la Sala Cuarta (de lo Social) del Tribunal Supremo.

El artículo 211 LRJS detalla las actuaciones posteriores a la formalización del recurso de casación.

El Letrado de la Administración de Justicia proveerá en el plazo de dos días, dando traslado del mismo a las demás partes por término común de diez días para su impugnación.

En el escrito de impugnación se desarrollarán por separado los distintos motivos de impugnación, correlativos a los de casación formulados de contrario y las causas de inadmisión que estime concurrentes, así como, en su caso, otros motivos subsidiarios de fundamentación del fallo de la sentencia recurrida o eventuales rectificaciones de hechos que, con independencia de los fundamentos aplicados por esta, pudieran igualmente sustentar la estimación de las pretensiones de la parte impugnante, observando análogos requisitos que los exigidos para la formalización del recurso.

El escrito deberá estar suscrito por letrado, quien de no indicarse otra cosa asumirá desde ese momento la representación de la parte en el recurso, designando domicilio con todos los datos necesarios para notificaciones en la sede de la Sala de lo Social del Tribunal Supremo.

Durante el plazo de impugnación, los autos se encontrarán a disposición de la parte o del letrado que designe a tal fin, en la oficina judicial de la Sala (del Tribunal Superior de Justicia o de la Audiencia Nacional, según los casos) para su entrega o examen. En el caso de que la Sala disponga de los autos en soporte electrónico o pueda accederse a ellos por medios telemáticos, podrá sustituir el traslado material de las actuaciones por tales medios.

Del escrito o escritos de impugnación se dará traslado a las partes. De haberse formulado en dichos escritos alegaciones sobre inadmisibilidad del recurso o los motivos subsidiarios de fundamentación de la sentencia recurrida, en su caso, las demás partes, si lo estiman oportuno, podrán presentar directamente sus alegaciones al respecto, junto con las correspondientes copias para su traslado a las demás partes, dentro de los cinco días siguientes a recibir el escrito de impugnación.

El artículo 212 LRJS añade que transcurrido el plazo de impugnación y, en su caso, el de alegaciones (párrafo anterior), háyanse presentado o no escritos en tal sentido, y previo traslado de las alegaciones si se hubieran presentado, se elevarán los autos a la Sala de lo Social del Tribunal Supremo dentro de los cinco días siguientes.

Hay que tener en cuenta el Acuerdo de 8 de abril de 2025 sobre extensión máxima y condiciones extrínsecas de los escritos de formalización o interposición y de impugnación de los recursos de casación dirigidos a la Sala Cuarta del Tribunal Supremo. El Acuerdo fija las directrices sobre la extensión máxima y los requisitos formales que han de reunir los escritos de formalización o interposición y de impugnación de los recursos de casación ordinario y para la unificación de la doctrina.


### Flujo

1. **Paso 0**: comprueba Jurisprudenciator (arriba).
2. Lee entero `assets/formulario.md` (el formulario que vas a rellenar, en la carpeta de esta skill) y la parte de `../indice/marco.md` que afecte al caso. Limítate a la materia de este formulario: no añadas contenido ajeno a él.
3. Pide los datos de la lista en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez. Lo que el usuario no sepa se queda como hueco visible con su etiqueta (p. ej. [FECHA]).
4. Resuelve cada [ELEGIR …] y cada [OPCIONAL …] según los hechos, y sustituye cualquier indicación entre paréntesis del formulario («(se describirá…)», «(indicar…)») por el contenido que corresponda. Redacta las partes que dependen del caso (hechos, motivos, descripción de bienes).
5. Aplica los avisos de actualización en el lugar que indican. Comprueba con `buscar_articulo` cada norma citada; si alguna ha cambiado, usa la redacción vigente. Si citas jurisprudencia, localízala con `buscar_sentencias` o `buscar_por_cita` y léela con `leer_sentencias`.
6. Antes de entregarlo, pasa `verificar_escrito` con las frases que citan normas o sentencias y corrige lo que señale.
7. **Documento final = el formulario tal cual, rellenado y limpio.**
   - Empieza exactamente por la primera línea de `assets/formulario.md` y sigue su estructura y su orden hasta la firma.
   - No pongas en el documento título, nombre del formulario o de la skill, código, encabezados, «Para qué sirve», leyendas, avisos, notas de uso, comentarios ni explicaciones. Tampoco marcas [ELEGIR…] u [OPCIONAL…]: ya están resueltas.
   - Formato Word (.docx, con la skill de Word disponible): **Times New Roman 11 pt** en todo el documento, **interlineado 1,15**, **texto justificado**, márgenes de 2,5 cm. Los rótulos del formulario (REUNIDOS, CLÁUSULAS, HECHOS, SUPLICO…) en su propia línea y en negrita, sin cambiar su texto.
8. En el chat (nunca dentro del documento): datos pendientes, partes redactadas por ti, normas y sentencias comprobadas con Jurisprudenciator (y, si algún dato sale de internet, cuál y su enlace) y, si es un escrito judicial o administrativo, el plazo y el órgano ante el que se presenta.

El resultado es un borrador para que lo revise un profesional antes de usarlo.
