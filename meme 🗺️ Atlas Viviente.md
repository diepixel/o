[NotebookLM](https://notebooklm.google.com/notebook/f48ac145-9ebb-46da-a32c-09f3dcf7affe)

# Un Atlas Viviente de la Cultura Humana: Un Marco Estratégico para el Desarrollo

  
  

## Resumen Ejecutivo

  

Este informe presenta un marco estratégico para el desarrollo de un proyecto de código abierto por etapas, cuyo objetivo es la creación de un "Atlas Viviente de la Cultura Humana". El proyecto se centra en una aplicación web diseñada para fomentar una conciencia colectiva más profunda sobre la diversidad de las culturas humanas. La plataforma permitirá a los usuarios de todo el mundo definir las características de sus propias culturas y ubicarlas en un mapa virtual global. La propuesta de valor única del proyecto reside en su innovadora ontología cultural, que sintetiza la accesibilidad y modularidad de los sistemas de simulación cultural de videojuegos complejos —como Rimworld: Ideology, Dwarf Fortress y Crusader Kings III— con el rigor analítico de marcos sociológicos y antropológicos establecidos, notablemente la Teoría de las Dimensiones Culturales de Hofstede y la Teoría de los Valores Humanos Básicos de Schwartz.

El análisis propone un modelo ontológico multicapa para la definición de una cultura, estructurado en: 1) Valores Fundamentales, 2) Preceptos y Tradiciones, 3) Estructuras y Roles Sociales, y 4) Expresión Material. Este modelo servirá como la base lógica tanto para la interfaz de usuario como para la arquitectura de la base de datos. Para la implementación técnica, se recomienda un conjunto de tecnologías de código abierto que garantice la escalabilidad, la accesibilidad para los contribuidores y la alineación con el ethos colaborativo del proyecto. La arquitectura sugerida incluye una biblioteca de mapeo front-end como Leaflet o MapLibre GL, una base de datos geoespacial robusta como PostgreSQL con la extensión PostGIS, y una API para la comunicación de datos.

Finalmente, el informe subraya la importancia crítica de una estructura de gobernanza dual y robusta, gestionada a través de GitHub. Esta gobernanza debe atender las necesidades de dos comunidades distintas pero interconectadas: la comunidad de desarrolladores que construye la plataforma y la comunidad de contribuidores que genera los datos culturales. Se detallan las mejores prácticas para la gestión del proyecto de software, así como un marco integral para la moderación de contenido y la curación de datos, esencial para mantener un entorno saludable, respetuoso y productivo. El desarrollo se concibe en un plan por fases: 1) Finalización de la Ontología, 2) Desarrollo del Prototipo, y 3) Lanzamiento Público y Crecimiento Comunitario, proporcionando una hoja de ruta clara para transformar esta visión ambiciosa en una herramienta tangible y de gran valor para la humanidad.

---

## Parte I: Deconstruyendo Culturas Simuladas - De la Mecánica de Juego a los Primitivos Ontológicos

  
  

### Introducción

  

La decisión de utilizar videojuegos de simulación complejos como punto de partida para un proyecto de mapeo cultural no es arbitraria. Títulos como Rimworld, Dwarf Fortress y Crusader Kings III han trascendido el mero entretenimiento para convertirse en laboratorios funcionales que simulan sistemas sociales y culturales.1 Estos juegos presentan ontologías simplificadas pero coherentes de la cultura, la sociedad y la interacción humana. Su valor fundamental para este proyecto radica en que ofrecen marcos accesibles, modulares y probados por millones de usuarios para conceptos abstractos y complejos.4 Al deconstruir sus mecánicas, es posible extraer un conjunto de "primitivos ontológicos" —componentes básicos y relaciones lógicas— que pueden servir como el andamiaje intuitivo para una plataforma orientada al público, sentando las bases para un sistema que es a la vez atractivo y analíticamente potente.

  

### 1.1 El Motor de Rimworld Ideology: Un Enfoque Modular para los Sistemas de Creencias

  

La expansión Ideology para el juego de simulación de colonias Rimworld introduce un sistema altamente personalizable para definir las creencias de los colonos. Este sistema se basa en una estructura jerárquica que ofrece una notable flexibilidad y profundidad, sirviendo como un excelente modelo inicial para la definición cultural en el atlas propuesto.5

- Análisis de Mecánicas Fundamentales: La estructura de Ideology se compone de tres elementos principales que interactúan para dar forma a una cultura.
    

- Memes: Son las ideas centrales, el núcleo de un sistema de creencias. Cada "ideoligión" se construye en torno a una combinación de 1 a 4 memes, como 'Colectivista', 'Transhumanista' o 'Caníbal'.5 Estos memes establecen la identidad de alto nivel de la cultura y dictan las tendencias generales de sus seguidores. La vasta cantidad de memes disponibles, tanto en el juego base como a través de modificaciones de la comunidad, demuestra el inmenso poder combinatorio de este enfoque, permitiendo la creación de un espectro casi infinito de sistemas de creencias.7
    
- Preceptos: Son las reglas y directrices específicas que se derivan de los memes. Cada precepto gobierna una actitud o comportamiento particular, como 'Consumo de carne: Aborrecible' o 'Modificación corporal: Aprobada'.11 Este nivel añade una granularidad crucial, permitiendo una personalización detallada y la existencia de matices dentro de un meme más amplio. Por ejemplo, dos culturas transhumanistas pueden diferir en sus preceptos sobre la inteligencia artificial o la modificación genética, lo que genera interacciones de juego únicas y desafíos específicos.11
    
- Roles Sociales: El sistema define roles formales como el Líder, el Guía Moral y los Especialistas. Estos roles codifican la estructura social y la jerarquía dentro de una cultura, otorgando a los individuos habilidades especiales, responsabilidades y expectativas de comportamiento.6 Un Líder puede dar discursos inspiradores, mientras que un Guía Moral puede consolar a los colonos o convertir a prisioneros.
    

- Aplicabilidad al Proyecto: El sistema de Rimworld ofrece un modelo de "bloques de construcción" potente e intuitivo. Los usuarios del atlas podrían seleccionar "Memes" de alto nivel para su cultura y luego ajustar los "Preceptos" para reflejar sus prácticas específicas, replicando la interfaz de personalización del juego.12 Además, la mecánica de "Ideoligión Fluida", que permite a una cultura evolucionar y adoptar nuevos memes y preceptos con el tiempo, proporciona un paralelismo directo sobre cómo una cultura podría cambiar dinámicamente dentro de la aplicación web.6
    

  

### 1.2 El Motor Ético de Dwarf Fortress: Comportamiento Emergente Impulsado por Valores

  

A diferencia del sistema más explícito de Rimworld, Dwarf Fortress simula la cultura a un nivel más fundamental a través de su sistema de "Ética". Este enfoque no prescribe comportamientos directos, sino que define un conjunto de valores centrales que, al interactuar, generan comportamientos complejos y emergentes a nivel de civilización.3

- Análisis de Mecánicas Fundamentales: El sistema utiliza etiquetas en los archivos de configuración de las entidades para definir la postura de una civilización sobre cuestiones fundamentales.15
    

- Etiquetas y Valores Éticos: El sistema define éticas específicas como SLAVERY (Esclavitud), EAT_SAPIENT_KILL (Comer seres sapientes asesinados), KILL_PLANT (Matar plantas) y TREASON (Traición).15 Cada una de estas éticas se asocia con un valor en un espectro que va desde ACCEPTABLE (Aceptable) hasta UNTHINKABLE (Impensable), cuantificando así el marco moral de la cultura.
    
- Dinámicas Inter-Civilizatorias: El motor del juego calcula la animosidad o la amistad entre civilizaciones basándose en la alineación o el conflicto de estos valores éticos. Un conflicto ético fuerte, como una civilización que considera la tala de árboles UNTHINKABLE (los elfos) interactuando con una que la considera ACCEPTABLE (los enanos), puede conducir directamente a resultados emergentes como embargos comerciales o guerras a gran escala durante la generación del mundo.15 Esto demuestra cómo un conjunto simple de valores fundamentales puede generar resultados sistémicos complejos y no guionizados.
    

