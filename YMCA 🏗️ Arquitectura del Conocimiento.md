
[Google Docs doc](https://docs.google.com/document/d/1xEGaguV5rf6Nka-_yZmeqo_wAb0widnw83MXRXKsyOo/edit?tab=t.0)
[NotebookLM General](https://notebooklm.google.com/notebook/66672d63-f1ec-4111-bbb3-b8db9ff97740)

**

# Arquitectura de Gestión del Conocimiento para YMCA Bogotá: Un Modelo Basado en Procesos para la Excelencia Operativa

## Sección 1: Fundamentos de la Arquitectura del Conocimiento para YMCA Bogotá

### 1.1. Introducción: De la Información al Conocimiento Estratégico

La presente propuesta detalla una arquitectura de gestión del conocimiento diseñada específicamente para YMCA Bogotá. Este proyecto trasciende la simple reorganización administrativa de archivos para posicionarse como un imperativo estratégico. En una organización impulsada por una misión clara y un compromiso con la calidad, como YMCA Bogotá, la gestión efectiva del conocimiento constituye el cimiento de la excelencia operativa, la mejora continua y la sostenibilidad a largo plazo.

Se define la "arquitectura de conocimiento" como un sistema deliberado y estructurado para capturar, organizar, compartir y aprovechar el capital intelectual de la organización. Su objetivo es transformar la información dispersa en un activo estratégico accesible y accionable, que impulse el cumplimiento de las metas institucionales y potencie el impacto en la comunidad.

### 1.2. Alineación con la Misión y la Política de Calidad

La arquitectura propuesta está intrínsecamente alineada con los principios fundamentales de la organización. La Política de Calidad de YMCA Bogotá establece un compromiso explícito con la prestación de "servicios y procesos de calidad certificada", la "mejora continua", la "innovación" y el fomento de una "cultura de calidad, aprendizaje y crecimiento". La estructura de conocimiento aquí delineada es la herramienta principal para operacionalizar estos compromisos.

La relación entre la política y la arquitectura es directa y funcional. Una política de calidad es una declaración de intenciones, mientras que un sistema de gestión del conocimiento es el mecanismo para su ejecución. Un sistema desestructurado, como un repositorio de archivos sin reglas, obstaculiza activamente el cumplimiento de dicha política al dificultar la localización, verificación y mejora de la información. Por el contrario, una arquitectura formal convierte las metas abstractas de la política en una realidad operativa tangible:

- Calidad Certificada: Un sistema estructurado hace que los procesos sean transparentes y fácilmente auditables, un requisito indispensable para la certificación.
    
- Mejora Continua: Al organizar la información de manera coherente, se facilita el análisis de datos y resultados, lo que permite identificar áreas de mejora de forma sistemática, cumpliendo con el Objetivo de Calidad N°4.
    
- Innovación: La arquitectura proporciona una base estable y predecible de conocimiento sobre la cual se pueden construir y probar nuevas iniciativas sin generar desorden.
    
- Cultura de Aprendizaje: Una base de conocimiento centralizada, accesible y predecible es la manifestación más tangible de una cultura que valora el aprendizaje y el crecimiento, ya que reduce la fricción en el acceso a la información y promueve la colaboración.
    

Por lo tanto, la implementación de esta arquitectura no es una acción que simplemente se alinea con la Política de Calidad; es un requisito previo para su implementación exitosa y sostenida.

### 1.3. Principios Rectores del Diseño Arquitectónico

El diseño de la siguiente estructura de carpetas se fundamenta en cuatro principios rectores que garantizan su eficacia, longevidad y adopción por parte de los usuarios.

- Principio 1: Centrado en el Proceso: La arquitectura refleja directamente el "Mapa de Procesos" oficial de la organización. Esta correspondencia asegura que la estructura sea intuitiva para todo el personal, ya que está organizada según la lógica operativa que ya conocen.
    
- Principio 2: Escalabilidad: La estructura está diseñada para crecer de manera ordenada. La adición de nuevos procesos, sub-procesos, servicios o unidades de negocio no requerirá una reestructuración completa del sistema, sino la simple adición de nuevas carpetas siguiendo la lógica establecida.
    
- Principio 3: Única Fuente de Verdad (Single Source of Truth - SSOT): El diseño busca eliminar la duplicación de documentos y la ambigüedad sobre la versión correcta de un archivo. Al tener un lugar único y definido para cada tipo de documento, los colaboradores pueden confiar en que están accediendo a la información más actual y aprobada.
    
- Principio 4: Previsibilidad: Mediante el uso de una estructura de sub-carpetas y una convención de nomenclatura estandarizadas, los usuarios pueden predecir dónde encontrar la información que necesitan y cómo almacenar nuevos documentos, independientemente del área de proceso en la que trabajen. Esto reduce la carga cognitiva y acelera la recuperación de información.
    

## Sección 2: Estructura Jerárquica Principal: Un Reflejo del Mapa de Procesos

### 2.1. Nivel 0: La Raíz del Sistema de Gestión de Conocimiento (SGC)

El punto de partida de toda la arquitectura es una única carpeta raíz que contendrá la totalidad de la base de conocimiento de la organización. Esta centralización es fundamental para la gobernanza del sistema.

- Propuesta: YMCA_BOGOTA_SGC
    

La creación de esta carpeta raíz única es crítica por tres razones principales: simplifica drásticamente la gestión de permisos y accesos a nivel global, facilita la implementación de estrategias de respaldo y recuperación de datos, y establece un límite claro y definido para el sistema oficial de gestión del conocimiento, diferenciándolo de otros repositorios informales.

### 2.2. Nivel 1: Macro-Procesos y Biblioteca Organizacional

Dentro de la carpeta raíz, la primera capa de carpetas refleja las categorías de más alto nivel del Mapa de Procesos de YMCA e introduce un componente esencial para los activos de toda la organización. El análisis del Mapa de Procesos muestra una clara división en tres tipos de procesos: Gerenciales, Operacionales y de Apoyo.

Sin embargo, no todo el conocimiento organizacional encaja en un proceso operativo. Documentos fundacionales como el Plan Estratégico , el Organigrama , o la Misión y Visión, son de naturaleza transversal. Mezclarlos con documentos de procesos específicos crearía desorden y dificultaría su localización. Por ejemplo, el organigrama es relevante para Gestión Humana, pero también para Planeación Estratégica y para cualquier colaborador que necesite entender la estructura jerárquica.

Para resolver esto, se propone la creación de una carpeta 0.0_BIBLIOTECA_ORGANIZACIONAL. Esta carpeta eleva dichos activos, los hace universalmente accesibles y mantiene las carpetas de procesos limpias y enfocadas en su propósito operativo. El prefijo numérico 0.0 asegura que esta carpeta siempre aparezca en primer lugar en una lista ordenada, señalando su importancia fundamental.

- Estructura Propuesta (Nivel 1):
    

- 0.0_BIBLIOTECA_ORGANIZACIONAL
    
- 1.0_PROCESOS_GERENCIALES
    
- 2.0_PROCESOS_OPERACIONALES
    
- 3.0_PROCESOS_DE_APOYO
    

### 2.3. Nivel 2 y 3: Detalle de Procesos y Sub-procesos

Esta sección detalla el mapeo completo de los procesos y sub-procesos de YMCA, según su documentación oficial, a la estructura de carpetas. El uso de los códigos de proceso existentes (ej. PG 01, PO-04 SP 001) en los nombres de las carpetas no es meramente estético; proporciona un identificador único, permanente y agnóstico al lenguaje para cada proceso, lo cual es crucial para la estabilidad a largo plazo y futuras automatizaciones.

- Estructura Propuesta (Nivel 2 y 3):
    

- 1.0_PROCESOS_GERENCIALES
    

- 1.1_PG-01_Planeacion_Estrategica
    
- 1.2_PG-02_Gestion_de_Calidad
    

- 2.0_PROCESOS_OPERACIONALES
    

- 2.1_PO-04_Educacion_Formal
    

- 2.1.1_PO-04-SP-001_Gestion_Academica
    
- 2.1.2_PO-04-SP-002_Gestion_de_la_Comunidad
    
- 2.1.3_PO-04-SP-003_Gestion_Administrativa_Educativa
    

- 2.2_PO-05_Servicios_de_Alimentacion
    

- 2.2.1_PO-05-SP-001_Planificacion_del_Servicio
    
- 2.2.2_PO-05-SP-002_Produccion_de_Alimentos
    
- 2.2.3_PO-05-SP-003_Prestacion_del_Servicio
    
- 2.2.4_PO-05-SP-004_Administracion_del_Servicio
    

- 3.0_PROCESOS_DE_APOYO
    

- 3.1_PA-01_Gestion_Humana
    
- 3.2_PA-02_Tesoreria
    
- 3.3_PA-03_Gestion_Contable
    
- 3.4_PA-04_Suministros_y_Servicios_Externos
    
- 3.5_PA-05_Marketing_y_Comunicaciones
    
- 3.6_PA-06_Mantenimiento_de_Infraestructura
    

La siguiente tabla sirve como una guía de implementación definitiva, eliminando cualquier ambigüedad y asegurando una correspondencia exacta con el Mapa de Procesos oficial.

Tabla 1: Mapeo Detallado de Procesos a la Arquitectura de Carpetas

|Código del Proceso|Nombre del Proceso|Ruta de Carpeta Designada|
|---|---|---|
|PG 01|Planeación Estratégica|.../1.1_PG-01_Planeacion_Estrategica/|
|PG 02|Gestión de Calidad|.../1.2_PG-02_Gestion_de_Calidad/|
|PO 04|Educación Formal|.../2.1_PO-04_Educacion_Formal/|
|PO-04 SP 001|Gestión Académica|.../2.1.1_PO-04-SP-001_Gestion_Academica/|
|PO-04 SP 002|Gestión de la Comunidad|.../2.1.2_PO-04-SP-002_Gestion_de_la_Comunidad/|
|PO-04 SP 003|Gestión Administrativa Educativa|.../2.1.3_PO-04-SP-003_Gestion_Administrativa_Educativa/|
|PO 05|Servicios de Alimentación|.../2.2_PO-05_Servicios_de_Alimentacion/|
|PO-05 SP 001|Planificación del Servicio|.../2.2.1_PO-05-SP-001_Planificacion_del_Servicio/|
|PO-05 SP 002|Producción de Alimentos|.../2.2.2_PO-05-SP-002_Produccion_de_Alimentos/|
|PO-05 SP 003|Prestación del Servicio|.../2.2.3_PO-05-SP-003_Prestacion_del_Servicio/|
|PO-05 SP 004|Administración del Servicio|.../2.2.4_PO-05-SP-004_Administracion_del_Servicio/|
|PA 01|Gestión Humana|.../3.1_PA-01_Gestion_Humana/|
|PA 02|Tesorería|.../3.2_PA-02_Tesoreria/|
|PA 03|Gestión Contable|.../3.3_PA-03_Gestion_Contable/|
|PA 04|Suministros y Servicios Externos|.../3.4_PA-04_Suministros_y_Servicios_Externos/|
|PA 05|Marketing y Comunicaciones|.../3.5_PA-05_Marketing_y_Comunicaciones/|
|PA 06|Mantenimiento de Infraestructura y Equipos|.../3.6_PA-06_Mantenimiento_de_Infraestructura/|

## Sección 3: Estandarización de Contenidos y Tipología Documental

### 3.1. La Necesidad de una Estructura Interna Coherente

Una vez establecida la jerarquía de procesos, es fundamental definir una estructura interna consistente para cada una de estas carpetas. Sin un conjunto estándar de sub-carpetas, cada departamento crearía su propia organización ad-hoc, lo que anularía los beneficios de previsibilidad y eficiencia del sistema global.

### 3.2. Diferenciación de Activos: Conocimiento de Referencia vs. Registros Transaccionales

Un análisis de la documentación del Sistema de Gestión de Calidad revela la existencia de dos tipos de activos de información fundamentalmente diferentes: documentos de referencia y registros transaccionales.

- Conocimiento de Referencia: Son los documentos que definen cómo se debe realizar el trabajo. Incluyen "procedimientos, caracterizaciones, manuales" y otros documentos guía. Son relativamente estáticos y sirven como la base de conocimiento del proceso.
    
- Registros Transaccionales: Son los documentos que proporcionan evidencia de qué trabajo se ha realizado. Incluyen los "formularios" una vez completados, como solicitudes, quejas, informes de inspección, actas de reunión, etc. Son dinámicos y se generan continuamente como resultado de la ejecución del proceso.
    

Mezclar estos dos tipos de documentos en la misma ubicación genera problemas de usabilidad significativos. Un colaborador que busca una plantilla en blanco para una solicitud de vacaciones no debería tener que navegar entre cientos de solicitudes ya completadas. De igual manera, un auditor que necesita revisar las solicitudes de un período específico no debería tener que filtrar plantillas y borradores.

Esta diferencia funcional exige una separación arquitectónica. Es necesario crear un repositorio dedicado para las plantillas reutilizables y otro, seguro y organizado, para los registros que sirven como evidencia. El uso de un guion bajo (_) como prefijo para estas sub-carpetas comunes asegura que siempre aparezcan en la parte superior de la lista de archivos dentro de cualquier carpeta de proceso, destacando su importancia y facilitando su acceso.

### 3.3. Estructura de Sub-carpetas Estándar Propuesta

Se propone que dentro de cada carpeta de proceso (definidas en la sección 2.3) se cree el siguiente conjunto estándar de sub-carpetas:

- _Caracterizacion_del_Proceso: Contendrá el documento oficial que define el objetivo, alcance, responsables, entradas, salidas y actividades del proceso.
    
- _Procedimientos_y_Guias: Para las instrucciones detalladas paso a paso sobre cómo ejecutar las tareas específicas dentro del proceso.
    
- _Manuales: Para documentos más extensos, como manuales de políticas o guías de referencia completas relacionadas con el proceso.
    
- _Formatos_y_Plantillas: Una biblioteca de plantillas y formularios en blanco, listos para ser utilizados (ej. F-PA-01-001_Solicitud_Vacaciones.docx). Este es el lugar para el conocimiento de referencia reutilizable.
    
- _Registros_y_Evidencias: El repositorio para todos los formularios completados, informes, actas de reunión, resultados de auditorías y cualquier otra evidencia de la ejecución del proceso. Esta carpeta puede requerir controles de acceso más restrictivos.
    
- _Indicadores_y_Resultados: Para almacenar los indicadores clave de rendimiento (KPIs), tableros de control y reportes de desempeño del proceso. Esta carpeta apoya directamente el Objetivo de Calidad N°4 de "aplicar procedimientos de medición, evaluación, análisis y mejora".
    
- _Material_de_Apoyo_y_Capacitacion: Para presentaciones de formación, videos, enlaces a recursos externos y otros materiales de aprendizaje relevantes para el proceso.
    

## Sección 4: Gestión de Activos Transversales y Biblioteca Organizacional

### 4.1. Definición y Propósito de la Biblioteca Organizacional

La carpeta 0.0_BIBLIOTECA_ORGANIZACIONAL funciona como el repositorio central para el conocimiento que define a la organización en su conjunto, en lugar de sus operaciones específicas. Es el hogar de los documentos de gobernanza, identidad y estrategia que son de interés y aplicabilidad para toda la institución.

### 4.2. Estructura Detallada de la Biblioteca

Basándose en la información disponible sobre la estructura y documentación de YMCA Bogotá , se propone la siguiente estructura interna para la biblioteca, proporcionando una ubicación lógica y centralizada para los activos de gobierno e identidad más críticos.

- 0.1_Gobernanza_y_Estrategia
    

- Mision_Vision_Valores.pdf
    
- Plan_Estrategico_Vigente.pdf
    
- Organigrama_Vigente.pdf
    
- Actas_Junta_Directiva/ (Carpeta para almacenar las actas de las reuniones del máximo órgano de gobierno)
    

- 0.2_Politicas_Corporativas
    

- (Ejemplos: POL-CORP-001_Politica_Tratamiento_de_Datos.pdf, POL-CORP-002_Codigo_de_Etica.pdf)
    

- 0.3_Documentacion_Legal_y_Cumplimiento
    

- (Ejemplos: RUT.pdf, Camara_de_Comercio.pdf, Estatutos.pdf)
    

- 0.4_Identidad_Corporativa
    

- Manual_de_Marca.pdf
    
- Logotipos/ (Con subcarpetas para diferentes formatos y versiones)
    
- Plantillas_Institucionales/ (Ej. plantillas de PowerPoint, Word con el membrete oficial)
    

- 0.5_Informes_Anuales_y_Transparencia
    

-   
    

## Sección 5: Protocolos de Gobernanza y Mantenimiento del Sistema

### 5.1. La Gobernanza como Pilar de la Sostenibilidad del Sistema

Una arquitectura bien diseñada es necesaria, pero no suficiente. Sin un conjunto claro de reglas y responsabilidades, cualquier sistema de archivos, por bien estructurado que esté, tenderá al desorden con el tiempo. La gobernanza es el conjunto de políticas, roles y procesos que aseguran la integridad, consistencia y valor de la base de conocimiento a lo largo del tiempo.

### 5.2. Convención de Nomenclatura para Archivos

Una convención de nomenclatura estandarizada es un elemento crítico de la gobernanza. Permite identificar el contenido y el contexto de un archivo sin necesidad de abrirlo, mejora drásticamente la eficacia de las búsquedas y filtros, y refuerza la previsibilidad del sistema.

- Convención Propuesta: [CodigoProceso]____[vX.X].ext
    

La siguiente tabla detalla cada componente de la convención y proporciona ejemplos prácticos para eliminar cualquier ambigüedad en su aplicación.

Tabla 2: Convención de Nomenclatura de Archivos y Ejemplos

|Componente|Descripción|Códigos/Ejemplos|
|---|---|---|
|[CodigoProceso]|Código oficial del proceso o sub-proceso al que pertenece el documento.|PG-02, PO-04-SP-001, PA-01|
|``|Abreviatura estandarizada que identifica el tipo de documento.|CAR: Caracterización<br>PROC: Procedimiento<br>MAN: Manual<br>FORM: Formato/Plantilla<br>REG: Registro/Evidencia<br>MIN: Minuta/Acta<br>INF: Informe<br>PRES: Presentación|
|``|Nombre breve y claro del documento, usando mayúsculas iniciales y sin espacios (CamelCase) o guiones bajos.|SeleccionDePersonal, InspeccionSanitariaCocina, ActaComiteCalidad|
|``|Fecha de creación, aprobación o relevancia del documento (formato ISO 8601). Opcional para plantillas.|2024-10-28|
|[vX.X]|Número de versión del documento.|v1.0, v2.3|
|Ejemplo 1 (Procedimiento):|Procedimiento de selección de personal del proceso de Gestión Humana.|PA-01_PROC_SeleccionDePersonal_2024-05-20_v1.0.pdf|
|Ejemplo 2 (Formato en blanco):|Formato para solicitud de permisos del proceso de Gestión Humana.|PA-01_FORM_SolicitudPermiso_v2.1.docx|
|Ejemplo 3 (Registro):|Registro de una inspección sanitaria en la cocina central del proceso de Servicios de Alimentación.|PO-05-SP-002_REG_InspeccionSanitariaCocinaCentral_2024-10-15_v1.0.pdf|

### 5.3. Control de Versiones y Estado del Documento

Se debe implementar un sistema de versionado simple y efectivo. Se sugiere usar versiones 0.x para borradores, 1.0 para la primera versión aprobada, 1.1, 1.2, etc., para revisiones menores (que no alteran el proceso), y 2.0 para revisiones mayores (que implican un cambio significativo en el proceso).

Para gestionar el estado del documento (borrador, vigente, obsoleto), se pueden utilizar sub-carpetas dedicadas dentro de la carpeta de tipo de documento correspondiente (ej. _Procedimientos_y_Guias/_Borradores/, _Procedimientos_y_Guias/_Vigente/, _Procedimientos_y_Guias/_Obsoleto/). Esto asegura que los usuarios solo accedan a las versiones vigentes en su trabajo diario, mientras se mantiene un archivo histórico para fines de auditoría y trazabilidad.

### 5.4. Roles y Responsabilidades en el Ciclo de Vida del Conocimiento

Para que el sistema funcione, es crucial definir roles claros:

- Propietario del Proceso (Process Owner): Es el máximo responsable del conocimiento dentro de su carpeta de proceso (ej. el Director de Gestión Humana es el propietario de 3.1_PA-01_Gestion_Humana). Aprueba los cambios significativos.
    
- Autor/Creador: El experto en la materia que redacta o actualiza un documento.
    
- Revisor/Aprobador: El gerente o experto designado que valida la exactitud y pertinencia del documento antes de su publicación.
    
- Coordinador de Calidad: Rol ya existente en la organización , supervisa la integridad de todo el sistema, asegura que se sigan los protocolos de gobernanza y gestiona el flujo del proceso de control de documentos.
    

### 5.5. Integración del Proceso de Control de Documentos

YMCA Bogotá ya cuenta con una herramienta clave para la gobernanza: el "Formulario para cambio de versión, creación o desactivación de documentos". La nueva arquitectura debe integrar y potenciar el uso de esta herramienta. El flujo de trabajo propuesto es el siguiente:

1. Un colaborador identifica la necesidad de crear o modificar un documento.
    
2. Completa el formulario oficial de control de documentos.
    
3. El formulario se envía al Propietario del Proceso y al Coordinador de Calidad para su evaluación y aprobación.
    
4. Una vez aprobado, el Autor crea o modifica el documento en una sub-carpeta de _Borradores, siguiendo la convención de nomenclatura.
    
5. El documento es revisado y aprobado formalmente por las partes designadas.
    
6. El Coordinador de Calidad mueve el documento final y aprobado a la carpeta _Vigente, actualiza el número de versión y mueve la versión anterior (si existe) a la carpeta _Obsoleto. Este acto finaliza el ciclo y publica el documento para su uso oficial.
    

## Sección 6: Implementación y Hoja de Ruta Sugerida

### 6.1. Un Enfoque Fásico para una Transición Exitosa

Se recomienda una implementación por fases para gestionar el cambio de manera efectiva, minimizar la interrupción de las operaciones diarias y asegurar la aceptación y adopción por parte de todos los colaboradores.

### 6.2. Fase 1: Configuración y Piloto (Semanas 1-2)

- Acciones: Crear la estructura completa de carpetas propuesta en la plataforma tecnológica seleccionada (ej. SharePoint, Google Drive). El piloto inicial involucrará únicamente al Equipo de Calidad (Johan Ferley Rios Romero y Eduardo Navarro ) y un proceso seleccionado, por ejemplo, 1.2_PG-02_Gestion_de_Calidad.
    
- Objetivo: Validar la funcionalidad de la arquitectura, probar los protocolos de gobernanza (nomenclatura, flujo de aprobación) y realizar ajustes antes del despliegue a gran escala.
    

### 6.3. Fase 2: Migración Guiada y Puesta a Punto (Semanas 3-6)

- Acciones: Cada Propietario de Proceso será responsable de liderar la migración de los documentos existentes de su área a la nueva estructura. Deberán aplicar retroactivamente la convención de nomenclatura y versionado a los documentos clave. El Coordinador de Calidad supervisará y brindará soporte durante todo este proceso.
    
- Objetivo: Poblar el nuevo sistema con toda la documentación vigente y relevante, asegurando que el conocimiento histórico se catalogue correctamente desde el inicio.
    

### 6.4. Fase 3: Capacitación y Despliegue Organizacional (Semanas 7-8)

- Acciones: Realizar sesiones de capacitación obligatorias para todo el personal. La formación no solo debe cubrir dónde encontrar los archivos, sino fundamentalmente cómo utilizar el sistema de acuerdo con los protocolos de gobernanza (nomenclatura, versionado, uso del formulario de control de cambios).
    
- Objetivo: Garantizar una comprensión universal y la adopción consistente de las nuevas prácticas de gestión del conocimiento.
    

### 6.5. Fase 4: Operación, Auditoría y Mejora Continua (Permanente)

- Acciones: El sistema está operativo. El Coordinador de Calidad realizará auditorías periódicas (ej. trimestrales) para verificar el cumplimiento de los protocolos, identificar documentos obsoletos o mal ubicados, y asegurar la salud general del sistema. La retroalimentación de los usuarios se recogerá de manera continua a través del formulario de Sugerencias, Quejas, Reclamos y Felicitaciones (SQRF) ya existente.
    
- Objetivo: Integrar el sistema de gestión del conocimiento en la cultura organizacional de mejora continua, cumpliendo directamente con el Objetivo de Calidad N°4. Esto asegura que el sistema siga siendo un activo vivo y valioso, en lugar de decaer en un archivo digital desatendido.
    

#### Fuentes citadas

1. Formularios - YMCA - Bogotá y Cundinamarca, https://www.ymcabogota.org/calidad/ 2. Planeación Estratégica - YMCA - Bogotá y Cundinamarca, https://www.ymcabogota.org/planeacion-estrategica/ 3. Organigrama - YMCA - Bogotá y Cundinamarca, https://www.ymcabogota.org/organigrama/

**