---
name: indice
description: "Índice de los 102 formularios de Recursos, ejecución y resoluciones en el proceso laboral. Úsala cuando el usuario pida un documento de esta materia y no esté claro qué formulario usar: propone el adecuado y lo abre. Requiere Jurisprudenciator."
---

# Recursos, ejecución y resoluciones en el proceso laboral: índice de formularios

> Plugin `formularios-recursos-y-ejecucion-laboral` · 102 formularios · normativa revisada el 25-11-2026.

## Qué es

Para la fase de recurso y ejecución en la jurisdicción social: recursos de reposición, suplicación, casación y queja y su impugnación, ejecución provisional y definitiva de sentencias, embargos, insolvencia y resoluciones del tribunal.

## Cómo se usa

Cuéntale a Claude qué documento necesitas y para qué caso. Esta skill busca en la lista de abajo el formulario que mejor encaja (por tipo de documento y por su nombre) y lo abre. Si hay dos o tres que encajan, te los propone para que elijas.

Ejemplos de petición:

- «Recurso de suplicación contra una sentencia de despido»
- «Solicitud de ejecución de una sentencia de despido»
- «Impugnación del recurso de suplicación»

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

### Cómo elegir

Busca por tipo de documento y por nombre. Cada formulario es una skill de este plugin (`/formularios-recursos-y-ejecucion-laboral:<skill>`). Si dudas entre dos, elige el que mejor encaje con los hechos y dilo; si la petición es ambigua, propón al usuario los dos o tres formularios que mejor encajan y pregúntale cuál quiere. Las reglas del tema están en `marco.md`.

### Cómo usar el formulario elegido

Invoca su skill. Si esa skill no aparece en tu lista de skills disponibles (puede pasar cuando hay muchas skills instaladas), lee directamente su fichero `SKILL.md`: está en la carpeta hermana de esta (`../<skill>/SKILL.md`). Síguelo igual que si la hubieras invocado: el formulario que se rellena está en `../<skill>/assets/formulario.md` y la guía del tema es el `marco.md` de esta carpeta.

### Contestaciones, oposiciones y alegaciones (10)

| Código | Formulario | Skill |
|---|---|---|
| LAB-0749 | Oposición de la empresa a la ejecución provisional del despido por imposibilidad de readmitir | `oposicion-empresa-ejecucion-provisional-despido-lab-0749` |
| LAB-0752 | Oposición de la empresa a la ejecución provisional del despido por haber optado por indemnizar | `oposicion-empresa-ejecucion-provisional-despido-haber-lab-0752` |
| LAB-0783 | Alegaciones del recurrente en el trámite de audiencia previo a la inadmisión de la suplicación | `alegaciones-recurrente-tramite-audiencia-previo-lab-0783` |
| LAB-0794 | Escrito de oposición a que se admita el recurso de suplicación | `escrito-oposicion-admita-recurso-suplicacion-lab-0794` |
| LAB-0829 | Oposición del deudor a la ejecución despachada en el proceso monitorio laboral | `oposicion-deudor-ejecucion-despachada-proceso-lab-0829` |
| LAB-0846 | Oposición del ejecutante a la suspensión y aplazamiento de la ejecución pedidos por el ejecutado | `oposicion-ejecutante-suspension-aplazamiento-ejecucion-lab-0846` |
| LAB-0924 | Alegaciones del recurrente ante la posible inadmisión del recurso de unificación de doctrina | `alegaciones-recurrente-ante-posible-inadmision-recurso-lab-0924` |
| LAB-0962 | Oposición al recurso de reposición contra resoluciones del LAJ por no haberse constituido depósito | `oposicion-recurso-reposicion-contra-resoluciones-laj-lab-0962` |
| LAB-0966 | Alegaciones en contra de la aportación de documentos nuevos en el recurso | `alegaciones-contra-aportacion-documentos-nuevos-recurso-lab-0966` |
| LAB-0967 | Alegaciones del recurrente ante el Supremo frente a la posible inadmisión del recurso de casación | `alegaciones-recurrente-ante-supremo-frente-posible-lab-0967` |

### Recursos (12)