- Aplicabilidad al Proyecto: El modelo de Dwarf Fortress es invaluable para simular la interacción entre las diferentes culturas definidas por los usuarios en el mapa. Mientras que el sistema de Rimworld es ideal para la autodefinición, el sistema de Dwarf Fortress ofrece un mecanismo para visualizar las relaciones. Los valores éticos pueden formar la base de una "puntuación de compatibilidad" entre culturas adyacentes, lo que permitiría al atlas representar visualmente áreas de potencial armonía, tensión o conflicto cultural en el mapa global, convirtiéndolo en una herramienta de análisis dinámico en lugar de un simple repositorio de datos estáticos.
    

  

### 1.3 El Motor Dinástico de Crusader Kings III: Evolución Cultural y Sincretismo

  

Crusader Kings III (CKIII) presenta el modelo más sofisticado de los tres para la dinámica y el cambio cultural. En CKIII, la cultura no es una entidad estática, sino un sistema vivo que evoluciona, se diverge y se hibrida a lo largo del tiempo, reflejando procesos históricos del mundo real.18

- Análisis de Mecánicas Fundamentales: La cultura en CKIII se compone de varios elementos interconectados.
    

- Pilares Culturales: Estos son los elementos fundacionales y de cambio lento de la identidad de una cultura, incluyendo la Herencia (linaje cultural, p. ej., Germánico del Norte), el Idioma y las Costumbres Marciales.18
    
- Ethos: Cada cultura tiene uno de los siete tipos de "Ethos" (p. ej., Belicoso, Espiritual, Estoico) que proporciona bonificaciones generales y define la actitud central de la cultura.18
    
- Tradiciones: Son las costumbres específicas que otorgan efectos mecánicos y añaden sabor a una cultura. Existe una vasta lista de tradiciones, como 'Gente del Bosque', 'Artistas Culinarios' o 'Cultura Filosófica', que permiten una personalización profunda y reflejan prácticas culturales únicas.20
    
- Hibridación y Divergencia: La mecánica más relevante para este proyecto es la que permite a dos culturas fusionarse. Una cultura híbrida puede seleccionar pilares y tradiciones de ambas culturas parentales, creando una nueva identidad sincrética.18 La divergencia permite que una subcultura se separe de su cultura madre, adoptando nuevas tradiciones. Estos mecanismos son modelos directos para representar el sincretismo cultural y la creación de nuevas identidades híbridas en el atlas.25
    

- Aplicabilidad al Proyecto: CKIII ofrece un marco robusto para el cambio cultural. El proyecto del atlas puede implementar mecánicas similares. Los usuarios podrían proponer "hibridaciones" con culturas vecinas en el mapa o "divergencias" para crear nuevas subculturas. Esto transformaría el mapa de una instantánea estática a una representación verdaderamente dinámica y evolutiva de la cultura humana, donde las identidades se mezclan, cambian y se crean con el tiempo.
    

  

### 1.4 Síntesis y Perspectivas: Un Modelo Unificado a Partir de la Mecánica de Juego

  

El análisis comparativo de estos tres sistemas de simulación revela patrones recurrentes y complementarios que pueden ser sintetizados en un modelo ontológico unificado y coherente para el proyecto.

La deconstrucción de estos sistemas de juego converge en una estructura jerárquica de tres capas para la definición de una cultura. Esta estructura es a la vez lógicamente sólida y potencialmente muy intuitiva para un usuario final.

1. Identidad Central (El "Porqué"): En la cima se encuentra un pequeño conjunto de principios fundamentales que definen la motivación central de la cultura. Esto corresponde a los Memes de Rimworld, la Ética fundamental de Dwarf Fortress y el Ethos de CKIII. Esta capa responde a la pregunta: "¿Cuál es la motivación fundamental de esta cultura?".
    
2. Prácticas y Normas (El "Cómo"): Debajo de la identidad central hay un conjunto más amplio y flexible de comportamientos, reglas y costumbres específicas. Esto se corresponde con los Preceptos de Rimworld y las Tradiciones de CKIII. Esta capa responde a: "¿Cómo expresan su identidad central en la vida cotidiana?".
    
3. Estructura Social (El "Quién"): La base de la estructura son los roles, las jerarquías y las instituciones que organizan la cultura. Esto se corresponde con los Roles Sociales de Rimworld y elementos de los tipos de gobierno y las leyes de sucesión de CKIII. Esta capa responde a: "¿Cómo se distribuye el poder y la responsabilidad?".
    

Este modelo de tres capas ofrece un flujo de trabajo natural para el usuario. Un usuario primero definiría el "Porqué" de su cultura (p. ej., "Ecologista"), lo que a su vez desbloquearía o sugeriría "Cómos" relevantes (p. ej., preceptos como "Veganismo" o tradiciones como "Guardianes del Bosque"), y finalmente definiría el "Quién" (p. ej., roles como "Guía Ecológico").

Además, los juegos presentan un espectro que va desde la prescripción directa hasta el comportamiento emergente. Rimworld es altamente prescriptivo: sus reglas causan directamente felicidad o tristeza en los personajes, centrándose en la experiencia interna de una cultura.6 Dwarf Fortress es más emergente: sus simples reglas éticas conducen a conflictos globales complejos y no guionizados, centrándose en las interacciones externas entre culturas.15 Dado que el proyecto del atlas busca permitir a los usuarios definir su propia cultura y verla en el contexto de otras, un enfoque híbrido es el más adecuado. La parte de autodefinición del usuario debe ser prescriptiva y modular, al estilo de Rimworld. La parte de interacción a nivel del mapa debe ser emergente, utilizando una comparación de valores éticos al estilo de Dwarf Fortress para calcular y visualizar dinámicamente las relaciones entre los diferentes polígonos culturales. Esto crea una experiencia mucho más rica que simplemente trazar definiciones estáticas.

|   |
|---|
|Tabla 1: Análisis Comparativo de la Simulación Cultural en Videojuegos|
|Categoría Ontológica (Propuesta)|
|Identidad/Motivación Central|
|Normas y Prácticas de Comportamiento|
|Estructura Social|
|Expresión Material/Estética|
|Mecánica de Evolución Cultural|

---

## Parte II: Marcos Fundacionales - Anclando la Ontología en la Teoría Sociológica

  
  

### Introducción

  

Para que el proyecto trascienda su inspiración lúdica y se convierta en una herramienta de análisis cultural seria, es imperativo conectar el modelo derivado de los videojuegos con marcos teóricos rigurosos y validados empíricamente de la sociología y la antropología. Este paso es fundamental para la credibilidad, la profundidad analítica y la utilidad a largo plazo del atlas. Anclar la ontología en la teoría académica garantiza que los datos generados por los usuarios no solo sean expresivos, sino también comparables y significativos dentro de un contexto científico más amplio.26

  

### 2.1 Análisis a Nivel Macro: Las Dimensiones Culturales de Hofstede como un "Lente"

  

El modelo de dimensiones culturales de Geert Hofstede es uno de los marcos más influyentes para la comparación de culturas a nivel nacional. Ofrece un vocabulario estandarizado para describir las tendencias generales de una sociedad.26

- Descripción del Marco: El modelo de Hofstede consta de seis dimensiones que cuantifican los valores culturales a lo largo de un espectro.26
    

1. Distancia al Poder (PDI): El grado en que los miembros menos poderosos de una sociedad aceptan y esperan que el poder se distribuya de manera desigual.32
    
2. Individualismo vs. Colectivismo (IDV): La preferencia por un marco social poco unido donde los individuos se cuidan a sí mismos y a su familia inmediata (individualismo) frente a un marco social muy unido donde los individuos esperan que sus parientes o miembros de un grupo los cuiden a cambio de lealtad (colectivismo).32
    
3. Masculinidad vs. Feminidad (MAS): La preferencia por el logro, el heroísmo, la asertividad y las recompensas materiales (masculinidad) frente a la preferencia por la cooperación, la modestia, el cuidado de los débiles y la calidad de vida (feminidad).32
    
