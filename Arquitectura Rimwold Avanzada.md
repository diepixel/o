**  

# Deconstruyendo el Rim: Un Plano Arquitectónico para el Modding Avanzado

  
  

## Sección 1: El Ecosistema de Modding y el Conjunto de Herramientas Fundamentales

  

Para embarcarse en la creación de modificaciones complejas para RimWorld, es imperativo trascender el enfoque de un aficionado y adoptar la mentalidad y las herramientas de un desarrollador de software profesional. Esta sección establece el entorno de desarrollo, presenta las herramientas de análisis esenciales y describe el panorama de la comunidad, que en conjunto forman la base para cualquier proyecto de modding ambicioso.

  

### 1.1. Configuración de su Entorno de Desarrollo

  

La transición de la edición de datos a la creación de nueva lógica de juego exige un conjunto de herramientas profesionales. Mientras que las modificaciones simples pueden realizarse con herramientas básicas, los sistemas complejos, especialmente aquellos que involucran IA y modelos de lenguaje, requieren un entorno de desarrollo integrado (IDE) y herramientas de análisis de código.

  

#### El IDE es Innegociable

  

Si bien las ediciones simples de XML se pueden realizar en cualquier editor de texto 1, el desarrollo serio en C#, el lenguaje de programación que impulsa la lógica de

RimWorld, exige un IDE completo. El estándar de la comunidad y la herramienta recomendada es Visual Studio 2022 Community Edition, que es gratuito para desarrolladores individuales y ofrece un conjunto robusto de características para la codificación, depuración y compilación.3 Como alternativa, JetBrains Rider es una opción potente, especialmente valorada por su rendimiento y sus capacidades multiplataforma, siendo gratuita para estudiantes.3

La elección de un IDE no es una mera preferencia; es un requisito para gestionar eficientemente las complejidades del código C#, navegar por las dependencias del proyecto y depurar la lógica del mod en tiempo de ejecución.

  

#### Configuración de la Solución

  

La configuración correcta del proyecto es un paso crítico para garantizar que el juego pueda cargar y ejecutar el código del mod. El proceso implica la creación de un proyecto de Biblioteca de Clases C# que se dirija específicamente a la versión del.NET Framework utilizada por RimWorld, que es la 4.7.2.3

El procedimiento estándar en Visual Studio es el siguiente:

1. Crear un nuevo proyecto: Seleccione la plantilla "Biblioteca de clases (.NET Framework)".
    
2. Establecer el Framework: Asegúrese de que la versión del framework de destino esté configurada en.NET Framework 4.7.2. Un desajuste aquí provocará que el juego no pueda cargar el ensamblado del mod.
    
3. Añadir Referencias: El proyecto debe hacer referencia a los ensamblados principales del juego para poder interactuar con su código. Las dos referencias indispensables son Assembly-CSharp.dll (que contiene todo el código del juego) y UnityEngine.CoreModule.dll (parte del motor Unity). Estas se encuentran en el directorio RimWorld..._Data/Managed/ de la instalación del juego.4
    
4. Configurar la Ruta de Salida: La propiedad de compilación del proyecto debe modificarse para que el archivo .dll resultante se guarde directamente en la carpeta Assemblies dentro de la estructura de carpetas de su mod. Esto automatiza el proceso de despliegue durante el desarrollo.4
    

  

#### Herramientas Esenciales para el Análisis

  

La documentación oficial para el modding de RimWorld es notoriamente escasa e incompleta.7 En la práctica, la comunidad de modding avanzado trata el código compilado del juego como la documentación principal. Para leer este código, se utilizan herramientas especializadas conocidas como descompiladores. Estas no son opcionales para el desarrollo avanzado; son la principal vía para comprender las mecánicas internas del juego.

- Descompiladores (ILSpy, dnSpy): Estas herramientas toman un ensamblado .dll compilado y lo revierten a un código fuente C# legible. ILSpy es conocido por su velocidad y simplicidad, mientras que dnSpy ofrece características más avanzadas, incluida la capacidad de depurar ensamblados en tiempo de ejecución.3 La capacidad de poner puntos de interrupción y examinar el estado del juego en vivo con dnSpy es invaluable para diagnosticar problemas complejos. La dependencia de la comunidad en estas herramientas revela una verdad fundamental sobre el modding de  
    RimWorld: es una forma de ingeniería inversa. Para crear mods complejos, es necesario ser capaz y estar dispuesto a leer el propio código del juego.
    

  

### 1.2. La Anatomía de una Carpeta de Mod de RimWorld

  

La estructura de carpetas de un mod no es arbitraria; sigue una convención que el motor del juego utiliza para descubrir y cargar diferentes tipos de activos. Una estructura bien organizada es el primer paso para un mod funcional.

- About: Contiene el archivo About.xml, que proporciona metadatos sobre el mod (nombre, autor, descripción, versiones compatibles) que se muestran en el menú de mods del juego.9
    
- Defs: Este es el corazón de cualquier mod basado en contenido. Contiene los archivos XML que definen todos los nuevos objetos, criaturas, plantas, investigaciones, etc..1
    
- Patches: Contiene archivos XML que no añaden nuevo contenido, sino que modifican los Defs existentes (del juego base u otros mods) de forma segura y compatible.1
    
- Assemblies: Aquí es donde se coloca el archivo .dll compilado que contiene todo el código C# del mod.2
    
- Textures: Almacena todos los archivos de imagen (generalmente en formato.png) para los objetos, la interfaz de usuario y las criaturas del mod.9
    

Comprender esta estructura es esencial para que el juego cargue correctamente todos los componentes del mod.

  

### 1.3. Navegando por la Base de Conocimiento de la Comunidad

  

Dado que la documentación oficial es limitada, el conocimiento colectivo de la comunidad es el recurso más valioso. Sin embargo, este conocimiento está distribuido en varias plataformas, y saber dónde buscar es clave.

- El Discord No Oficial de RimWorld: Este servidor se ha convertido en el centro neurálgico para las discusiones técnicas sobre modding. Canales como #mod-development son frecuentados por algunos de los modders más experimentados de la comunidad, lo que lo convierte en el mejor lugar para obtener respuestas a preguntas complejas y mantenerse al día con las mejores prácticas.3
    
- Subreddits y Foros: El subreddit r/rimworldmodding es un recurso útil para plantear preguntas específicas y compartir avances.13 Históricamente, los foros oficiales de Ludeon eran un centro importante, pero su actividad ha disminuido significativamente y ahora están congelados y archivados, principalmente debido a problemas con la actividad de bots, sirviendo más como un recurso histórico que como una comunidad activa.14
    

La participación activa en estos espacios comunitarios no solo proporciona respuestas, sino que también ofrece una visión de los problemas comunes, las soluciones elegantes y las innovaciones que están empujando los límites de lo que es posible en el juego.

  

## Sección 2: La Capa de Datos - Dominando XML y el Sistema de Defs

  

La arquitectura de RimWorld se fundamenta en un principio de diseño elegante y potente: una separación casi total entre los datos y la lógica. Los archivos XML definen el qué —las propiedades de cada objeto, criatura y concepto en el juego— mientras que el código C# define el cómo —el comportamiento y las interacciones de esos elementos. Comprender esta dicotomía es el primer paso para crear contenido que no solo funcione, sino que se sienta nativo del juego y coexista armoniosamente con el vasto ecosistema de mods.

  

### 2.1. La Arquitectura Impulsada por Datos

  

A diferencia de muchos juegos donde los atributos de los objetos están codificados directamente en el programa, RimWorld expone una gran cantidad de sus datos en archivos de Lenguaje de Marcado Extensible (XML).2 Estos archivos no son código; no ejecutan lógica. Son, en esencia, archivos de configuración estructurados que contienen valores, texto y referencias.2 Esta decisión de diseño es la que hace que