| Código | Formulario | Skill |
|---|---|---|
| LAB-0714 | Revisión contra decretos del LAJ - recurso | `revision-contra-decretos-laj-recurso-lab-0714` |
| LAB-0767 | Recurso de reposición contra el auto de la Sala de lo Social del TSJ que inadmite la suplicación | `recurso-reposicion-contra-auto-sala-lo-social-tsj-lab-0767` |
| LAB-0770 | Recurso de reposición contra una resolución de la Sala de lo Social del TSJ | `recurso-reposicion-contra-resolucion-sala-lo-social-tsj-lab-0770` |
| LAB-0785 | Recurso de reposición contra la admisión de la prueba propuesta por la parte contraria | `recurso-reposicion-contra-admision-prueba-propuesta-lab-0785` |
| LAB-0815 | Recurso de reposición del ejecutado contra el despacho de ejecución, pidiendo trámite incidental | `recurso-reposicion-ejecutado-contra-despacho-ejecucion-lab-0815` |
| LAB-0816 | Recurso de reposición del ejecutado contra el despacho de ejecución dineraria por prescripción | `recurso-reposicion-ejecutado-contra-despacho-ejecucion-lab-0816` |
| LAB-0835 | Recurso de reposición previo a la queja contra el auto que declara desierta la casación unificadora | `recurso-reposicion-previo-queja-contra-auto-declara-lab-0835` |
| LAB-0836 | Recurso de reposición, previo a la queja, contra la denegación del recurso de casación | `recurso-reposicion-previo-queja-contra-denegacion-lab-0836` |
| LAB-0899 | Recurso de reposición en el proceso social contra providencias, autos, diligencias o decretos | `recurso-reposicion-proceso-social-contra-providencias-lab-0899` |
| LAB-0901 | Escrito de interposición del recurso de casación ordinario en el orden social | `escrito-interposicion-recurso-casacion-ordinario-orden-lab-0901` |
| LAB-0905 | Escrito de interposición del recurso de casación para la unificación de doctrina | `escrito-interposicion-recurso-casacion-unificacion-lab-0905` |
| LAB-0964 | Recurso de reposición contra una resolución del Letrado de la Administración de Justicia | `recurso-reposicion-contra-resolucion-letrado-lab-0964` |

### Contratos, pactos y cláusulas (2)

| Código | Formulario | Skill |
|---|---|---|
| LAB-0807 | Convenio transaccional entre las partes durante la ejecución de la sentencia | `convenio-transaccional-entre-partes-durante-ejecucion-lab-0807` |
| LAB-0808 | Convenio transaccional entre las partes mientras se tramita un recurso | `convenio-transaccional-entre-partes-mientras-tramita-lab-0808` |

### Estatutos, actas, certificaciones y escrituras (2)

| Código | Formulario | Skill |
|---|---|---|
| LAB-0948 | Anuncio de suplicación con depósito, consignación y petición de cálculo del capital coste de renta | `anuncio-suplicacion-deposito-consignacion-peticion-lab-0948` |
| LAB-0963 | Anuncio de suplicación de la entidad gestora con certificado de que ya abona la prestación | `anuncio-suplicacion-entidad-gestora-certificado-ya-lab-0963` |

### Escritos de trámite y otros (76)