4. Aversión a la Incertidumbre (UAI): El grado en que los miembros de una cultura se sienten incómodos con la incertidumbre y la ambigüedad, lo que a menudo se manifiesta en una necesidad de reglas y formalidad.32
    
5. Orientación a Largo Plazo vs. a Corto Plazo (LTO): El enfoque de una sociedad en las virtudes orientadas al futuro, como la perseverancia y el ahorro (orientación a largo plazo), frente a las virtudes relacionadas con el pasado y el presente, como el respeto por la tradición y el cumplimiento de las obligaciones sociales (orientación a corto plazo).31
    
6. Indulgencia vs. Contención (IVR): El grado en que una sociedad permite la gratificación libre de los impulsos humanos básicos y naturales relacionados con disfrutar de la vida y divertirse (indulgencia) frente a una sociedad que suprime la gratificación de las necesidades y la regula mediante normas sociales estrictas (contención).31
    

- Aplicación al Proyecto: El modelo de Hofstede no es adecuado para que los usuarios introduzcan directamente sus puntuaciones, ya que opera a un nivel de agregación nacional y requiere una metodología de encuesta específica. Sin embargo, proporciona un poderoso "lente" analítico para el atlas. La aplicación web puede agregar los componentes culturales definidos por los usuarios (del modelo inspirado en los juegos) dentro de una región geográfica determinada y calcular una puntuación de Hofstede emergente. Esto permitiría un análisis a nivel macro y la comparación de regiones en el mapa. Por ejemplo, el mapa podría codificarse por colores para mostrar regiones con un alto "Individualismo" o "Aversión a la Incertidumbre" emergentes, basados enteramente en los datos generados por los usuarios, ofreciendo una visualización única de las tendencias culturales globales.
    

  

### 2.2 Definición a Nivel Micro: La Teoría de los Valores Humanos Básicos de Schwartz como "Bloques de Construcción"

  

Mientras que el modelo de Hofstede es ideal para el análisis macro, la teoría de los valores humanos básicos de Shalom H. Schwartz ofrece un marco perfecto para la definición cultural a nivel individual y de grupo. Proporciona un vocabulario de motivaciones humanas que ha demostrado ser transculturalmente reconocido.35

- Descripción del Marco: La teoría de Schwartz identifica diez valores básicos y universales, diferenciados por su motivación subyacente. Estos valores son: Autodirección, Estimulación, Hedonismo, Logro, Poder, Seguridad, Conformidad, Tradición, Benevolencia y Universalismo.37 Una característica clave de la teoría es su estructura circular, que mapea las relaciones de conflicto y compatibilidad entre estos valores. Por ejemplo, la búsqueda de valores de 'Poder' a menudo entra en conflicto con la búsqueda de valores de 'Universalismo', mientras que 'Conformidad' y 'Seguridad' son compatibles.37
    
- Aplicación al Proyecto: El modelo de Schwartz es ideal para servir como la capa fundacional de la herramienta de definición del usuario, específicamente para la capa de "Identidad/Motivación Central" identificada en la Parte I. En lugar de que un usuario seleccione un "Meme" abstracto como "Individualista", podría calificar la importancia de valores subyacentes como 'Autodirección' y 'Logro' frente a 'Conformidad' y 'Tradición'. Esto proporciona una fuente de datos mucho más rica, matizada y académicamente sólida. La estructura circular del modelo puede ser utilizada directamente para construir la lógica interna del sistema de definición cultural.
    

  

### 2.3 Síntesis de un Modelo Ontológico Multicapa

  

La integración de las estructuras de juego intuitivas con los marcos sociológicos rigurosos permite la formulación de un modelo ontológico híbrido y multicapa que es a la vez expresivo y analíticamente potente.

- El Modelo Híbrido Propuesto: Este modelo formaliza la estructura de definición cultural de la aplicación web.
    

1. Capa 1: Valores Fundamentales (El "Porqué"): Basada en la Teoría de los Valores Básicos de Schwartz.35 Los usuarios definirán su cultura calificando la importancia de los 10 valores. Esto forma el núcleo motivacional.
    
2. Capa 2: Preceptos y Tradiciones (El "Cómo"): Una biblioteca de prácticas y normas específicas, inspirada en los Preceptos de Rimworld 5 y las Tradiciones de CKIII.20
    
3. Capa 3: Estructuras y Roles (El "Quién"): Un sistema para definir la organización social, inspirado en los Roles Sociales de Rimworld 6 y conceptos sociológicos de estructura social.40
    
4. Capa 4: Expresión Material (El "Qué"): Componentes para definir la estética, los artefactos, el idioma y los símbolos, basándose en la estética de CKIII 18 y las definiciones sociológicas de la cultura material.29
    

Este modelo propuesto no es simplemente un formulario estático, sino un sistema dinámico e interconectado. Las elecciones realizadas en la Capa 1 (Valores) influyen directamente en las opciones y probabilidades de la Capa 2 (Prácticas). La estructura de conflicto y congruencia del modelo de Schwartz 37 puede traducirse directamente en la lógica del sistema. Por ejemplo, si un usuario define una cultura con un alto valor de 'Poder' (Capa 1), la interfaz de usuario podría desincentivar visualmente o aumentar el "coste" de adoptar un precepto universalista en la Capa 2, como "Fronteras Abiertas". Esto ancla las elecciones del usuario en un marco psicológico validado y hace que el proceso de definir una cultura sea más significativo que simplemente elegir de una lista, conectando el "Porqué" con el "Cómo".

Además, un desafío clave para cualquier plataforma de contenido generado por el usuario es superar el "problema de la página en blanco". Los componentes basados en juegos ofrecen una solución elegante. En lugar de presentar a los usuarios un complejo marco sociológico desde cero, la plataforma puede ofrecer "plantillas culturales" predefinidas basadas directamente en los arquetipos de Rimworld, Dwarf Fortress y CKIII.7 Un usuario podría comenzar con una plantilla "Transhumanista" de Rimworld o una "Estoica" de CKIII. Esta plantilla rellenaría previamente las cuatro capas del modelo, que el usuario podría luego modificar y personalizar. Esto aprovecha la accesibilidad de los conceptos de juego como una puerta de entrada al modelo sociológico más profundo, reduciendo significativamente la barrera de entrada para la participación.

|   |
|---|
|Tabla 2: Ontología Cultural Híbrida Propuesta|
|Capa del Modelo|
|Capa 1: Valores Fundamentales (El "Porqué")|
|Capa 2: Preceptos y Tradiciones (El "Cómo")|
|Capa 3: Estructuras y Roles (El "Quién")|
|Capa 4: Expresión Material (El "Qué")|

---

## Parte III: Vías Arquitectónicas - Construyendo el Atlas Cultural Colaborativo

  
  

### Introducción

  

Esta sección traduce la ontología conceptual desarrollada en la Parte II en una arquitectura técnica concreta. Se evaluarán las herramientas de código abierto disponibles y se recomendará un conjunto de tecnologías que se alinee con los principios fundamentales del proyecto: apertura, colaboración y escalabilidad. El objetivo es diseñar un sistema robusto capaz de soportar una base de datos global de culturas generada por los usuarios y presentarla de manera intuitiva y dinámica.

  

### 3.1 La Fundación Geoespacial: El Mapa Interactivo

  

El corazón visual y funcional del proyecto es su mapa interactivo. La elección de la tecnología de mapeo front-end es, por lo tanto, una decisión crítica que afectará el rendimiento, la personalización y la facilidad de contribución al proyecto.

- Análisis de Precedentes: La revisión de proyectos existentes de Humanidades Digitales proporciona un contexto valioso. Proyectos como WorldMap del Center for Geographic Analysis y HyperCities demuestran la viabilidad de plataformas de mapeo histórico y cultural a gran escala y de carácter colaborativo.43 Otros proyectos de mapeo cultural y geográfico, como los que documentan el sur de Estados Unidos o las diásporas, muestran una variedad de enfoques para visualizar datos espaciales con narrativas culturales.44
    