RimWorld sea tan excepcionalmente modificable.

  

#### Defs como Planos

  

El término central en el modding de XML de RimWorld es Def, una abreviatura de "Definition" (Definición). Un Def es un plano, una receta o una lista de ingredientes que el motor del juego (el código C#) utiliza para instanciar un objeto real en el mundo del juego.2 Es crucial entender esta distinción: un

ThingDef para un rifle de asalto no es un rifle de asalto; es la plantilla que contiene toda la información necesaria para que el juego cree uno, como su masa, el daño que inflige, el tiempo de enfriamiento, los materiales necesarios para su fabricación y la ruta a su archivo de textura.2 Lo que los jugadores ven e interactúan en el juego no son los

Defs, sino los Things (objetos) creados a partir de ellos.2

  

### 2.2. El Poder de la Herencia

  

El sistema de Defs de RimWorld implementa un robusto sistema de herencia, una práctica de desarrollo de software que promueve el principio de "No te repitas" (DRY - Don't Repeat Yourself). En lugar de definir cada atributo para cada objeto desde cero, los modders pueden heredar de plantillas base, sobrescribiendo solo los valores que necesitan cambiar. Esto no solo ahorra tiempo, sino que es fundamental para la mantenibilidad y la compatibilidad.

  

#### Herencia en la Práctica: ParentName

  

La herencia se logra a través del atributo ParentName. Cuando un Def especifica un ParentName, automáticamente copia todos los nodos y valores del Def base (el "padre") cuyo atributo Name coincide.18 El

Def hijo puede entonces añadir nuevos nodos o redefinir los existentes. Si un hijo define un nodo que ya existe en el padre (por ejemplo, <mass>), el valor del hijo anula al del padre.19

  

#### Defs Abstractos como Plantillas

  

El sistema de herencia se vuelve verdaderamente poderoso con el uso de Defs abstractos. Un Def marcado con el atributo Abstract="True" no es cargado por el juego como un objeto tangible. Su único propósito es servir como una plantilla base para que otros Defs hereden de ella.18 La jerarquía de contenido del juego base está construida sobre estas plantillas abstractas.

Un ejemplo clásico es la creación de armas. Un modder no crearía un nuevo rifle desde cero. En su lugar, seguiría una cadena de herencia:

1. BaseWeapon: Un Def abstracto que contiene propiedades comunes a todas las armas, como las estadísticas de calidad y el deterioro.
    
2. BaseGun: Hereda de BaseWeapon y añade propiedades específicas de las armas de fuego, como el sonido de disparo y la clase de verbo de ataque a distancia.
    
3. BaseMakeableGun: Hereda de BaseGun y añade la información necesaria para que el arma sea fabricable en una mesa de mecanizado, como el tiempo de trabajo y los requisitos de habilidad.18
    

Al heredar de BaseMakeableGun, un nuevo rifle adquiere instantáneamente docenas de propiedades necesarias, dejando al modder la tarea de definir solo los atributos únicos, como el daño, el alcance y la apariencia.

  

#### Manejo de Listas en la Herencia

  

Una peculiaridad crítica y a menudo confusa de la herencia de Defs es cómo maneja las listas (nodos que contienen múltiples elementos <li>). A diferencia de los valores únicos que se sobrescriben, las listas se añaden o concatenan.19 Si un

Def padre tiene una lista de <weaponTags> y el Def hijo también define una lista de <weaponTags>, el objeto final tendrá todos los tags de ambos, los del padre seguidos por los del hijo.

Este comportamiento es a menudo deseado, pero si se necesita reemplazar completamente la lista del padre, se debe añadir el atributo Inherit="False" al nodo de la lista en el Def hijo. Esto le indica al motor que ignore la lista del padre para ese nodo específico, mientras que el resto de las propiedades se heredan normalmente.19

  

### 2.3. Modificando Contenido de Forma Segura: Parches XML

  

Una de las reglas de oro del modding de RimWorld es nunca modificar directamente los archivos del juego base. Hacerlo no solo es una mala práctica que se pierde con cada actualización del juego, sino que crea conflictos de incompatibilidad inmediatos con cualquier otro mod que intente modificar el mismo Def.1

La solución arquitectónica proporcionada por el juego es el sistema de parches. Los mods deben colocar sus modificaciones en archivos XML dentro de una carpeta Patches. Estos archivos no definen Defs completos, sino que contienen una serie de PatchOperation (Operaciones de Parche).

Una PatchOperation es una instrucción que le dice al juego cómo modificar un Def existente en tiempo de carga. Utiliza el lenguaje de consulta XPath para apuntar con precisión a un nodo específico dentro de la estructura XML de un Def y luego realiza una acción sobre él. Las operaciones más comunes son:

- PatchOperationAdd: Añade un nuevo nodo XML en la ubicación especificada por el XPath.
    
- PatchOperationReplace: Reemplaza el contenido del nodo seleccionado con un nuevo valor.
    
- PatchOperationRemove: Elimina por completo el nodo seleccionado.1
    

Por ejemplo, para aumentar el daño de la pistola del juego base, un mod no editaría el ThingDef de la pistola. En su lugar, crearía un parche con una PatchOperationReplace que apunta al nodo <power> dentro del ThingDef con defName="Gun_Pistol" y lo reemplaza con un valor más alto. Este enfoque garantiza que múltiples mods puedan modificar diferentes aspectos del mismo objeto sin entrar en conflicto directo, ya que el juego aplica todos los parches de forma secuencial. La combinación de crear nuevo contenido a través de la herencia y modificar contenido existente a través de parches es el patrón central y la mejor práctica para todo el modding basado en XML.

  

## Sección 3: La Capa de Lógica - Ensamblados C# y Parches con Harmony

  

Si la capa de datos XML define la anatomía de RimWorld, la capa de lógica C# es su sistema nervioso central. Aquí es donde residen los comportamientos, las mecánicas y la inteligencia que dan vida al juego. Para crear mods que introduzcan nuevas funcionalidades, en lugar de simplemente redefinir datos existentes, es necesario cruzar el umbral hacia la programación en C#. Esta sección explora cómo el código C# se integra en el juego y se centra en Harmony, la biblioteca de software que ha hecho posible el próspero ecosistema de modding avanzado de RimWorld.

  

### 3.1. De Código C# a Lógica de Juego

  

El código fuente escrito en C# no es leído directamente por el juego. Debe ser compilado en un archivo de biblioteca de enlace dinámico (.dll), conocido como un ensamblado. Este archivo .dll se coloca en la carpeta Assemblies del mod y es cargado por RimWorld en el momento del arranque.2 Este ensamblado contiene clases y métodos que el motor del juego puede invocar para ejecutar la lógica personalizada del mod.

  

#### Conectando XML con C#

  

La arquitectura de RimWorld proporciona un puente elegante entre la capa de datos y la capa de lógica. Ciertos nodos dentro de un Def XML actúan como punteros a clases C# específicas. Cuando el juego instancia un objeto a partir de un Def, busca estos nodos para saber qué código debe ejecutar para gestionar el comportamiento de ese objeto. Algunos ejemplos clave incluyen:

- <thingClass>: En un ThingDef, este nodo especifica la clase C# que representará al objeto en el juego. Por ejemplo, un ThingDef para una torreta podría apuntar a una clase C# personalizada que herede de Building_Turret para implementar una lógica de apuntado única.
    
- <workerClass>: Se utiliza en Defs como RecipeDef o ResearchProjectDef para apuntar a una clase que gestiona la lógica de "trabajo" (por ejemplo, cómo se completa una receta o una investigación).
    
- <compClass>: Permite adjuntar componentes de comportamiento modulares a un Thing. Por ejemplo, se podría añadir un Comp a un arma que le dé la capacidad de recargarse con el tiempo, encapsulando esa lógica en una clase C# separada.17
    

Esta conexión permite a los modders crear sus propias clases C# para implementar comportamientos completamente nuevos y luego "adjuntarlos" a objetos del juego a través de simples entradas XML.

  

### 3.2. Harmony: La API de Modding Universal

  

El mayor desafío en el modding de lógica de juego es cómo modificar el comportamiento del código base sin reemplazar los archivos del juego. Si cada mod C# tuviera que distribuir su propia versión modificada del archivo Assembly-CSharp.dll del juego, sería imposible ejecutar más de un mod de este tipo a la vez. Esto crearía un ecosistema de mods mutuamente excluyentes y plagado de conflictos.

Harmony es la solución a este problema fundamental. Es una biblioteca C# de código abierto que se ha convertido en el estándar de facto para el modding de RimWorld y otros juegos basados en Unity. Harmony no modifica ningún archivo en el disco; en su lugar, realiza "parches en tiempo de ejecución".24

  

#### Cómo Funciona Harmony

  

Harmony utiliza una técnica avanzada llamada "hooking de métodos" o "detouring". En el momento en que el juego se está cargando, Harmony permite a los mods inyectar su propio código en métodos existentes del juego. Esto significa que un mod puede ejecutar su propia lógica antes de que se ejecute un método del juego, después de que se ejecute, o incluso en lugar de él. Como estas modificaciones ocurren en la memoria durante la ejecución, múltiples mods pueden parchear el mismo método del juego de forma cooperativa, creando una cadena de modificaciones que se aplican una tras otra.2

La crisis que rodeó la actualización a Harmony 2.0 en la comunidad de modding subraya su importancia crítica: cuando Harmony experimenta problemas, todo el ecosistema de mods C# se ve afectado, demostrando que es el pilar sobre el que se construye el modding avanzado.25

  

#### Parches Prácticos con Harmony

  

Harmony ofrece varios tipos de parches, cada uno con un propósito específico:

- Prefix (Prefijo): Un método de parche Prefix se ejecuta justo antes del método original del juego. Los Prefijos son extremadamente potentes. Pueden leer y modificar los argumentos que se pasan al método original. También pueden devolver un valor booleano: si un Prefijo devuelve false, la ejecución del método original se salta por completo, permitiendo que un mod lo reemplace eficazmente.
    
- Postfix (Posfijo): Un método de parche Postfix se ejecuta justo después de que el método original del juego haya completado su ejecución. Los Postfixes pueden leer los argumentos originales y, lo que es más importante, pueden leer y modificar el valor de retorno del método original. Esto es útil para alterar el resultado de un cálculo del juego sin tener que reescribir toda la lógica.
    
- Transpiler (Transpilador): Este es el tipo de parche más avanzado y complejo. Un Transpilador opera a un nivel más bajo, directamente sobre el Lenguaje Intermedio (IL) del método original. Permite a un mod reescribir el código del método instrucción por instrucción en tiempo de carga. Los Transpiladores se utilizan para realizar optimizaciones de rendimiento quirúrgicas o para cambiar la lógica interna de un método de formas que no son posibles con Prefijos o Postfixes.
    

La capacidad de inyectar lógica de esta manera es lo que permite la creación de mods que alteran profundamente las mecánicas del juego. Para un proyecto que busca integrar un modelo de lenguaje grande (LLM) para influir en el comportamiento de los peones, Harmony es indispensable. Será necesario utilizar Harmony para parchear los métodos de toma de decisiones del peón, como JobGiver.TryGiveJob, para insertar la influencia del LLM en el bucle de la IA nativa del juego.

  

## Sección 4: Inmersión Arquitectónica Profunda - Deconstruyendo los Sistemas Centrales del Juego

  

Esta sección constituye el núcleo de este informe, diseccionando los sistemas de juego fundamentales de RimWorld. Se analizará la intrincada interacción entre los Defs de XML y las clases C# que los gobiernan, revelando la lógica subyacente que impulsa la simulación. Comprender estas arquitecturas es un requisito previo para crear mods que se integren de manera significativa y estable con las mecánicas del juego, especialmente para un proyecto tan ambicioso como la integración de un LLM en la IA de los peones.

  

### 4.1. La Anatomía de un Peón

  

Los "peones" (pawns) son el corazón de la simulación de RimWorld. Cada colono, miembro de una tribu, pirata o animal es una instancia de un peón. Su generación no es un proceso monolítico, sino una construcción en capas a partir de múltiples Defs.

- Del Plano al Ser: El proceso comienza con un PawnKindDef. Este Def actúa como una plantilla para un tipo de peón, como "colono", "saqueador tribal" o "comerciante de élite".17 El  
    PawnKindDef especifica:
    

- La race (raza), que es en sí misma un ThingDef que define las propiedades biológicas base (por ejemplo, Human, Muffalo).17
    
- El equipo con el que puede aparecer (apparelMoney, weaponMoney, weaponTags).
    
- Restricciones de trasfondo y rasgos (backstoryFilters, disallowedTraits).27
    
- Estadísticas de combate base (combatPower).
    

A partir de esta plantilla, el juego genera un peón individual, asignándole BackstoryDefs (trasfondos de niñez y adultez que afectan las habilidades y las incapacidades laborales), TraitDefs (rasgos como "Optimista" o "Píromano"), y niveles de habilidad aleatorios dentro de los rangos permitidos.17 Esta arquitectura modular permite una vasta diversidad de personajes a partir de un conjunto relativamente pequeño de plantillas.

  

### 4.2. La Mente y el Cuerpo del Peón

  

La simulación de cada peón se gestiona a través de dos sistemas interconectados: el sistema de salud y el sistema de estado mental.

- Sistema de Salud (HediffDef): El término "Hediff" es una abreviatura de "Health Difference" (Diferencia de Salud). Un HediffDef define cualquier condición que altere el estado de salud base de un peón.29 Esto incluye:
    

- Lesiones: Como Cut (corte) o Blunt (contusión). Estas a menudo están vinculadas a DamageDefs, que definen cómo se aplica el daño.17
    
- Enfermedades: Como la gripe o la peste.
    
- Partes del cuerpo artificiales: Desde una simple pata de palo hasta un ojo biónico.
    
- Efectos de drogas: Tanto los efectos positivos de un estimulante como los negativos de la abstinencia.30
    
- Condiciones permanentes: Como una cicatriz o asma.
    

La interacción entre DamageDefs, ToolCapacityDefs (que define qué tipo de daño puede hacer un arma, como "Picar" o "Apuñalar") y HediffDefs crea un sistema de combate y salud detallado y emergente.17

- Estado Mental (ThoughtDef): El estado de ánimo de un peón, un factor crucial en su comportamiento, es la suma de sus pensamientos actuales. Cada pensamiento es una instancia de un ThoughtDef.17 Un  
    ThoughtDef define:
    

- Un modificador de humor (por ejemplo, -3, +10).
    
- Su duración.
    
- Su límite de acumulación (stackLimit).
    
- Múltiples "etapas" (stages) que pueden cambiar el efecto según la intensidad (por ejemplo, el pensamiento "Hambre" tiene etapas para "ligeramente hambriento", "hambriento" y "muriendo de hambre").32
    

Pensamientos como "Comí sin mesa" (-3), "Mi rival murió" (+10) o "Dormí en el frío" (-4) se combinan para determinar si un peón está feliz, contento o al borde de una crisis nerviosa.

  

### 4.3. El Cerebro de la IA - El Bucle de Decisión del Peón (Crucial para la Integración de LLM)

  

Este es el sistema más relevante para el objetivo de integrar un LLM. La IA del peón no es una caja negra, sino una máquina de estados jerárquica, determinista y altamente modular. No es un sistema de "empuje" (push), donde se le dice a un peón qué hacer, sino un sistema de "extracción" (pull), donde cada peón evalúa activamente su entorno y sus necesidades para decidir su próxima acción.

La jerarquía de decisión es la siguiente:

1. ThinkTreeDef: Este es el nivel más alto de la lógica de la IA. Es un árbol XML de ThinkNodes que define las prioridades generales de un peón. Contiene ramas para situaciones urgentes (por ejemplo, MentalState, SelfDefense), seguidas de necesidades básicas y, finalmente, el trabajo. Un ThinkTreeDef podría decir: "Primero, si estás en una crisis nerviosa, sigue esa lógica. Si no, si estás en llamas, apágate. Si no, si te están atacando, defiéndete. Si no, busca un trabajo que hacer".17
    
2. WorkTypeDef y WorkGiverDef: El ThinkTree finalmente delega en el sistema de trabajo. El WorkTypeDef corresponde a las columnas en la pestaña "Trabajo" de la interfaz de usuario (por ejemplo, Hauling, Crafting). Cada WorkTypeDef contiene una lista de WorkGiverDefs.17 Un  
    WorkGiverDef es una definición XML para una tarea específica dentro de esa categoría de trabajo. Por ejemplo, el WorkTypeDef de Hauling (Transporte) contiene WorkGiverDefs para "transportar objetos generales", "llenar generadores de combustible", "rearmar torretas", etc..17
    
3. JobGiver y JobDef: Aquí es donde el XML se encuentra con el C#. Cada WorkGiverDef está asociado a una clase C# que hereda de JobGiver. En cada "tick" de la IA, el juego itera a través de la lista priorizada de WorkGivers relevantes para un peón. Llama al método TryGiveJob de cada JobGiver. Este método C# escanea el entorno en busca de una tarea válida que coincida con su propósito (por ejemplo, el JobGiver para "transportar objetos" busca objetos en el mapa que no estén en un almacén). Si encuentra una tarea, crea y devuelve un Job.17
    
4. Job: Un Job es una instancia de un JobDef y representa la acción final que el peón ejecutará. Es una secuencia de instrucciones concretas, como "ir a la coordenada X, recoger el objeto Y, llevarlo a la coordenada Z".
    

Este bucle determinista es la revelación clave. Un peón no "piensa" de forma abstracta; itera a través de una lista de clases JobGiver y ejecuta la primera que le devuelve una tarea válida. Para integrar un LLM, el enfoque arquitectónicamente correcto no es intentar controlar al peón directamente, sino crear un JobGiver C# personalizado. Este JobGiver se insertaría con alta prioridad en el ThinkTree a través de un parche XML. Su método TryGiveJob consultaría al LLM. Si el LLM devuelve una acción coherente, el JobGiver la traduciría en un Job estándar del juego, insertando así la decisión del LLM en el flujo de la IA nativa de manera limpia y compatible.

  

### 4.4. La IA Narradora - Generación de Narrativa y Eventos

  

El famoso "AI Storyteller" (Narrador de IA) de RimWorld no es una IA consciente que escribe una historia, sino un sofisticado mecanismo de ritmo y gestión de eventos.

- El Narrador como Mecanismo de Ritmo: El rol principal del narrador (Cassandra Classic, Phoebe Chillax, Randy Random) es controlar la frecuencia, el tipo y la magnitud de los eventos que ocurren en la colonia.37
    
- Puntos de Amenaza y Riqueza de la Colonia: La magnitud de los eventos hostiles (como las incursiones) se calcula en función de un sistema de "puntos de amenaza". Estos puntos se generan principalmente a partir de la "riqueza" de la colonia (el valor de mercado de todos los objetos, edificios y peones en el mapa) y, en menor medida, del tiempo transcurrido.38 Esto crea un bucle de retroalimentación donde una colonia más exitosa y rica atrae mayores peligros.
    
- IncidentDef y Colas de Disparo: Cada evento posible, desde una incursión pirata hasta la caída de una vaina de carga, se define en un IncidentDef. El narrador mantiene colas de eventos y decide cuándo "disparar" un IncidentDef basándose en su personalidad. Cassandra busca una tensión creciente con picos y valles predecibles, mientras que Randy introduce un alto grado de aleatoriedad, pudiendo encadenar múltiples desastres o largos períodos de calma.42
    

Comprender este sistema permite a los modders crear sus propios narradores con lógicas de ritmo únicas o añadir nuevos eventos (IncidentDefs) que se integren en el sistema de generación de historias existente.

  

## Sección 5: Técnica Avanzada - Descompilación y Análisis del Código Fuente

  

Para trascender los tutoriales y la documentación superficial, y para acceder a las "revelaciones profundas" que sustentan el conocimiento de la comunidad de modding de élite, es esencial adoptar una práctica fundamental: tratar el propio código del juego como la fuente de verdad definitiva. Esto se logra mediante la descompilación, el proceso de convertir los archivos de programa compilados del juego de nuevo en código fuente legible por humanos.

  

### 5.1. La Documentación Definitiva: Assembly-CSharp.dll

  

Toda la lógica del juego RimWorld, desde cómo un peón elige su próxima comida hasta cómo se calcula la precisión de un disparo, está contenida en un único archivo: Assembly-CSharp.dll.

- Localización del Ensamblado Central: Este archivo crucial se encuentra dentro de la carpeta de instalación de RimWorld, en una subcarpeta llamada RimWorld..._Data/Managed/. La ruta exacta varía ligeramente entre Windows, macOS y Linux, pero la estructura ..._Data/Managed/ es consistente.6 Este archivo es el objetivo principal de cualquier esfuerzo de descompilación.
    
- Por Qué Descompilar: Las wikis y los tutoriales son, en el mejor de los casos, interpretaciones de segunda mano del comportamiento del juego. Pueden estar desactualizados, ser incompletos o simplemente incorrectos. El código fuente descompilado, por otro lado, es una representación directa y 100% precisa de cómo funcionan las mecánicas del juego en este momento.7 La capacidad de leer este código transforma a un modder de un experimentador que trabaja a base de prueba y error a un ingeniero que puede predecir el comportamiento del sistema con certeza.
    

  

### 5.2. Guía Práctica para el Uso de ILSpy/dnSpy

  

Aunque ambas herramientas son capaces, dnSpy es a menudo preferido por sus características avanzadas de depuración. El proceso general de análisis es similar en ambas.

1. Cargar el Ensamblado: El primer paso es abrir el descompilador y cargar el archivo Assembly-CSharp.dll. La herramienta analizará el archivo y presentará una vista de árbol de todos los namespaces, clases, métodos y campos que contiene.
    
2. Navegación y Búsqueda: La funcionalidad más básica y potente es la búsqueda. Si se desea entender cómo funciona una mecánica, se puede buscar por palabras clave. Por ejemplo, para investigar la mecánica de "comer sin mesa", se podría buscar el texto "Ate without table". Esto probablemente llevaría al ThoughtDef correspondiente. A partir de ahí, se puede buscar el defName de ese ThoughtDef en el código para encontrar las clases C# que hacen referencia a él, revelando la lógica que desencadena ese pensamiento.
    
3. Análisis de Flujo de Código: Las herramientas de descompilación modernas ofrecen más que solo texto. Permiten un análisis de código sofisticado. Se puede hacer clic con el botón derecho en un método y seleccionar "Analizar" o "Buscar Usos" para ver todos los lugares en el código desde donde se llama a ese método. También se puede rastrear de dónde provienen los valores de las variables y a dónde van. Esta capacidad de seguir el flujo de la lógica a través de la base de código es indispensable para comprender sistemas complejos.49
    

  

#### Ejemplo de Análisis: Trazando JobGiver_GetFood.TryGiveJob

  

Para ilustrar el poder de este enfoque, se puede realizar un análisis práctico de un método central de la IA. Supongamos que se quiere entender exactamente cómo un peón decide qué comida comer.

1. Búsqueda Inicial: Se busca en el descompilador la clase JobGiver_GetFood.
    
2. Localizar el Método Clave: Dentro de esta clase, el método TryGiveJob es el punto de entrada lógico. Este es el método que el motor de la IA llama para ver si el peón debe generar un trabajo para comer.
    
3. Lectura del Código: Al leer el código descompilado de TryGiveJob, se observaría una secuencia de lógica clara:
    

- El código primero comprueba si el peón realmente necesita comida (si su nivel de hambre está por debajo de un cierto umbral).
    
- Luego, busca la mejor fuente de comida disponible. Esto implica una serie de comprobaciones: ¿Hay una comida preparada en un inventario cercano? ¿Hay un dispensador de pasta de nutrientes accesible? ¿Hay bayas cosechables en el mapa? ¿Hay un cadáver que pueda ser consumido (si la ideología o los rasgos del peón lo permiten)?
    
- La lógica de búsqueda de alimentos a menudo utiliza un validador que comprueba no solo la existencia de la comida, sino también si el peón puede llegar a ella (pathfinding) y si tiene permitido comerla (políticas de comida).
    
- Si se encuentra una fuente de comida válida, el método construye y devuelve un nuevo Job con las instrucciones para ir a la comida y consumirla.
    

Este tipo de análisis detallado, realizado directamente sobre el código fuente, proporciona un nivel de comprensión que ningún tutorial puede igualar. Permite responder preguntas mecánicas complejas con total certeza y es la habilidad fundamental que separa a los modders principiantes de los expertos capaces de crear sistemas profundos y estables.

  

## Sección 6: La Frontera - Integración de Modelos de Lenguaje Grandes con la IA de los Peones

  

Esta sección final sintetiza todo el conocimiento arquitectónico previo para abordar directamente el objetivo principal: la integración de Modelos de Lenguaje Grandes (LLM) para crear peones con comportamientos más complejos y realistas. Este es un campo emergente en el modding, no solo para RimWorld sino para los videojuegos en general, y presenta un conjunto único de desafíos y oportunidades.

  

### 6.1. Marcos Conceptuales para la Integración de LLM

  

La integración de un LLM en RimWorld puede adoptar múltiples formas, cada una con su propio punto de entrada en la arquitectura del juego.

- Diálogo Dinámico y Registros Sociales: El caso de uso más directo es la generación de conversaciones contextuales. En lugar de las interacciones predefinidas del juego ("Peón A habló con Peón B sobre X"), un LLM puede generar diálogos reales basados en los rasgos de los peones, su relación, su estado de ánimo actual y el entorno. Mods como RimDialogue y Local AI Social Interactions ya exploran este concepto, interceptando los eventos de interacción social y utilizando un LLM para generar el texto de las burbujas de diálogo.54
    
- Descripciones Generativas de Arte y Objetos: El juego genera descripciones aleatorias para las obras de arte. Un LLM puede tomar los mismos datos de entrada (el creador, la calidad, el tema) y producir descripciones mucho más ricas, detalladas y estilísticamente coherentes. El mod RimWorldAI Items es un ejemplo de esta aplicación, enriqueciendo la narrativa del juego a través de los objetos.58
    
- Narración de la Historia: Un LLM puede actuar como un cronista de la colonia. Al recibir información sobre eventos importantes (incursiones, muertes, nacimientos, matrimonios), puede escribir una narrativa en prosa del desarrollo de la colonia, como lo demuestra el mod RimSaga.59
    
- Influencia en el Comportamiento (El Objetivo Principal): Este es el caso de uso más complejo. El objetivo es utilizar un LLM no solo para generar texto, sino para influir en la toma de decisiones de un peón. En lugar de que un peón siempre elija la tarea lógicamente óptima de su lista de JobGivers, un LLM podría introducir un elemento de personalidad, irracionalidad o planificación a largo plazo, sugiriendo acciones que de otro modo no se tomarían.
    

  

### 6.2. Implementación Técnica y Desafíos

  

La implementación de un sistema de LLM en un juego en tiempo real como RimWorld presenta desafíos técnicos significativos que deben abordarse a nivel arquitectónico.

- Modelos Locales vs. API en la Nube: La primera decisión fundamental es dónde se ejecutará el LLM.
    

- Modelos Locales (por ejemplo, a través de Ollama): La ejecución de un LLM directamente en la máquina del jugador ofrece ventajas clave: es gratuita (después de la descarga inicial), completamente privada y no tiene latencia de red. Sin embargo, tiene un costo considerable en términos de recursos de hardware, requiriendo una cantidad significativa de RAM y, para los modelos más grandes, una potente GPU. Mods como RimWorldAI y versiones recientes de mods de conversación están adoptando este enfoque para la privacidad y la capacidad de respuesta.54
    
- APIs en la Nube (por ejemplo, Google Gemini, OpenAI): El uso de una API externa da acceso a los modelos más potentes del mercado sin impacto en el rendimiento del hardware local. La desventaja es triple: el costo (cada llamada a la API puede tener un precio), la latencia de la red (que puede ser problemática para decisiones en tiempo real) y las preocupaciones sobre la privacidad de los datos enviados al servidor.54
    

- El Desafío Asíncrono: El motor de RimWorld se ejecuta en un único hilo principal. Realizar una operación de red (como una llamada a una API en la nube) o una inferencia de LLM local pesada en este hilo principal congelaría el juego por completo hasta que se reciba una respuesta. La solución es la programación asíncrona. El código C# debe iniciar la solicitud al LLM en un hilo de fondo y utilizar las construcciones async y await para esperar la respuesta sin bloquear el hilo principal del juego. Esto es absolutamente crítico para mantener una experiencia de juego fluida.62
    
- Ingeniería de Prompts y Gestión del Contexto: La calidad de la salida de un LLM depende directamente de la calidad de su entrada (el "prompt"). Para que un LLM tome una decisión informada para un peón, el prompt debe incluir un contexto rico: los rasgos del peón, su estado de ánimo, sus necesidades, sus relaciones, los objetos cercanos, la hora del día, el clima, etc. El desafío consiste en construir un prompt que sea lo suficientemente detallado para generar una respuesta coherente, pero lo suficientemente conciso para no ser excesivamente lento de procesar o costoso de enviar a una API.54
    

  

### 6.3. Estudios de Caso: Mods de LLM Existentes

  

El panorama actual de mods de LLM para RimWorld ofrece valiosas lecciones sobre diferentes enfoques arquitectónicos.

Tabla 1: Análisis Comparativo de Mods de Integración de LLM en RimWorld

  

|   |   |   |   |
|---|---|---|---|
|Característica|RimWorldAI 58|EchoColony / Talk with Colonists 54|RimDialogue 56 / RimSaga 59|
|Función Principal|Framework de IA sin conexión|Conversación directa con el peón|Burbujas de diálogo generativas / Narración de historias|
|Punto de Integración|Descripciones de arte, Framework|Menú contextual del peón (clic derecho)|Registros de interacción social / Eventos del juego|
|Tipo de Modelo AI|Local (Phi-3)|Local (Ollama) o API en la nube (Gemini, OpenAI)|API en la nube (requiere internet)|
|Dependencias Clave|Paquete personalizado sin conexión|Harmony, potencialmente aplicaciones externas (Player2)|Harmony, Interaction Bubbles|
|Desafío Principal|Compatibilidad de hardware|Ingeniería de prompts, gestión de API|Latencia, costo de API, contexto del prompt|

Este análisis comparativo revela que no existe una única solución "correcta". La elección de la arquitectura depende del objetivo del mod. Para la generación de contenido no sensible al tiempo como descripciones de arte, un modelo local es ideal. Para diálogos interactivos, existe un compromiso entre la capacidad de respuesta de los modelos locales y la potencia de las APIs en la nube. Para el objetivo de influir en el comportamiento, la latencia es un factor crítico, lo que sugiere que un enfoque de modelo local o una API de muy baja latencia sería preferible. La lección más importante es que la integración exitosa de un LLM no busca reemplazar la IA central del juego, sino aumentarla en puntos de contacto bien definidos.

  

## Conclusión y Recomendaciones Estratégicas

  

La arquitectura de RimWorld es un testimonio del poder del diseño de software bien pensado. Su estricta separación de datos (XML) y lógica (C#), junto con un sistema de herencia de datos robusto y la capacidad de modificación en tiempo de ejecución a través de Harmony, crea una plataforma extraordinariamente flexible y resistente para el modding. Para el desarrollador aspirante con la ambición de crear simulaciones más profundas y realistas, dominar estos pilares arquitectónicos no es opcional, es el único camino hacia el éxito.

La investigación de los sistemas del juego revela varias verdades fundamentales:

1. El Modding es Ingeniería Inversa: La falta de documentación oficial exhaustiva ha llevado a la comunidad a adoptar la descompilación del código fuente del juego como la práctica estándar. La capacidad de leer y comprender Assembly-CSharp.dll es la habilidad que desbloquea el verdadero potencial de modding.
    
2. La Herencia y los Parches son la Norma: La arquitectura del juego está diseñada explícitamente para ser extendida a través de la herencia de Defs y modificada a través de parches XML no destructivos. Cualquier enfoque que implique la sobreescritura de archivos centrales está destinado al fracaso y a la incompatibilidad.
    
3. Harmony es el Habilitador Universal: La biblioteca Harmony es el pilar que sostiene todo el ecosistema de modding C#. Proporciona la API estandarizada y segura para inyectar nueva lógica en el motor del juego, permitiendo que coexistan mods complejos.
    
4. La IA del Peón es un Sistema Modular y Predecible: Lejos de ser una caja negra, el bucle de decisión del peón es una máquina de estados jerárquica y determinista (ThinkTree -> JobGiver -> Job). Esta modularidad ofrece puntos de entrada claros y definidos para que los mods influyan en el comportamiento sin romper la lógica central.
    

Para el proyecto específico de integrar Modelos de Lenguaje Grandes (LLM) para impulsar el comportamiento de los peones, estas conclusiones arquitectónicas conducen a una hoja de ruta estratégica clara y viable:

Hoja de Ruta Recomendada:

1. Fase 1: Dominio de la Capa de Datos (XML): Antes de escribir una sola línea de C#, es crucial lograr la fluidez en XML. Se recomienda comenzar creando mods simples que solo usen XML:
    

- Crear un nuevo objeto (por ejemplo, un arma o un mueble) heredando de un Def abstracto apropiado.
    
- Crear un parche XML para modificar un Def del juego base (por ejemplo, cambiar el costo de un objeto).
    
- Este paso solidificará la comprensión de la estructura de Defs, la herencia y el sistema de parches.
    

2. Fase 2: Introducción a la Capa de Lógica (C# y Harmony): El siguiente paso es interactuar con la lógica del juego.
    

- Configurar un entorno de desarrollo profesional con Visual Studio y las referencias correctas.
    
- Escribir un parche simple con Harmony. Un buen primer proyecto es un parche Postfix que escriba un mensaje en el registro de depuración cuando se ejecuta un método específico del juego (por ejemplo, cuando un peón come).
    
- Esto enseñará los fundamentos de la compilación de ensamblados y el mecanismo de parcheo de Harmony.
    

3. Fase 3: Prueba de Concepto de Integración de LLM: Con una base sólida en XML y C#, se puede comenzar a abordar el proyecto principal. El enfoque arquitectónicamente más sólido es el siguiente:
    

- Crear un JobGiver Personalizado: Escribir una nueva clase C# que herede de RimWorld.JobGiver_Think.
    
- Implementar la Lógica del LLM: Dentro del método TryGiveJob de esta nueva clase, implementar la lógica para:  
    a. Recopilar el contexto relevante del peón y del mundo.  
    b. Formatear este contexto en un prompt.  
    c. Realizar una llamada asíncrona a un LLM (comenzando con un modelo local como Ollama para simplificar las pruebas).  
    d. Analizar la respuesta del LLM.  
    e. Si la respuesta corresponde a una acción válida en el juego, construir y devolver un Job estándar del juego que corresponda a esa acción.
    
- Integrar a través de XML: Crear un ThinkTreeDef personalizado o parchear uno existente para insertar el nuevo JobGiver con una alta prioridad.
    

Este enfoque gradual y sistemático, basado en una comprensión profunda de la arquitectura subyacente de RimWorld, permitirá construir una base de conocimientos sólida. Al trabajar con la arquitectura del juego en lugar de en su contra, es posible crear mods complejos, estables y verdaderamente innovadores que empujen los límites de lo que RimWorld puede ser como generador de historias. La visión de peones impulsados por LLM no es solo una idea fascinante; es un objetivo de ingeniería alcanzable sobre la base de los principios aquí descritos.

#### Obras citadas

1. modding tutorial for absolute beginners? : r/RimWorld - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/RimWorld/comments/100g1wl/modding_tutorial_for_absolute_beginners/](https://www.reddit.com/r/RimWorld/comments/100g1wl/modding_tutorial_for_absolute_beginners/)
    
2. Basic Concepts - RimWorld Modding Wiki, fecha de acceso: septiembre 25, 2025, [https://rimworldmodding.wiki.gg/wiki/Basic_Concepts](https://rimworldmodding.wiki.gg/wiki/Basic_Concepts)
    
3. Zeta-of-the-rim/RimWorld-Mod-Tutorials: Tutorials for ... - GitHub, fecha de acceso: septiembre 25, 2025, [https://github.com/Zeta-of-the-rim/RimWorld-Mod-Tutorials](https://github.com/Zeta-of-the-rim/RimWorld-Mod-Tutorials)
    
4. Rimworld Modding Guide - Visual Studio Integration - YouTube, fecha de acceso: septiembre 25, 2025, [https://www.youtube.com/watch?v=dQf3P-hIlFM](https://www.youtube.com/watch?v=dQf3P-hIlFM)
    
5. How to Make a RimWorld Mod - Step by Step - YouTube, fecha de acceso: septiembre 25, 2025, [https://www.youtube.com/watch?v=UgCOhFzeX4A](https://www.youtube.com/watch?v=UgCOhFzeX4A)
    
6. How to Mod RimWorld STEP BY STEP by Jecrell - GitHub Gist, fecha de acceso: septiembre 25, 2025, [https://gist.github.com/jecrell/79299728f0a614875ff79995f6cc3c02](https://gist.github.com/jecrell/79299728f0a614875ff79995f6cc3c02)
    
7. About this wiki - RimWorld Modding Wiki, fecha de acceso: septiembre 25, 2025, [https://rimworldmodding.wiki.gg/wiki/About_this_wiki](https://rimworldmodding.wiki.gg/wiki/About_this_wiki)
    
8. RimWorld Modding Resources | A community-collated hub for all ..., fecha de acceso: septiembre 25, 2025, [https://spdskatr.github.io/RWModdingResources/](https://spdskatr.github.io/RWModdingResources/)
    
9. Melee Weapon Def - RimWorld Modding Wiki, fecha de acceso: septiembre 25, 2025, [https://rimworldmodding.wiki.gg/wiki/Melee_Weapon_Def](https://rimworldmodding.wiki.gg/wiki/Melee_Weapon_Def)
    
10. Modding Community - Discord? Other ways to get in touch? : r/RimWorld - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/RimWorld/comments/149f1kn/modding_community_discord_other_ways_to_get_in/](https://www.reddit.com/r/RimWorld/comments/149f1kn/modding_community_discord_other_ways_to_get_in/)
    
11. Rimworld Modding Discord? - Steam Community :: Discussions, fecha de acceso: septiembre 25, 2025, [https://steamcommunity.com/workshop/discussions/18446744073709551615/4848778446418514082/?appid=294100](https://steamcommunity.com/workshop/discussions/18446744073709551615/4848778446418514082/?appid=294100)
    
12. Is there a discord for modded Rimworld? - Steam Community, fecha de acceso: septiembre 25, 2025, [https://steamcommunity.com/app/294100/discussions/0/3422186614288499252/](https://steamcommunity.com/app/294100/discussions/0/3422186614288499252/)
    
13. r/rimworldmodding - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/rimworldmodding/](https://www.reddit.com/r/rimworldmodding/)
    
14. Ludeon Forums have been frozen : r/RimWorld - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/RimWorld/comments/1gd4uel/ludeon_forums_have_been_frozen/](https://www.reddit.com/r/RimWorld/comments/1gd4uel/ludeon_forums_have_been_frozen/)
    
15. What's going on in the Ludeon Forums? :: RimWorld General Discussions - Steam Community, fecha de acceso: septiembre 25, 2025, [https://steamcommunity.com/app/294100/discussions/0/4140564660386092747/](https://steamcommunity.com/app/294100/discussions/0/4140564660386092747/)
    
16. Which code is more important in RimWorld : XML or C# : r/RimWorld - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/RimWorld/comments/spfahy/which_code_is_more_important_in_rimworld_xml_or_c/](https://www.reddit.com/r/RimWorld/comments/spfahy/which_code_is_more_important_in_rimworld_xml_or_c/)
    
17. Def Types - RimWorld Modding Wiki, fecha de acceso: septiembre 25, 2025, [https://rimworldmodding.wiki.gg/wiki/Def_Types](https://rimworldmodding.wiki.gg/wiki/Def_Types)
    
18. Abstracts and inheritance | RimWorld Modding Resources - spdskatr, fecha de acceso: septiembre 25, 2025, [https://spdskatr.github.io/RWModdingResources/abstracts.html](https://spdskatr.github.io/RWModdingResources/abstracts.html)
    
19. XML Inheritance - RimWorld Modding Wiki, fecha de acceso: septiembre 25, 2025, [https://rimworldmodding.wiki.gg/wiki/XML_Inheritance](https://rimworldmodding.wiki.gg/wiki/XML_Inheritance)
    
20. Rimworld Modding Guide - Basic PatchOperations - YouTube, fecha de acceso: septiembre 25, 2025, [https://www.youtube.com/watch?v=O-xEieTmp3w](https://www.youtube.com/watch?v=O-xEieTmp3w)
    
21. [SOLVED] How do I xpath into a ThingDef with a parent name? :: RimWorld Discussioni generali - Steam Community, fecha de acceso: septiembre 25, 2025, [https://steamcommunity.com/app/294100/discussions/0/1643170269565401101/?l=italian](https://steamcommunity.com/app/294100/discussions/0/1643170269565401101/?l=italian)
    
22. [SOLVED] How do I xpath into a ThingDef with a parent name? :: RimWorld General Discussions - Steam Community, fecha de acceso: septiembre 25, 2025, [https://steamcommunity.com/app/294100/discussions/0/1643170269565401101/](https://steamcommunity.com/app/294100/discussions/0/1643170269565401101/)
    
23. My first functional C# project for Rimworld - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/RimWorld/comments/1giwko9/my_first_functional_c_project_for_rimworld/](https://www.reddit.com/r/RimWorld/comments/1giwko9/my_first_functional_c_project_for_rimworld/)
    
24. Introduction - Harmony, fecha de acceso: septiembre 25, 2025, [https://harmony.pardeike.net/articles/intro.html](https://harmony.pardeike.net/articles/intro.html)
    
25. Harmony - the full story : r/RimWorld - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/RimWorld/comments/fbnm45/harmony_the_full_story/](https://www.reddit.com/r/RimWorld/comments/fbnm45/harmony_the_full_story/)
    
26. Pawn activities : r/RimWorld - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/RimWorld/comments/1kmrnkl/pawn_activities/](https://www.reddit.com/r/RimWorld/comments/1kmrnkl/pawn_activities/)
    
27. Edit PawnKindDefs to Spawn With Specific Trait(s) :: RimWorld General Discussions, fecha de acceso: septiembre 25, 2025, [https://steamcommunity.com/app/294100/discussions/0/3114769644703375814/](https://steamcommunity.com/app/294100/discussions/0/3114769644703375814/)
    
28. Steam Workshop::Pawnkind Race Diversification (Continued), fecha de acceso: septiembre 25, 2025, [https://steamcommunity.com/sharedfiles/filedetails/?id=2828866565](https://steamcommunity.com/sharedfiles/filedetails/?id=2828866565)
    
29. ThoughtDefs or Hediffs? Or both?! : r/RimWorld - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/RimWorld/comments/qqb9cc/thoughtdefs_or_hediffs_or_both/](https://www.reddit.com/r/RimWorld/comments/qqb9cc/thoughtdefs_or_hediffs_or_both/)
    
30. Is it possible to make a conditional hediff? : r/rimworldmodding - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/rimworldmodding/comments/c22ua9/is_it_possible_to_make_a_conditional_hediff/](https://www.reddit.com/r/rimworldmodding/comments/c22ua9/is_it_possible_to_make_a_conditional_hediff/)
    
31. Need some help understanding melee damage types from the XML :: RimWorld General Discussions - Steam Community, fecha de acceso: septiembre 25, 2025, [https://steamcommunity.com/app/294100/discussions/0/3042732243097084212/](https://steamcommunity.com/app/294100/discussions/0/3042732243097084212/)
    
32. ABF: Synstructs Core - Workshop - Steam Community, fecha de acceso: septiembre 25, 2025, [https://steamcommunity.com/workshop/filedetails/?l=norwegian&id=3288463094](https://steamcommunity.com/workshop/filedetails/?l=norwegian&id=3288463094)
    
33. ABF: Synstructs Core - Steam Workshop, fecha de acceso: septiembre 25, 2025, [https://steamcommunity.com/workshop/filedetails/?id=3288463094](https://steamcommunity.com/workshop/filedetails/?id=3288463094)
    
34. XML editing help : r/RimWorld - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/RimWorld/comments/53gksl/xml_editing_help/](https://www.reddit.com/r/RimWorld/comments/53gksl/xml_editing_help/)
    
35. I made new Workgivers and it's working great. : r/RimWorld - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/RimWorld/comments/1gsol7i/i_made_new_workgivers_and_its_working_great/](https://www.reddit.com/r/RimWorld/comments/1gsol7i/i_made_new_workgivers_and_its_working_great/)
    
36. Error IN job Giver :: RimWorld General Discussions - Steam Community, fecha de acceso: septiembre 25, 2025, [https://steamcommunity.com/app/294100/discussions/0/3058492678366238755/](https://steamcommunity.com/app/294100/discussions/0/3058492678366238755/)
    
37. RimWorld - Wikipedia, fecha de acceso: septiembre 25, 2025, [https://en.wikipedia.org/wiki/RimWorld](https://en.wikipedia.org/wiki/RimWorld)
    
38. Difference between story tellers. :: RimWorld General Discussions - Steam Community, fecha de acceso: septiembre 25, 2025, [https://steamcommunity.com/app/294100/discussions/0/591762915933076109/](https://steamcommunity.com/app/294100/discussions/0/591762915933076109/)
    
39. Which Storyteller Should You Choose? - RimWorld Guide for Beginners [2024, 1.5+], fecha de acceso: septiembre 25, 2025, [https://www.youtube.com/watch?v=Q296JZzqcp8](https://www.youtube.com/watch?v=Q296JZzqcp8)
    
40. RimWorld Difficulty and Wealth Management - YouTube, fecha de acceso: septiembre 25, 2025, [https://www.youtube.com/watch?v=TaPYcA58fbE](https://www.youtube.com/watch?v=TaPYcA58fbE)
    
41. I made a graphic to explain the Storytellers' major threat schedules. : r/RimWorld - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/RimWorld/comments/v7mozp/i_made_a_graphic_to_explain_the_storytellers/](https://www.reddit.com/r/RimWorld/comments/v7mozp/i_made_a_graphic_to_explain_the_storytellers/)
    
42. Steam Workshop::[A17] Expanded Incidents, fecha de acceso: septiembre 25, 2025, [https://steamcommunity.com/sharedfiles/filedetails/?id=847634810](https://steamcommunity.com/sharedfiles/filedetails/?id=847634810)
    
43. Steam Workshop::Misc. Incidents, fecha de acceso: septiembre 25, 2025, [https://steamcommunity.com/sharedfiles/filedetails/?id=719702781](https://steamcommunity.com/sharedfiles/filedetails/?id=719702781)
    
44. A slightly more in-depth overview of the vanilla storyteller threat schedules : r/RimWorld, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/RimWorld/comments/v7za1f/a_slightly_more_indepth_overview_of_the_vanilla/](https://www.reddit.com/r/RimWorld/comments/v7za1f/a_slightly_more_indepth_overview_of_the_vanilla/)
    
45. Is there an easy way to change the properties/value of a resource ..., fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/RimWorld/comments/mrhhss/is_there_an_easy_way_to_change_the/](https://www.reddit.com/r/RimWorld/comments/mrhhss/is_there_an_easy_way_to_change_the/)
    
46. Where are the def files? : r/RimWorld - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/RimWorld/comments/4tfy0i/where_are_the_def_files/](https://www.reddit.com/r/RimWorld/comments/4tfy0i/where_are_the_def_files/)
    
47. What are the core files of rimworld? :: RimWorld General Discussions - Steam Community, fecha de acceso: septiembre 25, 2025, [https://steamcommunity.com/app/294100/discussions/0/3274690571061802434/](https://steamcommunity.com/app/294100/discussions/0/3274690571061802434/)
    
48. Storytellers source code? : r/RimWorld - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/RimWorld/comments/n7ukdm/storytellers_source_code/](https://www.reddit.com/r/RimWorld/comments/n7ukdm/storytellers_source_code/)
    
49. Dnspy help : r/dotnet - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/dotnet/comments/1ddkpxl/dnspy_help/](https://www.reddit.com/r/dotnet/comments/1ddkpxl/dnspy_help/)
    
50. Dnspy: how to recompile with broken code that doesnt actually affect anything? - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/csharp/comments/w31vy0/dnspy_how_to_recompile_with_broken_code_that/](https://www.reddit.com/r/csharp/comments/w31vy0/dnspy_how_to_recompile_with_broken_code_that/)
    
51. dnSpy/dnSpy: .NET debugger and assembly editor - GitHub, fecha de acceso: septiembre 25, 2025, [https://github.com/dnSpy/dnSpy](https://github.com/dnSpy/dnSpy)
    
52. ILSpy .NET Decompiler - YouTube, fecha de acceso: septiembre 25, 2025, [https://www.youtube.com/watch?v=u4bBadA6O-Y](https://www.youtube.com/watch?v=u4bBadA6O-Y)
    
53. RimWorld Optimized ILSpy - Decompile Them Iterators - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/RimWorld/comments/53ezsj/rimworld_optimized_ilspy_decompile_them_iterators/](https://www.reddit.com/r/RimWorld/comments/53ezsj/rimworld_optimized_ilspy_decompile_them_iterators/)
    
54. I made a mod to talk with your colonists! : r/RimWorld - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/RimWorld/comments/1jyjov5/i_made_a_mod_to_talk_with_your_colonists/](https://www.reddit.com/r/RimWorld/comments/1jyjov5/i_made_a_mod_to_talk_with_your_colonists/)
    
55. Local AI Social Interactions - Workshop - Steam Community, fecha de acceso: septiembre 25, 2025, [https://steamcommunity.com/sharedfiles/filedetails/?id=3413305419](https://steamcommunity.com/sharedfiles/filedetails/?id=3413305419)
    
56. RimDialogue needs beta testers. AI powered conversations in Rimworld. See comments for details. - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/RimWorld/comments/1gs0eqe/rimdialogue_needs_beta_testers_ai_powered/](https://www.reddit.com/r/RimWorld/comments/1gs0eqe/rimdialogue_needs_beta_testers_ai_powered/)
    
57. SpeakUp - Workshop - Steam Community, fecha de acceso: septiembre 25, 2025, [https://steamcommunity.com/sharedfiles/filedetails/?id=2502518544](https://steamcommunity.com/sharedfiles/filedetails/?id=2502518544)
    
58. Steam Workshop::RimWorldAI Items, fecha de acceso: septiembre 25, 2025, [https://steamcommunity.com/sharedfiles/filedetails/?id=3269938552](https://steamcommunity.com/sharedfiles/filedetails/?id=3269938552)
    
59. New mod RimSaga: Uses free AI to write the story of your colony like a novel while you play : r/RimWorld - Reddit, fecha de acceso: septiembre 25, 2025, [https://www.reddit.com/r/RimWorld/comments/1d5sw4f/new_mod_rimsaga_uses_free_ai_to_write_the_story/](https://www.reddit.com/r/RimWorld/comments/1d5sw4f/new_mod_rimsaga_uses_free_ai_to_write_the_story/)
    
60. Steam Workshop::RimWorldAI Core, fecha de acceso: septiembre 25, 2025, [https://steamcommunity.com/sharedfiles/filedetails/?id=3269938006](https://steamcommunity.com/sharedfiles/filedetails/?id=3269938006)
    
61. How to use ChatGPT in Unity - Simple Tutorial - YouTube, fecha de acceso: septiembre 25, 2025, [https://www.youtube.com/watch?v=gI9QSHpiMW0](https://www.youtube.com/watch?v=gI9QSHpiMW0)
    
62. Master UNITY with C# in 4 HOURS Game Physics, AI Integration, Full Projects - YouTube, fecha de acceso: septiembre 25, 2025, [https://www.youtube.com/watch?v=m9pIU9zB5ds](https://www.youtube.com/watch?v=m9pIU9zB5ds)
    
63. Integrate with external services - Unity Documentation, fecha de acceso: septiembre 25, 2025, [https://docs.unity.com/ugs/en-us/manual/cloud-code/manual/modules/how-to-guides/external-services-integration](https://docs.unity.com/ugs/en-us/manual/cloud-code/manual/modules/how-to-guides/external-services-integration)
    
64. Building an API Integration for Unity Using C# | by Jay Kim - Medium, fecha de acceso: septiembre 25, 2025, [https://medium.com/@bravekjh/building-an-api-integration-for-unity-using-c-7cd60bd8e914](https://medium.com/@bravekjh/building-an-api-integration-for-unity-using-c-7cd60bd8e914)
    

**