| Código | Formulario | Skill |
|---|---|---|
| LAB-0003 | Escrito de recurso de suplicación contra el auto que deniega autorizar el despido colectivo | `escrito-recurso-suplicacion-contra-auto-deniega-lab-0003` |
| LAB-0708 | Reiniciar la ejecución laboral - escrito | `reiniciar-ejecucion-laboral-escrito-lab-0708` |
| LAB-0711 | Embargo preventivo de bienes tras la demanda - medida cautelar | `embargo-preventivo-bienes-tras-demanda-medida-cautelar-lab-0711` |
| LAB-0712 | Impugnar la liquidación de intereses en la ejecución laboral | `impugnar-liquidacion-intereses-ejecucion-laboral-lab-0712` |
| LAB-0716 | Ejecución del acuerdo de conciliación judicial (decreto del LAJ) | `ejecucion-acuerdo-conciliacion-judicial-decreto-laj-lab-0716` |
| LAB-0720 | Pedir embargo | `pedir-embargo-lab-0720` |
| LAB-0721 | Cambio de partes en la ejecución por sucesión empresarial - escrito | `cambio-partes-ejecucion-sucesion-empresarial-escrito-lab-0721` |
| LAB-0722 | Pedir declaración de insolvencia | `pedir-declaracion-insolvencia-lab-0722` |
| LAB-0723 | Pedir apremio pecuniario o multa coercitiva | `pedir-apremio-pecuniario-multa-coercitiva-lab-0723` |
| LAB-0724 | Pedir suspensión o aplazamiento de la ejecución | `pedir-suspension-aplazamiento-ejecucion-lab-0724` |
| LAB-0725 | Ejecución de sentencia o acta de conciliación firme - solicitud | `ejecucion-sentencia-acta-conciliacion-firme-solicitud-lab-0725` |
| LAB-0726 | Ejecución provisional de sentencia - solicitud | `ejecucion-provisional-sentencia-solicitud-lab-0726` |
| LAB-0727 | Anunciar recurso de suplicación | `anunciar-recurso-suplicacion-lab-0727` |
| LAB-0729 | Reposición contra la acumulación indebida de acciones - recurso | `reposicion-contra-acumulacion-indebida-acciones-recurso-lab-0729` |
| LAB-0730 | Reposición contra la acumulación de procesos - recurso | `reposicion-contra-acumulacion-procesos-recurso-lab-0730` |
| LAB-0731 | Multas coercitivas a terceros por incumplir en la ejecución de sentencia laboral - solicitud | `multas-coercitivas-terceros-incumplir-ejecucion-lab-0731` |
| LAB-0732 | Petición del representante sindical de ejecución provisional con garantías para su función | `peticion-representante-sindical-ejecucion-provisional-lab-0732` |
| LAB-0736 | Escrito que aporta documentos nuevos en el recurso ante la Sala de lo Social | `escrito-aporta-documentos-nuevos-recurso-ante-sala-lo-lab-0736` |
| LAB-0737 | Petición de ejecución provisional del despido improcedente con readmisión, sentencia recurrida | `peticion-ejecucion-provisional-despido-improcedente-lab-0737` |
| LAB-0743 | Petición de la empresa para recuperar lo anticipado al trabajador en ejecución provisional | `peticion-empresa-recuperar-lo-anticipado-trabajador-lab-0743` |
| LAB-0744 | Escrito para cobrar la diferencia entre la condena y lo anticipado en ejecución provisional | `escrito-cobrar-diferencia-entre-condena-lo-anticipado-lab-0744` |
| LAB-0745 | Petición de anticipo sobre lo consignado para recurrir en ejecución provisional | `peticion-anticipo-sobre-lo-consignado-recurrir-lab-0745` |
| LAB-0746 | Petición de anticipo al Estado en ejecución provisional al no haberse consignado para recurrir | `peticion-anticipo-estado-ejecucion-provisional-no-lab-0746` |
| LAB-0747 | Escrito de la empresa optando por que el trabajador no preste servicios durante el recurso | `escrito-empresa-optando-trabajador-no-preste-servicios-lab-0747` |
| LAB-0748 | Petición de ejecución provisional del despido nulo o improcedente recurrido por la empresa | `peticion-ejecucion-provisional-despido-nulo-lab-0748` |
| LAB-0751 | Petición de la empresa para que el trabajador vuelva a trabajar mientras se tramita el recurso | `peticion-empresa-trabajador-vuelva-trabajar-mientras-lab-0751` |
| LAB-0754 | Respuesta de la empresa a la ejecución provisional, optando por que el trabajador siga trabajando | `respuesta-empresa-ejecucion-provisional-optando-lab-0754` |
| LAB-0764 | Escrito subsanando la falta de poder en el recurso de casación para la unificación de doctrina | `escrito-subsanando-falta-poder-recurso-casacion-lab-0764` |
| LAB-0768 | Escrito que subsana los defectos del anuncio de suplicación o de la preparación de la casación | `escrito-subsana-defectos-anuncio-suplicacion-lab-0768` |
| LAB-0780 | Personación ante la Sala Cuarta del Tribunal Supremo en la casación para unificación de doctrina | `personacion-ante-sala-cuarta-tribunal-supremo-casacion-lab-0780` |
| LAB-0781 | Escrito del recurrente que desiste del recurso de suplicación | `escrito-recurrente-desiste-recurso-suplicacion-lab-0781` |
| LAB-0784 | Escrito que subsana los defectos del recurso de suplicación ya formalizado | `escrito-subsana-defectos-recurso-suplicacion-ya-lab-0784` |
| LAB-0789 | Escrito de la parte contraria que impugna el recurso directo de revisión | `escrito-parte-contraria-impugna-recurso-directo-lab-0789` |
| LAB-0799 | Escrito que pide dejar sin efecto la acumulación de recursos | `escrito-pide-dejar-sin-efecto-acumulacion-recursos-lab-0799` |
| LAB-0800 | Petición de certificación de sentencia para interponer la casación para unificación de doctrina | `peticion-certificacion-sentencia-interponer-casacion-lab-0800` |
| LAB-0803 | Escrito del ejecutante que designa bienes del deudor para su embargo | `escrito-ejecutante-designa-bienes-deudor-embargo-lab-0803` |
| LAB-0809 | Petición conjunta de homologación de la transacción alcanzada durante la suplicación o la casación | `peticion-conjunta-homologacion-transaccion-alcanzada-lab-0809` |
| LAB-0811 | Petición del acreedor para que se despache ejecución en el monitorio laboral | `peticion-acreedor-despache-ejecucion-monitorio-laboral-lab-0811` |
| LAB-0813 | Petición de ejecución provisional de la sentencia de tutela de derechos fundamentales | `peticion-ejecucion-provisional-sentencia-tutela-lab-0813` |
| LAB-0818 | Escrito del ejecutado que pide levantar el embargo de bienes inembargables | `escrito-ejecutado-pide-levantar-embargo-bienes-lab-0818` |
| LAB-0820 | Escrito del ejecutante que pide la mejora del embargo | `escrito-ejecutante-pide-mejora-embargo-lab-0820` |
| LAB-0825 | Otrosí de la demanda laboral que pide el embargo preventivo de bienes | `otrosi-demanda-laboral-pide-embargo-preventivo-bienes-lab-0825` |
| LAB-0833 | Petición de ejecución contra el Estado por el reintegro de lo anticipado en ejecución provisional | `peticion-ejecucion-contra-estado-reintegro-lo-lab-0833` |
| LAB-0844 | Escrito del ejecutante que comunica la cesión a un tercero del bien adjudicado en subasta | `escrito-ejecutante-comunica-cesion-tercero-bien-lab-0844` |
| LAB-0845 | Escrito del ejecutado que se opone a la liquidación de intereses de la ejecución | `escrito-ejecutado-opone-liquidacion-intereses-ejecucion-lab-0845` |
| LAB-0847 | Escrito del ejecutado que se opone al embargo de un bien por existir otros de embargo preferente | `escrito-ejecutado-opone-embargo-bien-existir-otros-lab-0847` |
| LAB-0848 | Incidente de nulidad contra sentencia firme no recurrible, previo al recurso de amparo | `incidente-nulidad-contra-sentencia-firme-no-recurrible-lab-0848` |
| LAB-0853 | Escrito que aporta las sentencias de contraste del recurso de casación para unificación de doctrina | `escrito-aporta-sentencias-contraste-recurso-casacion-lab-0853` |
| LAB-0855 | Escrito del abogado de oficio que considera inviable el recurso de unificación de doctrina | `escrito-abogado-oficio-considera-inviable-recurso-lab-0855` |
| LAB-0859 | Petición de certificación de la sentencia de contraste para el recurso de unificación de doctrina | `peticion-certificacion-sentencia-contraste-recurso-lab-0859` |
| LAB-0878 | Personación de la parte recurrida en el recurso de casación para la unificación de doctrina | `personacion-parte-recurrida-recurso-casacion-lab-0878` |
| LAB-0879 | Preparación del recurso de casación ordinario ante la Sala de lo Social del Tribunal Supremo | `preparacion-recurso-casacion-ordinario-ante-sala-lo-lab-0879` |
| LAB-0881 | Impugnación por la parte recurrida del recurso de casación para la unificación de doctrina | `impugnacion-parte-recurrida-recurso-casacion-lab-0881` |
| LAB-0882 | Escrito que prepara el recurso de casación para la unificación de doctrina | `escrito-prepara-recurso-casacion-unificacion-doctrina-lab-0882` |
| LAB-0894 | Petición de acumular varias ejecuciones contra el mismo ejecutado | `peticion-acumular-varias-ejecuciones-contra-mismo-lab-0894` |
| LAB-0907 | Petición de ejecución del acuerdo alcanzado en conciliación o mediación ante el SMAC | `peticion-ejecucion-acuerdo-alcanzado-conciliacion-lab-0907` |
| LAB-0914 | Petición de ejecución de la sentencia de despido nulo por falta de readmisión o readmisión irregular | `peticion-ejecucion-sentencia-despido-nulo-falta-lab-0914` |
| LAB-0919 | Petición de embargo preventivo en el proceso laboral | `peticion-embargo-preventivo-proceso-laboral-lab-0919` |
| LAB-0920 | Escrito de impugnación del recurso de casación ordinario | `escrito-impugnacion-recurso-casacion-ordinario-lab-0920` |
| LAB-0921 | Escrito de la empresa que elige pagar salarios sin trabajo en la ejecución provisional del despido | `escrito-empresa-elige-pagar-salarios-sin-trabajo-lab-0921` |
| LAB-0922 | Escrito de la empresa que cambia su opción tras elevarse la indemnización en el recurso | `escrito-empresa-cambia-opcion-tras-elevarse-lab-0922` |
| LAB-0923 | Escrito del trabajador que cambia su opción tras reducirse la indemnización en el recurso | `escrito-trabajador-cambia-opcion-tras-reducirse-lab-0923` |
| LAB-0925 | Petición de que se paguen los gastos antes que el principal en la ejecución laboral | `peticion-paguen-gastos-antes-principal-ejecucion-lab-0925` |
| LAB-0926 | Escrito de tercería de mejor derecho en la ejecución laboral | `escrito-terceria-mejor-derecho-ejecucion-laboral-lab-0926` |
| LAB-0928 | Petición del trabajador de un anticipo reintegrable en la ejecución provisional | `peticion-trabajador-anticipo-reintegrable-ejecucion-lab-0928` |
| LAB-0932 | Petición de reembargo de bienes ya trabados en otra ejecución | `peticion-reembargo-bienes-ya-trabados-otra-ejecucion-lab-0932` |
| LAB-0933 | Petición de administración forzosa de los bienes subastados | `peticion-administracion-forzosa-bienes-subastados-lab-0933` |
| LAB-0935 | Petición de embargo del salario del ejecutado | `peticion-embargo-salario-ejecutado-lab-0935` |
| LAB-0940 | Petición de ejecución por readmisión irregular tras sentencia de despido nulo | `peticion-ejecucion-readmision-irregular-tras-sentencia-lab-0940` |
| LAB-0941 | Petición de ejecución porque la empresa no readmite al trabajador pese al requerimiento judicial | `peticion-ejecucion-porque-empresa-no-readmite-lab-0941` |
| LAB-0945 | Tasación de costas y liquidación de intereses en la ejecución laboral | `tasacion-costas-liquidacion-intereses-ejecucion-laboral-lab-0945` |
| LAB-0949 | Petición de ejecución parcial de la sentencia recurrida | `peticion-ejecucion-parcial-sentencia-recurrida-lab-0949` |
| LAB-0950 | Petición de suspensión de la ejecución por haberse recurrido | `peticion-suspension-ejecucion-haberse-recurrido-lab-0950` |
| LAB-0961 | Escrito que subsana la consignación insuficiente al anunciar el recurso | `escrito-subsana-consignacion-insuficiente-anunciar-lab-0961` |
| LAB-0965 | Escrito que aporta en el recurso una resolución administrativa firme como documento nuevo | `escrito-aporta-recurso-resolucion-administrativa-firme-lab-0965` |
| LAB-0974 | Petición de embargo preventivo frente a la empresa que ha dejado de pagar los salarios | `peticion-embargo-preventivo-frente-empresa-ha-dejado-lab-0974` |