- Comparación de Bibliotecas Front-End: El ecosistema de código abierto ofrece varias bibliotecas de mapeo maduras, cada una con sus propias fortalezas.
    

- Leaflet: Es una biblioteca ligera, minimalista y extremadamente popular. Sus principales ventajas son su simplicidad, su curva de aprendizaje suave, su tamaño reducido y un vasto ecosistema de complementos que amplían su funcionalidad.49 Es ideal para un prototipado rápido y para proyectos donde la facilidad de contribución de la comunidad es una prioridad. Su documentación y guías de inicio rápido son excelentes para principiantes.52
    
- OpenLayers: Es una biblioteca más completa y potente, a menudo descrita como un Sistema de Información Geográfica (SIG) completo en el navegador. Ofrece un soporte más robusto para diferentes proyecciones y formatos de datos de forma nativa, pero a costa de una mayor complejidad y un tamaño de archivo más grande.49
    
- MapLibre GL: Es una bifurcación de código abierto de Mapbox GL JS, creada después de que Mapbox cambiara su licencia a una propietaria.51 Su principal ventaja es el renderizado de alto rendimiento de teselas vectoriales a través de WebGL. Esto permite mapas más fluidos, estilos dinámicos del lado del cliente y una mejor experiencia visual, especialmente con grandes conjuntos de datos y altos niveles de interactividad.55
    

- Análisis de Plataformas Colaborativas: Plataformas como uMap, construida sobre OpenStreetMap y Leaflet, sirven como una prueba de concepto directa para el proyecto. uMap permite a los usuarios sin conocimientos técnicos crear mapas colaborativos, añadir puntos, líneas y polígonos, e importar datos, validando el flujo de trabajo central que el atlas cultural busca implementar.57
    
- Recomendación: Se propone un enfoque por fases para el front-end.
    

1. Fase de Prototipo (MVP): Utilizar Leaflet. Su simplicidad y la facilidad para que nuevos desarrolladores contribuyan la convierten en la opción ideal para construir rápidamente la funcionalidad principal y atraer a una comunidad de desarrolladores inicial.50
    
2. Fase de Escalamiento: A medida que la cantidad de polígonos culturales y datos asociados crezca, migrar o integrar MapLibre GL. Su rendimiento superior con teselas vectoriales será crucial para mantener una experiencia de usuario fluida y para implementar visualizaciones de datos complejas (p. ej., colorear dinámicamente miles de polígonos según su compatibilidad cultural).51
    

  

### 3.2 El Motor de Datos: Almacenando un Mundo de Culturas

  

El backend debe ser capaz de gestionar datos geoespaciales (los polígonos culturales), datos relacionales complejos (la ontología cultural de cuatro capas) y escalar para soportar potencialmente millones de contribuciones de usuarios de todo el mundo.

- Requisitos de la Base de Datos: El sistema debe soportar eficientemente consultas espaciales (p. ej., "encontrar todas las culturas en un radio de 500 km que tengan un alto valor de 'Seguridad'") y unir esos resultados con los datos culturales relacionales.
    
- Opciones Tecnológicas:
    

- PostgreSQL con la extensión PostGIS: Esta es la combinación estándar de la industria para bases de datos geoespaciales de código abierto. PostgreSQL es un sistema de gestión de bases de datos relacionales de objetos extremadamente robusto y maduro, mientras que PostGIS añade soporte para tipos de datos geográficos y consultas espaciales de alto rendimiento.62 Esta solución puede manejar sin problemas tanto los polígonos del mapa como la compleja estructura relacional de la ontología cultural.
    
- Bases de Datos Geoespaciales Especializadas: Soluciones como CrateDB están diseñadas para consultas geoespaciales en tiempo real, pero pueden ser menos flexibles para los complejos requisitos relacionales de la ontología cultural propuesta.63
    

- Arquitectura de Datos: Se propone un esquema que conecte una tabla geometries (que almacena los polígonos del mapa utilizando tipos de datos de PostGIS) con una tabla cultures. Esta tabla cultures, a su vez, se vinculará a tablas secundarias para values, precepts, roles y material_expressions, implementando fielmente el modelo ontológico de la Parte II.
    
- Conexión Front-end a Back-end: La arquitectura estándar para aplicaciones de mapeo web modernas implica la creación de una API (ya sea RESTful o GraphQL) en el servidor. Esta API consultará la base de datos PostGIS, formateará los resultados como GeoJSON (un formato estándar para datos geográficos en la web) y los enviará al cliente front-end (Leaflet/MapLibre GL) para su visualización.64
    

  

### 3.3 La Interfaz de Usuario: Una Gramática para Definir la Cultura

  

La interfaz de usuario (UI) es el puente entre la compleja ontología y el usuario final. Su diseño es fundamental para el éxito del proyecto.

- Flujo de Trabajo Conceptual: Se concibe un viaje de usuario claro y guiado:
    

1. Creación de una cuenta para atribuir las contribuciones.
    
2. Dibujar un polígono en el mapa para definir el corazón geográfico de su cultura.
    
3. Ser guiado a través del proceso de definición de cuatro capas, posiblemente a través de una interfaz de tipo "asistente" que explique cada paso.
    
4. Utilizar herramientas de visualización de datos (p. ej., gráficos de radar para los valores de Schwartz) para recibir retroalimentación inmediata sobre sus elecciones.
    
5. Enviar su definición cultural para su inclusión en el mapa global.
    

- Consideraciones Clave de UI/UX: La interfaz debe lograr un equilibrio delicado entre el poder expresivo y la facilidad de uso. Debe ser lo suficientemente simple para que un usuario casual pueda contribuir, pero lo suficientemente profunda para que un experto pueda definir matices culturales complejos. El uso de las "plantillas culturales" basadas en juegos, como se discutió en la Parte II, será una característica crucial de la UI para facilitar la incorporación de nuevos usuarios.
    

  

### 3.4 Perspectivas Arquitectónicas Integradas

  

El diseño de la arquitectura no es una decisión puramente técnica; debe reflejar y reforzar la filosofía del proyecto.

El ethos del proyecto es fundamentalmente abierto y colaborativo. La elección de tecnologías debe encarnar este principio. La solicitud del usuario de que la lógica del proyecto se gestione en GitHub implica una preferencia por la transparencia y la participación comunitaria no solo en los datos, sino en la plataforma misma [User Query]. Por lo tanto, optar por un conjunto de tecnologías completamente de código abierto —como Leaflet/MapLibre GL, PostGIS y un backend en Python/Node.js— es una decisión estratégica.51 A diferencia de las soluciones que incluyen componentes propietarios (como el uso de los servicios de pago de Mapbox 66), un enfoque totalmente de código abierto hace que todo el proyecto, desde el esquema de la base de datos hasta el código del front-end, sea bifurcable, auditable y extensible por la misma comunidad a la que sirve. Esta alineación filosófica es un factor crítico para el éxito a largo plazo y la aceptación de la comunidad.

Además, es fundamental reconocer que cada envío de un usuario no es un dato objetivo, sino una reivindicación subjetiva sobre la identidad cultural. La arquitectura debe estar diseñada para manejar esta ambigüedad inherente. A diferencia de muchos proyectos de Humanidades Digitales que tratan con datos históricos estáticos 43, este proyecto trata con datos vivos y, a menudo, disputados. Cuando un usuario dibuja un polígono, está haciendo una reivindicación espacial. ¿Qué sucede cuando los polígonos se superponen? ¿O cuando dos usuarios envían definiciones culturales radicalmente diferentes para el mismo lugar? La arquitectura no puede tratar esto como un simple conflicto de datos. Debe soportar características como el control de versiones (permitiendo ver cómo evoluciona la definición de una cultura con el tiempo), la atribución clara (dando crédito a los contribuidores) y, potencialmente, un mecanismo de "disputa" o "perspectiva alternativa". Esto significa que el backend debe parecerse más al historial de una wiki que a una base de datos SIG tradicional. Esta comprensión tiene profundas implicaciones para el esquema de la base de datos y el diseño de la API, exigiendo un enfoque en la historicidad y la atribución desde el primer día.

