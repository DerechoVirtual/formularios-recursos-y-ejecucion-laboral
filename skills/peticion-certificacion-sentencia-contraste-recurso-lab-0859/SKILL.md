---
name: peticion-certificacion-sentencia-contraste-recurso-lab-0859
description: "Petición de certificación de la sentencia de contraste para el recurso de unificación de doctrina. Lo redacta con los datos del caso y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Petición de certificación de la sentencia de contraste para el recurso de unificación de doctrina

> Formulario **LAB-0859** del plugin **Recursos, ejecución y resoluciones en el proceso laboral** (`formularios-recursos-y-ejecucion-laboral`) · Laboral › Proceso laboral (conciliación, demandas, recursos y ejecución) · normativa revisada el 25-11-2026.

## Qué es

Es un modelo de tipo **escritos de trámite y otros**, en su versión revisada y actualizada a la normativa vigente.

## Para qué sirve

Para obtener, en pocos minutos, un borrador completo de «Petición de certificación de la sentencia de contraste para el recurso de unificación de doctrina» adaptado a tu caso y a la normativa vigente, en Word y listo para revisar. Claude no se limita a copiar el modelo: te pide los datos, decide contigo las opciones, redacta las partes que dependen de los hechos y comprueba en el BOE cada norma que cita.

## Cómo se usa

1. **Pídelo con tus palabras**, por ejemplo: «Prepárame el documento “Petición de certificación de la sentencia de contraste para el recurso de unificación de doctrina” para mi caso». También puedes invocarla directamente con `/formularios-recursos-y-ejecucion-laboral:peticion-certificacion-sentencia-contraste-recurso-lab-0859`.
2. **Dale los datos del caso** cuando te los pida (abajo tienes la lista para tenerlos a mano). Lo que no sepas queda como hueco visible.
3. **Resuelve las opciones** que te plantee (las marcadas [ELEGIR] y [OPCIONAL] en el modelo).
4. **Recibe el documento en Word, tal cual es el formulario**: empieza por su primera línea (por ejemplo «En [LOCALIDAD], a [FECHA]» o «A LA SECCIÓN…»), sin títulos ni notas añadidas, en Times New Roman 11, interlineado 1,15 y texto justificado. Lo pendiente, las normas comprobadas y el plazo te los dice en el chat.

Si no estás seguro de que este sea el formulario que necesitas, usa el índice del plugin: `/formularios-recursos-y-ejecucion-laboral:indice`.

## Qué contiene esta skill

- `SKILL.md` (este fichero): qué es el formulario, para qué sirve, cómo se usa, los datos que pide, las normas que cita, los avisos de actualización y las instrucciones para Claude.
- `assets/formulario.md`: el formulario seco, tal cual, desde su primera línea hasta la firma, con sus campos [EN MAYÚSCULAS] y sus opciones [ELEGIR…] / [OPCIONAL…]. Es el texto que se rellena; no lleva explicaciones.
- `../indice/marco.md` (en la skill `indice` del plugin): la guía del tema (Recursos, ejecución y resoluciones en el proceso laboral) con las normas, órganos y plazos vigentes que Claude lee antes de redactar.

## Datos que conviene tener a mano

- [ ] FECHA (4 veces)
- [ ] LOCALIDAD (4 veces)
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE PROCEDIMIENTO (3 veces)
- [ ] SECCIÓN (2 veces)
- [ ] COLEGIO
- [ ] COMPLETAR
- [ ] LUGAR
- [ ] NOMBRE DEL REPRESENTADO/A
- [ ] Nº DE COLEGIADO/A

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

Son recurribles en casación para la unificación de doctrina las sentencias dictadas en suplicación por las Salas de lo Social de los Tribunales Superiores de Justicia, que fueran contradictorias entre sí, con la de otra u otras Salas de los referidos Tribunales Superiores o con sentencias del Tribunal Supremo, respecto de los mismos litigantes u otros diferentes en idéntica situación donde, en mérito a hechos, fundamentos y pretensiones sustancialmente iguales, se hubiere llegado a pronunciamientos distintos, siempre que la Sala Social del Tribunal Supremo aprecie que el recurso presenta interés casacional objetivo. Existe interés casacional objetivo cuando se de alguno de los siguientes supuestos:

a) Si concurren circunstancias que aconsejen un nuevo pronunciamiento de la Sala.

b) Si la cuestión posee una trascendencia o proyección significativa.

c) Si el debate suscitado presenta relevancia para la formación de la jurisprudencia.

Podrá alegarse como doctrina de contradicción la establecida en las sentencias dictadas por el Tribunal Constitucional y los órganos jurisdiccionales instituidos en los Tratados y Acuerdos internacionales en materia de derechos humanos y libertades fundamentales ratificados por España, siempre que se cumplan los presupuestos del número anterior referidos a la pretensión de tutela de tales derechos y libertades.

En virtud del art. 221.2 LRJS, el escrito de preparación del recurso de casación para la unificación de doctrina deberá estar firmado por abogado, acreditando la representación de la parte de no constar previamente en las actuaciones, y expresará el propósito de la parte de formalizar el recurso, con exposición sucinta de la concurrencia de los requisitos exigidos. El escrito deberá:

a) Exponer cada uno de los extremos del núcleo de la contradicción, determinando el sentido y alcance de la divergencia existente entre las resoluciones comparadas, en atención a la identidad de la situación, a la igualdad sustancial de hechos, fundamentos y pretensiones y a la diferencia de pronunciamientos.

b) Hacer referencia detallada y precisa a los datos identificativos de la sentencia o sentencias que la parte pretenda utilizar para fundamentar cada uno de los puntos de contradicción.

c) Exponer, de manera sucinta, las razones por las que la cuestión suscitada posee interés casacional objetivo.

Las sentencias invocadas como doctrina de contradicción deberán haber ganado firmeza a la fecha de finalización del plazo de interposición del recurso.

Las sentencias que no hayan sido objeto de expresa mención en el escrito de preparación no podrán ser posteriormente invocadas en el escrito de interposición.

Con el escrito de interposición, de no haberse aportado con anterioridad, podrá hacerse aportación certificada de la sentencia o sentencias contrarias, acreditando su firmeza en la fecha de expiración del plazo de interposición, o con certificación posterior de que ganó firmeza dentro de dicho plazo la sentencia anteriormente aportada. Si la parte recurrente no aporta la certificación de la sentencia y de su firmeza en tiempo oportuno se reclamará de oficio por la secretaría de la Sala.

Actualizado según modificaciones introducidas por la Ley Orgánica 1/2025, de 2 de enero, de medidas en materia de eficiencia del Servicio Público de Justicia.


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