|   |
|---|
|Tabla 3: Matriz de Recomendación del Conjunto de Tecnologías|
|Componente|
|Biblioteca de Mapeo Front-End|
||
|Base de Datos Geoespacial Back-End|
||
|Framework de API Back-End|

---

## Parte IV: Gobernanza y Crecimiento - Cultivando un Proyecto Vivo

  
  

### Introducción

  

El éxito a largo plazo de un proyecto de esta magnitud y ambición depende tanto de sus sistemas humanos como de su código. Una arquitectura técnica sólida es necesaria, pero insuficiente. Es la comunidad que se forma en torno al proyecto —tanto los desarrolladores que lo construyen como los contribuidores que lo pueblan de datos— la que le dará vida y asegurará su sostenibilidad. Esta sección describe un marco para gestionar el desarrollo del software de código abierto y los datos culturales generados por los usuarios de una manera que sea saludable, productiva, transparente y resiliente.

  

### 4.1 Una Constitución de Código Abierto: Gestionando la Base de Código en GitHub

  

La gestión del proyecto en una plataforma pública como GitHub requiere un conjunto claro de reglas y procesos para facilitar la colaboración y mantener la calidad del código.67

- Establecimiento de Directrices Claras: La salud de un proyecto de código abierto comienza con una documentación fundamental en el repositorio.
    

- README.md: Debe articular claramente la visión del proyecto, sus objetivos, y proporcionar instrucciones claras sobre cómo empezar, tanto para usuarios como para desarrolladores potenciales.68
    
- CONTRIBUTING.md: Es esencial para delinear el proceso de contribución de código. Debe especificar los estándares de codificación, cómo configurar el entorno de desarrollo, el flujo de trabajo para las solicitudes de extracción (pull requests) y los criterios para su aceptación.68
    
- CODE_OF_CONDUCT.md: Un código de conducta explícito es no negociable. Establece el estándar para una interacción respetuosa y constructiva dentro de la comunidad de desarrolladores, asegurando que sea un espacio acogedor para todos.69
    

- Gestión Transparente del Proyecto: Las herramientas de GitHub deben ser utilizadas para gestionar el proceso de desarrollo de forma abierta.
    

- Issues y Plantillas: El uso de plantillas para informes de errores y solicitudes de características ayuda a estructurar los comentarios de la comunidad, asegurando que los mantenedores reciban toda la información necesaria para actuar.68
    
- Projects y Milestones: La herramienta GitHub Projects permite crear una hoja de ruta pública, ofreciendo transparencia sobre las prioridades y el progreso hacia los lanzamientos importantes.70
    
- Automatización con GitHub Actions: La automatización es clave para la eficiencia. Se deben configurar flujos de trabajo de GitHub Actions para la integración continua (ejecutar pruebas automáticamente en cada pull request), el triaje de issues y otras tareas repetitivas, liberando tiempo a los mantenedores.67
    

  

### 4.2 Moderación Comunitaria y Curación de Datos: Gestionando el Mapa

  

El mayor riesgo existencial para el proyecto no es técnico, sino social: el potencial de ser utilizado para promover el discurso de odio, el revisionismo histórico o para inflamar conflictos étnicos y nacionalistas. Una estrategia de moderación robusta y transparente es, por lo tanto, un requisito indispensable desde el primer día.

- Marco de Moderación Propuesto:
    

- Un Código de Conducta Público para Contribuidores: Distinto del CoC de los desarrolladores, este documento debe definir claramente el contenido aceptable para las definiciones culturales. Debe prohibir explícitamente el discurso de odio, la deshumanización de cualquier grupo y la negación de atrocidades históricas.
    
- Moderación Reactiva: Cada entrada cultural en el mapa debe tener un botón de "Reportar" fácil de usar. Esto permite a la comunidad señalar contenido problemático para que sea revisado por un equipo de moderación dedicado.69
    
- Moderación Proactiva: Se puede explorar el uso de herramientas de aprendizaje automático para escanear nuevas presentaciones en busca de palabras clave asociadas con el discurso de odio antes de que se publiquen.
    
- Un Proceso Transparente: Todas las acciones de moderación (p. ej., la eliminación de una entrada cultural) deben registrarse públicamente (protegiendo al mismo tiempo la privacidad del usuario) con una justificación clara basada en el Código de Conducta. Esto genera confianza y protege al proyecto de acusaciones de censura arbitraria.
    

- Gestión de Reivindicaciones Conflictivas: Como se identificó anteriormente, el sistema debe estar diseñado para manejar reivindicaciones culturales superpuestas y conflictivas. La solución no es que el proyecto arbitre la "verdad", sino que visualice la complejidad. La interfaz de usuario podría permitir a los usuarios alternar entre diferentes "capas" de reivindicaciones culturales en regiones disputadas, o utilizar técnicas visuales (como gradientes de color o patrones de sombreado) para mostrar áreas de alta contestación cultural. El objetivo es informar, no decretar.
    

  

### 4.3 Crecimiento por Fases y Participación Comunitaria

  

El lanzamiento y crecimiento del proyecto deben ser gestionados estratégicamente en fases para construir una base sólida.

- Fase 1: Finalización de la Ontología y Creación del Equipo Central: El enfoque inicial debe ser refinar el modelo cultural (Tabla 2) de forma abierta, utilizando GitHub Discussions para fomentar el debate. Esto atraerá a los primeros contribuidores interesados en la fase conceptual del proyecto.68
    
- Fase 2: Desarrollo del MVP: Construir la aplicación principal basada en el conjunto de tecnologías recomendado (Tabla 3). Realizar una fase alfa/beta cerrada con la comunidad inicial para recoger comentarios y corregir errores.
    
- Fase 3: Lanzamiento Público y Crecimiento Comunitario: Abrir la plataforma al público. La estrategia de crecimiento debe centrarse en la divulgación a comunidades relevantes: departamentos académicos de antropología y sociología, grupos de patrimonio cultural, y comunidades en línea interesadas en la construcción de mundos, la historia y la genealogía. El objetivo es sembrar el mapa con datos iniciales de alta calidad para demostrar el potencial del proyecto.
    

  

### 4.4 Perspectivas de Gobernanza Integradas

  

Una gobernanza eficaz requiere reconocer las complejidades estructurales de la comunidad del proyecto y su potencial impacto más allá de la propia plataforma.

El proyecto debe gestionar dos comunidades distintas pero superpuestas: la comunidad de desarrolladores en GitHub y la comunidad de contribuidores de contenido en la aplicación web. Los marcos de gobernanza de código abierto se centran principalmente en la primera.68 Sin embargo, la base de usuarios principal del proyecto serán contribuidores de contenido no técnicos. El modelo de gobernanza debe abordar a ambos. El repositorio de GitHub es el "gobierno" del código de la plataforma, pero es necesario establecer una estructura de gobernanza separada, aunque vinculada, para el contenido de la plataforma. Esto podría implicar la elección de moderadores comunitarios de entre la base de contribuidores, el establecimiento de un consejo de revisión de contenido y la creación de canales de comunicación claros entre las dos comunidades. No reconocer esta distinción conducirá inevitablemente a fallos de gobernanza.

Si tiene éxito, el proyecto creará un conjunto de datos sin precedentes, generado de forma colaborativa, sobre la identidad cultural humana. Este conjunto de datos tiene un enorme valor potencial para investigadores, educadores y responsables políticos. A diferencia de muchos proyectos académicos que se centran en visualizar datos existentes 44, este proyecto genera nuevos datos. Por lo tanto, el plan de gobernanza debe incluir una estrategia de licenciamiento de datos desde el primer día. Para maximizar su valor para la humanidad, los datos anonimizados deberían publicarse periódicamente en el dominio público o bajo una licencia permisiva (p. ej., Creative Commons). La arquitectura debe incluir una función de exportación de datos que se alinee con los estándares académicos. Esto posiciona al proyecto no solo como una herramienta de visualización, sino como un novedoso instrumento para las ciencias sociales, creando un círculo virtuoso en el que los investigadores utilizan los datos, publican hallazgos y, a su vez, atraen a más contribuidores a la plataforma.

---

## Conclusión y Recomendaciones por Fases

  

Este informe ha presentado un marco estratégico integral para el desarrollo de un Atlas Viviente de la Cultura Humana. El análisis concluye que el proyecto es conceptualmente sólido y técnicamente factible, con un potencial significativo para fomentar la comprensión intercultural a escala global. La estrategia central recomendada se basa en la síntesis de dos mundos aparentemente dispares: la accesibilidad de las mecánicas de simulación de videojuegos y el rigor de los marcos sociológicos.

La recomendación principal es construir el atlas sobre un modelo ontológico híbrido y multicapa. Este modelo debe estar anclado en la Teoría de los Valores Básicos de Schwartz como su núcleo motivacional, y utilizar una estructura de Preceptos, Estructuras y Expresiones Materiales inspirada en los sistemas de Rimworld: Ideology y Crusader Kings III para la definición detallada. Esta estructura dual ofrece una profundidad analítica sin sacrificar la intuición del usuario.

Desde el punto de vista técnico, el proyecto debe comprometerse con un conjunto de tecnologías totalmente de código abierto para alinearse con su ethos colaborativo. Se recomienda un enfoque por fases, comenzando con Leaflet para el prototipo y escalando a MapLibre GL para el rendimiento a largo plazo, todo ello respaldado por una base de datos PostgreSQL con PostGIS.

Finalmente, el éxito a largo plazo dependerá de una estructura de gobernanza dual y robusta, que gestione por separado pero de forma coordinada a la comunidad de desarrolladores en GitHub y a la comunidad de contribuidores de contenido en la plataforma. La moderación transparente y una estrategia clara de licenciamiento de datos no son opcionales, sino componentes esenciales del diseño del proyecto.

Para traducir esta estrategia en acción, se recomienda el siguiente plan de desarrollo por fases:

Fase 1: Finalización de la Ontología y Construcción de la Comunidad Inicial (Duración estimada: 3-6 meses)

- Objetivos Clave:
    

- Establecer el repositorio público en GitHub con los documentos fundacionales (README.md, CONTRIBUTING.md, CODE_OF_CONDUCT.md).
    
- Publicar el modelo ontológico propuesto (Tabla 2) como un borrador para la discusión pública.
    
- Utilizar GitHub Discussions para refinar y finalizar la ontología con los aportes de una comunidad inicial de expertos en sociología, antropología, diseño de juegos y desarrollo de software.
    
- Definir el esquema inicial de la base de datos y la especificación de la API.
    

- Resultado Esperado: Una ontología cultural finalizada y validada por la comunidad, y un equipo central de contribuidores comprometidos.
    

Fase 2: Desarrollo del Prototipo (Producto Mínimo Viable - MVP) (Duración estimada: 6-9 meses)

- Objetivos Clave:
    

- Desarrollar la funcionalidad principal de la aplicación web utilizando el conjunto de tecnologías recomendado (Leaflet + PostGIS).
    
- Implementar el flujo de trabajo completo del usuario: creación de cuenta, dibujo de polígonos y el proceso de definición cultural guiado por la ontología.
    
- Construir las herramientas básicas de moderación (función de reporte).
    
- Lanzar una versión beta cerrada para la comunidad inicial para pruebas y retroalimentación.
    

- Resultado Esperado: Una aplicación web funcional que permita a los usuarios definir y enviar sus culturas al mapa, lista para ser probada y mejorada.
    

Fase 3: Lanzamiento Público, Crecimiento y Gobernanza (Continuo)

- Objetivos Clave:
    

- Lanzar públicamente la plataforma.
    
- Implementar una estrategia de divulgación dirigida a instituciones académicas, grupos de patrimonio cultural y comunidades en línea relevantes para poblar el mapa.
    
- Establecer formalmente el equipo de moderación de contenido y los procesos de gobernanza comunitaria.
    
- Comenzar el trabajo de escalamiento técnico, incluyendo la posible migración a MapLibre GL a medida que el conjunto de datos crece.
    
- Publicar la primera exportación de datos anonimizados para la comunidad investigadora.
    

- Resultado Esperado: Un atlas cultural vivo y en crecimiento, una comunidad activa de contribuidores y desarrolladores, y el establecimiento del proyecto como una herramienta valiosa para la exploración y el análisis cultural.
    

#### Obras citadas

1. Simulation video game - Wikipedia, fecha de acceso: octubre 19, 2025, [https://en.wikipedia.org/wiki/Simulation_video_game](https://en.wikipedia.org/wiki/Simulation_video_game)
    
2. Game Studies 0102: Cultural framing of computer/video games. By Kurt Squire, fecha de acceso: octubre 19, 2025, [https://gamestudies.org/0102/squire/](https://gamestudies.org/0102/squire/)
    
3. (PDF) Dwarf Fortress: Laboratory and Homestead - ResearchGate, fecha de acceso: octubre 19, 2025, [https://www.researchgate.net/publication/281832877_Dwarf_Fortress_Laboratory_and_Homestead](https://www.researchgate.net/publication/281832877_Dwarf_Fortress_Laboratory_and_Homestead)
    
4. What are games that have featured emergent culture as a central element? i.e, games that are not just city or civilization sims, but culture sims? : r/truegaming - Reddit, fecha de acceso: octubre 19, 2025, [https://www.reddit.com/r/truegaming/comments/28l3j1/what_are_games_that_have_featured_emergent/](https://www.reddit.com/r/truegaming/comments/28l3j1/what_are_games_that_have_featured_emergent/)
    
5. Ideology (DLC) - RimWorld Wiki, fecha de acceso: octubre 19, 2025, [https://www.rimworldwiki.com/wiki/Ideology_(DLC)](https://www.rimworldwiki.com/wiki/Ideology_\(DLC\))
    
6. Guide :: IIdeology DLC - RimWorld - Steam Community, fecha de acceso: octubre 19, 2025, [https://steamcommunity.com/sharedfiles/filedetails/?id=2560400783](https://steamcommunity.com/sharedfiles/filedetails/?id=2560400783)
    
7. Vanilla Ideology Expanded - Memes And Structures - Rimworld Mod Rundown [1.5], fecha de acceso: octubre 19, 2025, [https://www.youtube.com/watch?v=TdB9Kpt9Upo](https://www.youtube.com/watch?v=TdB9Kpt9Upo)
    
8. Steam Workshop::Vanilla Ideology Expanded - Memes and Structures, fecha de acceso: octubre 19, 2025, [https://steamcommunity.com/sharedfiles/filedetails/?id=2636329500](https://steamcommunity.com/sharedfiles/filedetails/?id=2636329500)
    
9. Vanilla Ideology Expanded - Memes And Structures mod breakdown - YouTube, fecha de acceso: octubre 19, 2025, [https://www.youtube.com/watch?v=wslVttDqqnY](https://www.youtube.com/watch?v=wslVttDqqnY)
    
10. Vanilla Ideology Expanded - Memes and Structures showcase || More info in the comments : r/RimWorld - Reddit, fecha de acceso: octubre 19, 2025, [https://www.reddit.com/r/RimWorld/comments/peqrt5/vanilla_ideology_expanded_memes_and_structures/](https://www.reddit.com/r/RimWorld/comments/peqrt5/vanilla_ideology_expanded_memes_and_structures/)
    
11. RimWorld Console Edition Ideology | Memes and Precepts - YouTube, fecha de acceso: octubre 19, 2025, [https://www.youtube.com/watch?v=1pKGw3Psxos](https://www.youtube.com/watch?v=1pKGw3Psxos)
    
12. Ideology precepts? : r/RimWorld - Reddit, fecha de acceso: octubre 19, 2025, [https://www.reddit.com/r/RimWorld/comments/vnrr9l/ideology_precepts/](https://www.reddit.com/r/RimWorld/comments/vnrr9l/ideology_precepts/)
    
13. Ideology dlc considerations : r/RimWorld - Reddit, fecha de acceso: octubre 19, 2025, [https://www.reddit.com/r/RimWorld/comments/1kz4jvk/ideology_dlc_considerations/](https://www.reddit.com/r/RimWorld/comments/1kz4jvk/ideology_dlc_considerations/)
    
14. What do the DLC's add? :: RimWorld General Discussions - Steam Community, fecha de acceso: octubre 19, 2025, [https://steamcommunity.com/app/294100/discussions/0/3764479392876883777/](https://steamcommunity.com/app/294100/discussions/0/3764479392876883777/)
    
15. Ethic - Dwarf Fortress Wiki, fecha de acceso: octubre 19, 2025, [https://dwarffortresswiki.org/index.php/Ethic](https://dwarffortresswiki.org/index.php/Ethic)
    
16. DF2014:Ethic - Dwarf Fortress Wiki, fecha de acceso: octubre 19, 2025, [https://dwarffortresswiki.org/index.php/DF2014:Ethic](https://dwarffortresswiki.org/index.php/DF2014:Ethic)
    
17. dwarffortresswiki.org, fecha de acceso: octubre 19, 2025, [https://dwarffortresswiki.org/index.php/DF2014:Ethic#:~:text=Relationships%20between%20civilizations%20are%20based,trigger%20wars%20during%20world%20generation.](https://dwarffortresswiki.org/index.php/DF2014:Ethic#:~:text=Relationships%20between%20civilizations%20are%20based,trigger%20wars%20during%20world%20generation.)
    
18. Culture - CK3 Wiki, fecha de acceso: octubre 19, 2025, [https://ck3.paradoxwikis.com/Culture](https://ck3.paradoxwikis.com/Culture)
    
19. Crusader Kings III - Wikipedia, fecha de acceso: octubre 19, 2025, [https://en.wikipedia.org/wiki/Crusader_Kings_III](https://en.wikipedia.org/wiki/Crusader_Kings_III)
    
20. Traditions - CK3 Wiki, fecha de acceso: octubre 19, 2025, [https://ck3.paradoxwikis.com/Traditions](https://ck3.paradoxwikis.com/Traditions)
    
21. The Ultimate Guide to the Best Cultures in CK3 - Whole World - YouTube, fecha de acceso: octubre 19, 2025, [https://www.youtube.com/watch?v=K_Lhgbi_xCQ](https://www.youtube.com/watch?v=K_Lhgbi_xCQ)
    
22. Cultures - After the End Wiki - Miraheze, fecha de acceso: octubre 19, 2025, [https://aftertheend.miraheze.org/wiki/Cultures](https://aftertheend.miraheze.org/wiki/Cultures)
    
23. List of cultures - Official Godherja Wiki - Miraheze, fecha de acceso: octubre 19, 2025, [https://godherja.miraheze.org/wiki/List_of_cultures](https://godherja.miraheze.org/wiki/List_of_cultures)
    
24. CK3 Culture Guide for Beginners - YouTube, fecha de acceso: octubre 19, 2025, [https://www.youtube.com/watch?v=sxZs8W5DbzA](https://www.youtube.com/watch?v=sxZs8W5DbzA)
    
25. Crusader Kings 3 Technology & Culture Guide - YouTube, fecha de acceso: octubre 19, 2025, [https://www.youtube.com/watch?v=N-cS7paKvpg](https://www.youtube.com/watch?v=N-cS7paKvpg)
    
26. Dimensionalizing Cultures: The Hofstede Model in Context - ScholarWorks@GVSU, fecha de acceso: octubre 19, 2025, [https://scholarworks.gvsu.edu/cgi/viewcontent.cgi?article=1014&context=orpc](https://scholarworks.gvsu.edu/cgi/viewcontent.cgi?article=1014&context=orpc)
    
27. Cross-Cultural Analysis - Anthropology - The University of Alabama, fecha de acceso: octubre 19, 2025, [https://anthropology.ua.edu/theory/cross-cultural-analysis/](https://anthropology.ua.edu/theory/cross-cultural-analysis/)
    
28. Cultural Sociology (Chapter 3) - The Cambridge Handbook of Social Theory, fecha de acceso: octubre 19, 2025, [https://www.cambridge.org/core/books/cambridge-handbook-of-social-theory/cultural-sociology/B92048C7FB53C778F808876758F52D1B](https://www.cambridge.org/core/books/cambridge-handbook-of-social-theory/cultural-sociology/B92048C7FB53C778F808876758F52D1B)
    
29. Culture - Wikipedia, fecha de acceso: octubre 19, 2025, [https://en.wikipedia.org/wiki/Culture](https://en.wikipedia.org/wiki/Culture)
    
30. Hofstede's cultural dimensions theory | Research Starters - EBSCO, fecha de acceso: octubre 19, 2025, [https://www.ebsco.com/research-starters/business-and-management/hofstedes-cultural-dimensions-theory](https://www.ebsco.com/research-starters/business-and-management/hofstedes-cultural-dimensions-theory)
    
31. Intercultural Management - The Culture Factor Group, fecha de acceso: octubre 19, 2025, [https://www.hofstede-insights.com/models/national-culture/](https://www.hofstede-insights.com/models/national-culture/)
    
32. Hofstede's cultural dimensions theory - Wikipedia, fecha de acceso: octubre 19, 2025, [https://en.wikipedia.org/wiki/Hofstede%27s_cultural_dimensions_theory](https://en.wikipedia.org/wiki/Hofstede%27s_cultural_dimensions_theory)
    
33. Hofstede's Six Cultural Dimensions—and Why They Matter - Verywell Mind, fecha de acceso: octubre 19, 2025, [https://www.verywellmind.com/hofstedes-cultural-dimensions-8583990](https://www.verywellmind.com/hofstedes-cultural-dimensions-8583990)
    
34. Hofstede's Cultural Dimensions Theory - Simply Psychology, fecha de acceso: octubre 19, 2025, [https://www.simplypsychology.org/hofstedes-cultural-dimensions-theory.html](https://www.simplypsychology.org/hofstedes-cultural-dimensions-theory.html)
    
35. An Overview of the Schwartz Theory of Basic Values - ScholarWorks@GVSU, fecha de acceso: octubre 19, 2025, [https://scholarworks.gvsu.edu/cgi/viewcontent.cgi?article=1116&context=orpc](https://scholarworks.gvsu.edu/cgi/viewcontent.cgi?article=1116&context=orpc)
    
36. An Overview of the Schwartz Theory of Basic Values - ScholarWorks@GVSU, fecha de acceso: octubre 19, 2025, [https://scholarworks.gvsu.edu/orpc/vol2/iss1/11/](https://scholarworks.gvsu.edu/orpc/vol2/iss1/11/)
    
37. Theory of basic human values - Wikipedia, fecha de acceso: octubre 19, 2025, [https://en.wikipedia.org/wiki/Theory_of_basic_human_values](https://en.wikipedia.org/wiki/Theory_of_basic_human_values)
    
38. The Schwartz Theory of Basic Values and Some Implications for Political Philosophy, fecha de acceso: octubre 19, 2025, [https://irfankhawajaphilosopher.com/2015/08/12/the-schwartz-theory-of-basic-values-and-some-implications-for-political-philosophy/](https://irfankhawajaphilosopher.com/2015/08/12/the-schwartz-theory-of-basic-values-and-some-implications-for-political-philosophy/)
    
39. Understanding values: Schwartz theory of basic values, fecha de acceso: octubre 19, 2025, [https://i2insights.org/2022/05/10/schwartz-theory-of-basic-values/](https://i2insights.org/2022/05/10/schwartz-theory-of-basic-values/)
    
40. Sociocultural anthropology - Wikipedia, fecha de acceso: octubre 19, 2025, [https://en.wikipedia.org/wiki/Sociocultural_anthropology](https://en.wikipedia.org/wiki/Sociocultural_anthropology)
    
41. Defining culture and society from the perspectives of ANTHROPOLOGY AND SOCIOLOGY, fecha de acceso: octubre 19, 2025, [https://www.slideshare.net/slideshow/defining-culture-and-society-from-the-perspectives-of-anthropology-and-sociology/168297150](https://www.slideshare.net/slideshow/defining-culture-and-society-from-the-perspectives-of-anthropology-and-sociology/168297150)
    
42. Culture: Values, Norms and Material Objects | Research Starters - EBSCO, fecha de acceso: octubre 19, 2025, [https://www.ebsco.com/research-starters/religion-and-philosophy/culture-values-norms-and-material-objects](https://www.ebsco.com/research-starters/religion-and-philosophy/culture-values-norms-and-material-objects)
    
43. Projects & Groups · Spatial Humanities, fecha de acceso: octubre 19, 2025, [https://spatial.scholarslab.org/project/](https://spatial.scholarslab.org/project/)
    
44. Digital Humanities Projects @ UNC, fecha de acceso: octubre 19, 2025, [https://dhprojects.web.unc.edu/](https://dhprojects.web.unc.edu/)
    
45. Projects - Digital Humanities @ Stanford, fecha de acceso: octubre 19, 2025, [https://digitalhumanities.stanford.edu/projects/](https://digitalhumanities.stanford.edu/projects/)
    
46. Projects and Initiatives - Digital Humanities - NC State University, fecha de acceso: octubre 19, 2025, [https://dh.chass.ncsu.edu/projects/](https://dh.chass.ncsu.edu/projects/)
    
47. Digital Humanities Projects - The University of Southern Mississippi, fecha de acceso: octubre 19, 2025, [https://www.usm.edu/digital-humanities/digital-humanities-projects.php](https://www.usm.edu/digital-humanities/digital-humanities-projects.php)
    
48. Projects - Critical Digital Humanities Initiative - University of Toronto, fecha de acceso: octubre 19, 2025, [https://dhn.utoronto.ca/research/current-projects/](https://dhn.utoronto.ca/research/current-projects/)
    
49. Comparing Mapbox, Leaflet, and OpenLayers - Bac Ha Software (BHSoft), fecha de acceso: octubre 19, 2025, [https://bachasoftware.com/blog/insights-2/comparing-mapbox-openlayers-and-leaflet-30](https://bachasoftware.com/blog/insights-2/comparing-mapbox-openlayers-and-leaflet-30)
    
50. Leaflet adoption guide: Overview, examples, and alternatives - LogRocket Blog, fecha de acceso: octubre 19, 2025, [https://blog.logrocket.com/leaflet-adoption-guide/](https://blog.logrocket.com/leaflet-adoption-guide/)
    
51. Map libraries popularity: Leaflet vs MapLibre GL vs OpenLayers - Geoapify, fecha de acceso: octubre 19, 2025, [https://www.geoapify.com/map-libraries-comparison-leaflet-vs-maplibre-gl-vs-openlayers-trends-and-statistics/](https://www.geoapify.com/map-libraries-comparison-leaflet-vs-maplibre-gl-vs-openlayers-trends-and-statistics/)
    
52. Quick Start Guide - Leaflet - a JavaScript library for interactive maps, fecha de acceso: octubre 19, 2025, [https://leafletjs.com/examples/quick-start/](https://leafletjs.com/examples/quick-start/)
    
53. Tutorials - Leaflet - a JavaScript library for interactive maps, fecha de acceso: octubre 19, 2025, [https://leafletjs.com/examples.html](https://leafletjs.com/examples.html)
    
54. A Beginner's Guide to Creating a Map Using Leaflet.js - SitePoint, fecha de acceso: octubre 19, 2025, [https://www.sitepoint.com/leaflet-create-map-beginner-guide/](https://www.sitepoint.com/leaflet-create-map-beginner-guide/)
    
55. I've struggled to understand the relationship between Mapbox, Mapbox Studio, Map... | Hacker News, fecha de acceso: octubre 19, 2025, [https://news.ycombinator.com/item?id=27607050](https://news.ycombinator.com/item?id=27607050)
    
56. 5 JavaScript mapping APIs compared - LogRocket Blog, fecha de acceso: octubre 19, 2025, [https://blog.logrocket.com/javascript-mapping-apis-compared/](https://blog.logrocket.com/javascript-mapping-apis-compared/)
    
57. uMap lets you create maps with OpenStreetMap layers in a minute and embed them in your site. - GitHub, fecha de acceso: octubre 19, 2025, [https://github.com/umap-project/umap](https://github.com/umap-project/umap)
    
58. Online map creator - uMap project, fecha de acceso: octubre 19, 2025, [https://umap-project.org/](https://umap-project.org/)
    
59. Collaborative mapping - Wikipedia, fecha de acceso: octubre 19, 2025, [https://en.wikipedia.org/wiki/Collaborative_mapping](https://en.wikipedia.org/wiki/Collaborative_mapping)
    
60. uMap: create quick interactive maps – UQ Library Technology Training, fecha de acceso: octubre 19, 2025, [https://uqlibrary.github.io/technology-training/uMap/umap_intro.html](https://uqlibrary.github.io/technology-training/uMap/umap_intro.html)
    
61. uMap - Online map creator, fecha de acceso: octubre 19, 2025, [https://umap.openstreetmap.fr/en/](https://umap.openstreetmap.fr/en/)
    
62. 9 Ways to Integrate User-Generated Content Into Maps That Transform Data, fecha de acceso: octubre 19, 2025, [https://www.maplibrary.org/1601/integrating-user-generated-content-into-mapping-projects/](https://www.maplibrary.org/1601/integrating-user-generated-content-into-mapping-projects/)
    
63. Open Source Analytical Database for Geospatial Data - CrateDB, fecha de acceso: octubre 19, 2025, [https://cratedb.com/data-model/geospatial](https://cratedb.com/data-model/geospatial)
    
64. Accessing External Data Sources | Leaflet.js Succinctly | Syncfusion®, fecha de acceso: octubre 19, 2025, [https://www.syncfusion.com/succinctly-free-ebooks/leafletjs/accessing-external-data-sources](https://www.syncfusion.com/succinctly-free-ebooks/leafletjs/accessing-external-data-sources)
    
65. Chapter 13 Collaborative Mapping | Introduction to Web Mapping, fecha de acceso: octubre 19, 2025, [https://geobgu.xyz/web-mapping/collaborative-mapping.html](https://geobgu.xyz/web-mapping/collaborative-mapping.html)
    
66. Leaflet or Mapbox? Choosing the Right Tool for Interactive Maps | by Visarsoft - Medium, fecha de acceso: octubre 19, 2025, [https://medium.com/visarsoft-blog/leaflet-or-mapbox-choosing-the-right-tool-for-interactive-maps-53dea7cc3c40](https://medium.com/visarsoft-blog/leaflet-or-mapbox-choosing-the-right-tool-for-interactive-maps-53dea7cc3c40)
    
67. Build community-driven software projects on GitHub - Training - Microsoft Learn, fecha de acceso: octubre 19, 2025, [https://learn.microsoft.com/en-us/training/paths/build-community-driven-projects-github/](https://learn.microsoft.com/en-us/training/paths/build-community-driven-projects-github/)
    
68. What are the best practices for maintaining a large open-source project on GitHub? · community · Discussion #153817, fecha de acceso: octubre 19, 2025, [https://github.com/orgs/community/discussions/153817](https://github.com/orgs/community/discussions/153817)
    
69. About community management and moderation - GitHub Docs, fecha de acceso: octubre 19, 2025, [https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/about-community-management-and-moderation](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/about-community-management-and-moderation)
    
70. Best practices for Projects - GitHub Docs, fecha de acceso: octubre 19, 2025, [https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/best-practices-for-projects](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/best-practices-for-projects)
    
71. USGS Geospatial Data Sources | U.S. Geological Survey, fecha de acceso: octubre 19, 2025, [https://www.usgs.gov/educational-resources/usgs-geospatial-data-sources](https://www.usgs.gov/educational-resources/usgs-geospatial-data-sources)
    

**