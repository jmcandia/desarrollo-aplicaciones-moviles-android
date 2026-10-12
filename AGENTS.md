# Instrucciones para construir los contenidos del libro

## 1. Propósito y alcance

Este documento instruye al agente de IA que redactará el libro online sobre Kotlin y desarrollo Android con MkDocs. Debe producir los archivos Markdown del índice maestro aprobado, no una propuesta alternativa de curso. Antes de escribir, debe verificar el árbol de archivos y el `nav` vigente; no debe asumir que los nombres indicados aquí ya existen.

## 1.1 Límite de alcance: escribir el libro, no construir ParkFlow

El agente **no debe desarrollar ni entregar la aplicación ParkFlow**. Su tarea es redactar contenidos educativos para el libro: explicaciones, diagramas, ejercicios, fragmentos de código, instrucciones de laboratorio y tutoriales escritos. ParkFlow es un caso ficticio/didáctico que da continuidad a esos materiales.

En particular, el agente no debe:

- implementar una app Android funcional de ParkFlow ni crear un producto listo para usar;
- crear un proyecto Android/Kotlin ejecutable como entregable, salvo que el responsable editorial lo solicite expresamente en otra instrucción;
- construir o desplegar backend, Firebase, base remota, reglas de producción, cuentas, servicios, infraestructura o almacenamiento;
- registrar aplicaciones o cuentas de proveedor, configurar credenciales reales, firmar/publicar una app ni cargar datos;
- tratar las acciones descritas en un tutorial como autorización para realizar dichas acciones en servicios externos.

Los tutoriales progresivos **explican** cómo un estudiante podría construir cada etapa de ParkFlow. Pueden incluir estructura de archivos ilustrativa, código de ejemplo y pasos reproducibles dentro del contenido del libro; esos materiales deben permanecer como documentación y ejemplos del libro. No se deben ejecutar para construir la aplicación ni desplegar servicios. Si la redacción requiere un ejemplo completo, mantenerlo acotado al capítulo/tutorial y señalar claramente sus prerrequisitos y carácter educativo.

El libro debe ser una obra de referencia rigurosa y autónoma, comparable en intención a una guía completa de Kotlin y Android. ParkFlow es el proyecto integrador que da continuidad a ejemplos y tutoriales. No es un filtro para decidir qué conceptos de Kotlin o Android se enseñan.

La estructura tiene tres unidades:

1. **Fundamentos autónomos de Kotlin.** Enseñar Kotlin como lenguaje, con programas de consola/dominio. No crear una app Android ni presentar elementos Android como prerrequisito.
2. **Desarrollo de aplicaciones Android.** Enseñar Android moderno con Kotlin, Compose y persistencia local.
3. **Integración, calidad y distribución.** Integrar servicios gestionados, seguridad, sincronización, pruebas y distribución sin construir un backend tradicional completo.

Redactar en español claro y consistente. Mantener términos técnicos en inglés cuando sean nombres oficiales de APIs, tipos, herramientas o patrones; definirlos la primera vez que aparezcan.

## 2. Instrucciones obligatorias para el agente

- Usar el índice maestro como contrato editorial. No cambiar el orden de unidades o capítulos ni eliminar capítulos porque no parezcan necesarios para ParkFlow.
- Limitar el trabajo a los contenidos del libro y los archivos de documentación que el responsable editorial haya pedido. No ampliar el encargo a implementar ParkFlow, aunque un tutorial describa código o pasos de implementación.
- Antes de desarrollar una página, revisar los archivos vecinos, el `mkdocs.yml`, las instrucciones del repositorio y las decisiones editoriales existentes. Respetar el formato y convenciones del proyecto.
- Trabajar en páginas pequeñas y enfocadas. No fusionar dos archivos del `nav` en una sola página ni reutilizar el mismo archivo para tutoriales distintos.
- Crear todo archivo referenciado por `nav`, con contenido sustantivo. No dejar enlaces rotos, páginas vacías, títulos de relleno ni secciones “por completar”.
- Conservar los tutoriales progresivos como páginas distintas; explicar prerrequisitos y enlazar las páginas conceptuales necesarias.
- No duplicar capítulos enteros en recorridos o tutoriales. Resumir lo indispensable, enlazar la explicación y aplicar el concepto al proyecto.
- No afirmar compatibilidad, comportamiento de API, requisito legal, formato de placa, precio, política de tienda o recomendación actual sin verificar una fuente primaria vigente.
- Para hechos variables, consultar documentación oficial al redactar. Preferir Kotlin, Android Developers, AndroidX, Gradle, Firebase, Google Play y fuentes oficiales chilenas. Citar la fuente junto a la afirmación y añadir las referencias completas al archivo de referencias.
- No tratar ejemplos de ParkFlow como fuentes de reglas legales. La validación local de patente solo valida formatos que la app documenta y admite; no prueba existencia, autenticidad, titularidad ni situación registral del vehículo.
- Evitar reglas de negocio ocultas en la UI. Expresar decisiones de dominio con tipos y funciones comprobables.
- No dejar credenciales, secretos, claves privadas, datos personales ni configuraciones de producción en ejemplos o repositorio.
- No ejecutar generación masiva que cambie nombres o rutas sin actualizar todos los enlaces y el `nav` de forma consistente.

## 3. Principios didácticos

### 3.1 Explicar antes de aplicar

Cada concepto debe entenderse por sí mismo antes de aparecer en ParkFlow. Introducir el problema, explicar el modelo mental, mostrar sintaxis mínima y casos límite, y después aplicarlo. El integrador sirve para hacer concretos los conceptos, no para reemplazar su explicación general.

### 3.2 Enseñanza rigurosa

Para cada concepto importante, explicar:

1. Qué problema resuelve y qué no resuelve.
2. Su modelo mental y vocabulario.
3. Sintaxis y ejemplo mínimo ejecutable o verificable.
4. Casos normales, límites y errores habituales.
5. Alternativas razonables y criterio de elección.
6. Pruebas, ejercicios progresivos y autoevaluación.
7. Referencias primarias para profundizar.

No convertir cada tema en una receta. Mostrar por qué la decisión funciona, cuándo falla y qué otras opciones existen.

### 3.3 Ejemplos

- Preferir ejemplos pequeños, coherentes y completos. Indicar archivo o ubicación del código cuando forme parte del proyecto.
- Asegurar que los nombres usados en ejemplos coincidan entre capítulos y tutoriales.
- No presentar pseudocódigo como Kotlin compilable. Etiquetar claramente pseudocódigo, diagramas y fragmentos incompletos.
- Cuando un fragmento dependa de contexto omitido, indicar qué se omite y por qué.
- Explicar el resultado esperado de código relevante.
- Usar montos en CLP con tipo decimal o unidades enteras apropiadas; no usar `Float`/`Double` para aritmética monetaria de producción sin explicar el riesgo.
- Usar fechas, horas y zona horaria explícitas al explicar cálculo de sesiones y franjas tarifarias.

### 3.4 Diagramas

Incluir diagramas cuando clarifiquen flujo, arquitectura, ciclo de vida, estado, navegación, sincronización o dependencias. Preferir Mermaid para diagramas pequeños compatibles con el sitio. Acompañar todo diagrama con explicación textual accesible; no codificar información solo con color.

## 4. Plantilla mínima de capítulo

Adaptar la plantilla al tema; no forzar secciones que no aporten. Todo capítulo conceptual debe contener:

1. Título igual al `nav`.
2. Objetivos de aprendizaje concretos.
3. Prerrequisitos y enlaces a páginas anteriores.
4. Explicación progresiva con conceptos y vocabulario definidos.
5. Ejemplos desarrollados y explicación de resultados.
6. Casos límite, errores comunes y criterios de decisión.
7. Aplicación a ParkFlow solo donde resulte pedagógicamente natural.
8. Ejercicios de dificultad progresiva y autoevaluación con respuestas comprobables o criterios de revisión.
9. Resumen breve de ideas clave.
10. Referencias citadas en contexto y enlaces a páginas relacionadas.

No crear soluciones orientativas como apéndice general. Pistas o criterios de respuesta pueden ir con el ejercicio cuando sean útiles, sin revelar de inmediato la solución si eso reduce el valor del ejercicio.

## 5. Plantilla mínima de tutorial progresivo

Cada tutorial debe indicar:

- Qué producto quedará construido al terminar y qué no forma parte de ese tramo.
- Conocimientos y tutoriales previos requeridos.
- Punto de partida verificable y estado final esperado.
- Pasos numerados en orden, cada uno con objetivo, decisión y resultado observable.
- Código exacto suficiente para seguir; no dejar saltos que impidan continuar.
- Errores previsibles y cómo diagnosticarlos.
- Una actividad breve de comprobación al acabar cada hito.
- Enlaces al capítulo donde se explica cada concepto.

Cuando el tutorial modifica archivos creados antes, indicar claramente qué se agrega, reemplaza o elimina. Mantener un estado acumulativo coherente del proyecto.

## 6. ParkFlow: contrato funcional y técnico

ParkFlow es una app Android offline-first para la gestión de estacionamientos en Chile.

### Capacidades del dominio

- Perfiles: administrador y operador.
- Gestión de vehículos y sesiones de estacionamiento.
- Configuración de tarifas según duración, tipo de vehículo y franjas horarias.
- Registro de vehículos con foto obligatoria de la matrícula.
- Validación documentada de formatos chilenos de patentes, con normalización explícita y casos admitidos/rechazados.
- Funcionamiento útil sin conexión y sincronización cuando vuelva la conectividad.

### Arquitectura didáctica

- Room es la fuente local de verdad de los datos operativos.
- DataStore guarda preferencias, no conjuntos relacionales de vehículos, sesiones o tarifas.
- Compose y Material 3 para UI.
- Navigation Compose para navegación.
- MVVM con ViewModel y estado observable mediante StateFlow.
- Coroutines y Flow para operaciones y datos asíncronos.
- Repositorios para abstraer fuentes de datos.
- Servicio gestionado/API para autenticación, acceso remoto y sincronización. Firebase es la opción recomendada para evaluar, no una decisión incondicional.
- Android Keystore cuando se requiera administrar claves criptográficas; no afirmar que cifra automáticamente la base de datos.
- Sin backend tradicional completo. Explicar límites del cliente y cuándo un proceso confiable gestionado o servicio adicional sería necesario.

### Reglas de consistencia

- El vehículo no se considera registrado hasta tener matrícula válida según la política documentada y una foto asociada.
- La app no debe depender de la red para mostrar o registrar operación local.
- Las operaciones pendientes deben sobrevivir reinicios y evitar duplicarse al reintentar.
- Definir política de conflictos por tipo de dato; no decir simplemente “sincroniza” sin explicar qué sucede ante escrituras concurrentes.
- La autoridad del rol se valida en el servicio, no solo ocultando botones en la UI.
- Nunca incluir credenciales privilegiadas o secretos de proveedor en la app.
- La tarifa aplicada a una sesión debe conservar la regla/valor relevante para que un cambio posterior de configuración no reescriba silenciosamente el historial.

## 7. Fuentes, vigencia y citas

### Jerarquía de fuentes

1. Documentación oficial de lenguaje, plataforma, librería o proveedor.
2. Normativa y sitios oficiales de Chile para reglas relacionadas con PPU/patentes.
3. Especificaciones técnicas o publicaciones originales de estándares.
4. Fuentes secundarias confiables solo para contexto, identificadas como tales.

No usar blogs, foros o Wikipedia como respaldo único de comportamiento actual, compatibilidad o normativa. Las fuentes secundarias pueden ayudar a localizar un asunto, pero hay que rastrear la fuente primaria.

### Formato de referencias

- Enlazar la fuente junto a la afirmación que respalda.
- Registrar en `referencias.md`: organismo/autor, título, URL, tema que respalda y fecha de consulta cuando el contenido pueda cambiar.
- Evitar una bibliografía de enlaces sin explicar para qué sirve cada fuente.
- Revisar que los enlaces respondan, sean directos y correspondan al contenido citado.
- Distinguir hechos documentados, decisión editorial, ejemplo didáctico e inferencia.

### Datos de Chile

- Consultar textos normativos vigentes en fuentes oficiales, incluida LeyChile/BCN y organismos públicos pertinentes.
- Documentar cada patrón reconocido de patente: categoría del vehículo, forma normalizada, caracteres permitidos/excluidos solo si la fuente lo confirma, separadores ignorados o conservados, y fecha/revisión de la regla.
- Cubrir formatos históricos que el sistema decida aceptar, sin declarar que uno es el único formato existente si no se verifica.
- Separar formato de matrícula, lectura óptica de una imagen y verificación registral: son problemas diferentes.
- La foto obligatoria del flujo es evidencia visual del registro; no equivale a OCR ni a autenticación oficial.
- Si no se encuentra fuente primaria suficiente para una regla, exponer la incertidumbre y no codificar la suposición como requisito legal.

## 8. Especificaciones de cada archivo del `nav`

Las rutas siguientes corresponden al `nav` aprobado. Cada instrucción define el foco único de esa página. Todos los archivos deben enlazar a conceptos previos y posteriores pertinentes.

### Inicio y orientación

#### `index.md` — Inicio

Presentar audiencia, propósito, alcance y las tres unidades. Explicar cómo ParkFlow recorre el libro sin limitar los fundamentos. Mostrar prerequisitos, ruta sugerida, tecnologías principales y cómo navegar. No duplicar el temario completo.

#### `como-usar-el-libro.md` — Cómo usar el libro

Explicar lectura lineal y consulta por tema, tipos de página, recorridos tutoriales, ejercicios, autoevaluación y convenciones de código. Definir los iconos/etiquetas si se usan. No inventar rutas de referencia independientes ya descartadas.

#### `convenciones-y-laboratorios.md` — Convenciones y laboratorios

Definir versiones técnicas actuales que se hayan verificado, formato de código, nombres, estructura de snippets, advertencias, capturas, comandos y prácticas de laboratorio. Distinguir ejemplos de Kotlin/JVM de código Android. No dejar configuraciones completas de entorno aquí si corresponden al capítulo inicial de Android.

### Unidad 1 — Fundamentos autónomos de Kotlin

Para todos los capítulos de esta unidad: usar Kotlin autónomo, ejemplos ejecutables de consola o pruebas JVM, y no exigir Android Studio, Compose, Activity, Context, Room ni otras APIs Android. ParkFlow puede servir de dominio de ejemplo, no como única motivación.

#### `unidad-1-kotlin/index.md` — Presentación

Explicar objetivos, secuencia, conocimientos previos y resultado de unidad. Aclarar autonomía respecto de Android. Incluir un mapa de dependencias entre tipos, funciones, objetos, colecciones, errores y concurrencia.

#### `01-kotlin-y-su-ecosistema.md`

Presentar Kotlin, compilación y entornos de ejecución pertinentes al curso, relación con JVM/Java, herramientas y primer programa. Distinguir lenguaje, biblioteca estándar, compilador e IDE. Evitar empezar con Android.

#### `02-sintaxis-y-expresiones.md`

Enseñar declaraciones, `val`/`var`, inferencia, literales, operadores, interpolación, bloques y expresiones. Mostrar alcance, mutabilidad y errores típicos con pequeños programas completos.

#### `03-tipos-y-null-safety.md`

Explicar sistema de tipos, nulabilidad, smart casts, llamadas seguras, Elvis, `!!`, tipos de plataforma e interoperabilidad. Incluir estados de ausencia y entradas inválidas; comparar soluciones seguras y frágiles.

#### `04-control-de-flujo.md`

Cubrir `if`, `when`, ciclos, rangos, progresiones y saltos. Mostrar exhaustividad, casos vacíos y límites de rangos. Comparar legibilidad de formas imperativas y expresiones.

#### `05-funciones.md`

Desarrollar parámetros, valores por defecto, argumentos nombrados, retorno, funciones locales, extensiones, lambdas, tipos funcionales, orden superior, inline y recursión. Explicar firmas y diseño testeable.

#### `06-clases-y-objetos.md`

Enseñar clases, constructores, propiedades, invariantes, `data class`, `object`, visibilidad y delegación perezosa. Distinguir igualdad por valor/referencia y límites de modelos mutables.

#### `07-interfaces-y-composicion.md`

Explicar interfaces, abstracción, herencia, despacho, `open`/`override`, composición y delegación. Incluir criterios concretos para elegir y ejemplos desacoplados de Android.

#### `08-enums-y-tipos-sellados.md`

Comparar `enum class`, `sealed class` y `sealed interface`; enseñar exhaustividad de `when`. Modelar categorías finitas con enums y alternativas que transportan datos/estados/resultados con tipos sellados. Mostrar límites y no presentar sealed como reemplazo universal.

#### `09-colecciones-y-secuencias.md`

Cubrir List/Set/Map, mutabilidad, igualdad, operaciones de transformación/agregación/agrupación y Sequence. Explicar pereza, consumo, coste intuitivo, orden, duplicados y colecciones vacías.

#### `10-genericos-y-variancia.md`

Enseñar parámetros de tipo, restricciones, `in`/`out`, proyecciones, borrado de tipos y reified. Usar ejemplos pequeños y explicar el problema de seguridad de tipos que resuelve la variancia.

#### `11-extensiones-y-delegacion.md`

Explicar extensiones, resolución estática, operadores, destructuración y delegados. Destacar los límites de extensión y las formas en que una API demasiado “mágica” pierde claridad.

#### `12-errores-y-recursos.md`

Distinguir excepciones, errores de dominio, validación y errores de programación. Enseñar `try`, `require`, `check`, `Result` o sellados con criterio, propagación y `use` para recursos.

#### `13-funcional-y-colecciones-inmutables.md`

Explicar pureza, efectos, inmutabilidad, composición y transformaciones. Contrastar código declarativo e imperativo; incluir dinero y redondeo como ejemplo de modelado correcto.

#### `14-concurrencia-kotlin.md`

Introducir concurrencia, coroutines, suspend, contextos, cancelación estructurada, excepciones y Flow a nivel de Kotlin/librería. Separar APIs del lenguaje, kotlinx.coroutines y APIs específicas de Android. Evitar afirmar que `suspend` crea automáticamente un hilo.

#### `15-lectura-y-diseno-de-programas.md`

Enseñar lectura de código, contratos, descomposición, diagnóstico de compilación, convenciones y revisión. Cerrar la unidad con un checklist independiente de Android.

#### `recorrido-modelar-dominio.md` — Recorrido conceptual

Desarrollar de forma acumulativa el modelo de dominio del estacionamiento: valores, tarifa, duración, vehículo, sesión, resultados y errores. Referenciar capítulos relevantes y justificar decisiones; no construir UI ni persistencia Android.

#### `tutorial-kotlin-parking.md` — Tutorial de dominio

Construir una biblioteca Kotlin/JVM pequeña para calcular tarifas y resumir sesiones. Incluir reglas por duración/tipo/franja como entrada explícita, modelo monetario, colecciones, pruebas y límites. Resultado comprobable en consola; sin app Android ni servidor.

#### `unidad-1-kotlin/evaluacion.md`

Evaluar comprensión y transferencia de Kotlin con interpretación de código, corrección de errores, diseño de tipos y ejercicios acumulativos. Las consignas deben poder resolverse sin Android. Proveer criterios de evaluación y retroalimentación.

### Unidad 2 — Desarrollo de aplicaciones Android

#### `unidad-2-android/index.md` — Presentación

Declarar dependencia conceptual de Kotlin, objetivos Android, mapa de capas, resultados ParkFlow y orden recomendado. Explicar que capítulo 1 contiene preparación del entorno, Gradle y compatibilidad de herramientas.

#### `01-plataforma-y-proyecto-android.md`

Incluir plataforma/API levels, Android Studio, SDK, emulador/dispositivo, instalación/configuración del entorno, estructura de proyecto, Gradle y catálogo de versiones, compatibilidad verificada y primer proyecto. Mantener versiones comprobadas y fecha. No remitir estos contenidos a apéndices.

#### `02-actividad-ciclo-de-vida-y-recursos.md`

Explicar Activity, proceso y ciclo de vida, recreación, recursos, Manifest, permisos y persistencia del estado. Separar estado transitorio de datos duraderos y evitar recetas que dependan de callbacks obsoletos.

#### `03-compose-y-estado.md`

Explicar composición, recomposición, estado, flujo unidireccional, eventos, listas, efectos y elevación de estado. Dar ejemplos claros y advertir de trabajo lateral o mutación no observable.

#### `04-material-3-y-diseno-adaptable.md`

Enseñar tema, componentes Material 3, layout adaptable, accesibilidad, contraste, estados de pantalla y localización de UI. Explicar criterios de diseño, no solo listas de componentes.

#### `05-entradas-formularios-y-validacion.md`

Separar estado de edición, validación y modelo. Diseñar validación y mensajes para la patente chilena con fuente oficial y una política de formatos explícita. Normalizar sin destruir el valor presentado. Incluir casos admitidos/rechazados y pruebas puras. Aclarar límites: no es verificación registral.

#### `06-navegacion-compose.md`

Enseñar destinos, argumentos, back stack, callbacks, estado y pruebas. Evitar pasar `NavController` dentro de toda pantalla si callbacks bastan. Aplicar navegación a perfiles sin confundir presentación con autorización.

#### `07-arquitectura-android-y-mvvm.md`

Explicar UI/dominio/datos, MVVM, repositorios, flujo unidireccional, dependencias e inyección manual inicial. Justificar límites de capas y enseñar a no trasladar toda lógica al ViewModel.

#### `08-viewmodel-stateflow-y-estado-ui.md`

Construir estado inmutable de pantalla, acciones, StateFlow, ciclo de vida y SavedStateHandle. Distinguir estado durable, recuperable y efímero; incluir pruebas.

#### `09-coroutines-y-flow-en-android.md`

Aplicar coroutines/Flow a ViewModel, repositorio y DAO; explicar scope, cancelación, dispatchers, errores y conversión de flujo a UI. Respetar ciclo de vida y no bloquear el hilo principal.

#### `10-room-y-modelo-local.md`

Enseñar entidad, relaciones, DAO, consultas Flow/suspend, transacciones, migraciones, conversores y pruebas. Diseñar Room como fuente local de verdad para vehículos, fotos referenciadas, tarifas y sesiones.

#### `11-foto-permisos-y-ciclo-de-vida.md`

Implementar selección/captura, permisos apropiados, URI, persistencia de acceso, previsualización, reemplazo, compresión y política de archivo. Imponer foto obligatoria antes de confirmar registro. Tratar privacidad y fallos.

#### `12-preferencias-con-datastore.md`

Comparar DataStore Preferences/Proto con Room. Implementar preferencias vía repositorio/Flow/ViewModel. Limitar su uso a configuración; cubrir errores y pruebas.

#### `13-errores-accesibilidad-y-localizacion.md`

Aplicar estados de carga/error/vacío, cadenas localizadas, formatos CLP/fecha/hora, zonas horarias, semántica y accesibilidad. No codificar formatos locales como universales.

#### `recorrido-primera-app.md` — Recorrido conceptual

Seguir desde creación del proyecto hasta la primera pantalla: Activity, Compose, recursos, tema, estado y ejecución. Enlazar el setup del capítulo 1 y no duplicar explicación Android entera.

#### `tutorial-primera-pantalla-parkflow.md`

Crear proyecto Compose, tema, navegación mínima e inicio con datos de demostración, estados vacío/carga/error. Entregar app ejecutable con primera pantalla; aún no gestionar flujos completos ni persistencia.

#### `recorrido-estructura-y-navegacion.md` — Recorrido conceptual

Explicar destinos, estructura de pantallas, callbacks, argumentos identificadores, back stack y perfiles visibles. Referenciar capítulos 6–8.

#### `tutorial-formularios-componentes-parkflow.md`

Crear componentes de entrada y formularios de vehículo/tarifa; implementar validación de matrícula, selección/previsualización obligatoria de foto y estados de error. Mantener datos temporales si Room aún no se introdujo. Resultado: formularios probables y accesibles listos para integrar.

#### `tutorial-parkflow-room-offline.md`

Integrar modelo, Room, DAOs, repositorios, Flow, ViewModels, pantallas, registro con foto requerida, tarifas y sesiones. Agregar DataStore solo para preferencias. Demostrar uso sin red/reinicio y pruebas básicas. Resultado de unidad: ParkFlow operativa localmente; todavía no requiere Firebase.

#### `unidad-2-android/evaluacion.md`

Evaluar UI, estado, navegación, MVVM, formularios, Room, DataStore, foto y accesibilidad. Requerir explicar decisiones y reproducir un escenario sin red.

### Unidad 3 — Integración, calidad y distribución

#### `unidad-3-integracion-y-distribucion/index.md` — Presentación

Presentar integración gestionada, seguridad, sincronización, calidad y publicación. Explicar que Firebase es candidato recomendado para validar y que la meta no es un backend tradicional completo.

#### `01-arquitecturas-clientes-y-servicios-gestionados.md`

Comparar cliente, API, backend y servicio gestionado; responsabilidades, riesgos, costos, cuotas y dependencia del proveedor. Explicar qué no debe confiarse al cliente y criterios para agregar función confiable/servidor.

#### `02-evaluar-firebase-para-parkflow.md`

Evaluar Auth, Firestore, Storage, reglas y App Check con fuentes actuales. Comparar Firestore/Realtime Database/API alternativa frente a requisitos, consultas, fotos, offline, conflictos, costos y salida. Terminar con decisión condicionada y criterios para aceptar/rechazar.

#### `03-modelo-de-datos-remoto-y-contratos.md`

Diseñar modelos remotos, DTOs y mapeos sin acoplar dominio a Firestore. Explicar claves, organización/estacionamiento, índices, versiones, timestamps, consistencia y minimización.

#### `04-autenticacion-y-sesion.md`

Describir alta/acceso/salida, identidad, recuperación, expiración y sesión. Modelar estados de UI, reautenticación y uso offline. No almacenar tokens manualmente sin necesidad ni exponer secretos.

#### `05-autorizacion-roles-y-reglas.md`

Separar autenticación/autorización; definir permisos admin/operador, aislamiento de datos y reglas del proveedor. Explicar asignación confiable de roles, validación server-side y pruebas de permitido/denegado. Advertir que ocultar UI no asegura datos.

#### `06-sincronizacion-offline-first.md`

Diseñar Room, outbox, estados de operación, coordinación de conectividad y sincronización reanudable. Explicar persistencia y estado visible. No delegar el modelo de verdad a dos cachés opacas.

#### `07-idempotencia-conflictos-y-reintentos.md`

Definir ID de operación, deduplicación, idempotencia, versiones, conflictos y reintentos con backoff. Determinar política para vehículos, fotos, tarifas y sesiones. Tratar transacciones remotas offline con precisión según proveedor vigente.

#### `08-fotografias-y-almacenamiento-remoto.md`

Diseñar flujo local→pendiente→subida→confirmada/error; reintentos idempotentes, permisos de lectura, tamaño, compresión, retención y eliminación. Garantizar coherencia entre registro y foto obligatoria.

#### `09-seguridad-y-keystore.md`

Clasificar datos, amenazas, claves, Keystore, secretos, tokens, archivos y privacidad. Decir qué protege cada mecanismo y qué queda fuera. No presentar Keystore como cifrado automático de Room ni solución de autorización remota.

#### `10-pruebas-unitarias-e-integracion.md`

Diseñar estrategia de pruebas para dominio, ViewModel, Room, sincronizador, repositorios y reglas. Fijar compatibilidad validada: JUnit 5/Kotest donde corresponda a local JVM; AndroidX Test/runner compatible para instrumentadas. MockK con criterio, fakes cuando sean mejores. Incluir matriz de versiones y no prometer soporte universal de JUnit 5 en Android instrumentado.

#### `11-pruebas-compose-y-navegacion.md`

Probar semántica, interacción, estado, errores, formularios y NavHost. Preferir acciones de UI y callbacks desacoplados. Explicar límites de emulador y evitar pruebas frágiles por texto/tiempos.

#### `12-calidad-observabilidad-y-mantenimiento.md`

Cubrir formato/análisis, logs sin datos personales, fallos, métricas de sync, rendimiento, batería, migraciones y mantenimiento. Separar instrumentación útil de captura excesiva de datos.

#### `13-firma-versiones-y-distribucion.md`

Explicar build debug/release, claves, upload key, App Bundle, versionado, configuración segura, pruebas previas y distribución. Verificar requisitos actuales de Play y firma; no publicar ni crear credenciales reales.

#### `tutorial-parkflow-sincronizado.md`

Extender el ParkFlow local: preparar Firebase de desarrollo, Auth, roles/reglas, modelos remotos, outbox Room, sincronizador idempotente y fotos en Storage. Incluir prueba de modo avión, reinicio, duplicados, conflictos, token vencido y restauración de red. Resultado: sistema integrado con límites explícitos, no backend completo.

#### `evaluacion-final.md`

Proponer evaluación integral con criterios verificables: arquitectura, operación offline, validación documentada, foto obligatoria, autorización remota, idempotencia, conflictos, pruebas, seguridad y build firmado de prueba. Exigir justificar los límites del sistema.

### Apéndices

Los apéndices complementan el curso; no reemplazan los capítulos ni deben introducir prerrequisitos ocultos. Usar ejemplos Kotlin/Android solo después de explicar el concepto general.

#### `apendices/pilares-poo.md`

Explicar encapsulación, abstracción, herencia y polimorfismo: origen, sentido práctico, malentendidos y límites. Mostrar Kotlin compacto y una aplicación pertinente. Contrastar composición y modelado moderno sin forzar herencia.

#### `apendices/solid.md`

Explicar SRP, OCP, LSP, ISP y DIP uno por uno: intención, ejemplo pequeño, síntoma de violación, refactor y coste de aplicar mecánicamente. No declarar SOLID como leyes universales ni imponer capas por dogma.

#### `apendices/kiss-y-dry.md`

Explicar KISS y DRY con ejemplos de duplicación real y abstracción prematura. Diferenciar repetición accidental de duplicación intencional útil. Mostrar refactor en Kotlin y advertir que “no repetirse” no justifica una abstracción confusa.

### Referencias

#### `referencias.md`

Colocar al final del `nav`. Organizar referencias por Kotlin, Android/Compose, arquitectura/almacenamiento, Firebase/servicios, pruebas, seguridad, distribución y normativa/fuentes chilenas. Incluir título, entidad, enlace directo, asunto que profundiza y fecha de consulta para fuentes cambiantes. Mantener las citas contextuales dentro de los capítulos; esta página amplía, no sustituye esas citas.

## 9. MkDocs, navegación y enlaces

- Mantener los títulos de entradas del `nav` entre comillas dobles, como en el `nav` acordado.
- El `nav` es el orden canónico de lectura; no insertar páginas no aprobadas sin actualizarlo.
- Usar rutas Markdown relativas coherentes con la ubicación de cada archivo.
- Todos los enlaces internos deben resolverse. No enlazar a rutas propuestas que no existan todavía.
- Conservar un título H1 por página y mantenerlo igual o claramente equivalente al título del `nav`.
- Usar encabezados jerárquicos sin saltos arbitrarios; evitar saltar de H1 a H4.
- Los bloques de código deben indicar lenguaje. Mantener líneas razonables y explicar bloques no obvios.
- No usar tablas anchas para texto explicativo extenso; preferir encabezados y listas. Las tablas son para comparaciones compactas.
- No depender de extensiones MkDocs no configuradas. Revisar `mkdocs.yml` antes de usar admonitions, tabs, superfences u otra sintaxis específica.
- Añadir atributos alt útiles a imágenes. Toda figura debe tener propósito, texto alternativo y fuente/licencia cuando corresponda.

## 10. Secuencia sugerida de producción

1. Auditar `mkdocs.yml`, rutas, instrucciones del proyecto y páginas existentes.
2. Confirmar el `nav` aprobado y crear una lista de archivos faltantes.
3. Redactar páginas de orientación y glosario de términos recurrentes.
4. Escribir la Unidad 1, validar ejemplos y prerequisitos, y cerrar su tutorial.
5. Escribir la Unidad 2 en orden, manteniendo tutoriales incrementales y estado acumulado del proyecto.
6. Investigar fuentes vigentes antes de redactar matrícula, compatibilidad, Firebase, pruebas, seguridad y distribución.
7. Escribir la Unidad 3 y probar mentalmente/reproducir los escenarios offline y de conflicto descritos.
8. Escribir apéndices como materiales breves de profundización y referencias al final.
9. Revisar coherencia de nombres, modelos, reglas de tarifas, perfiles, fotos y estados a lo largo del libro.
10. Revisar todos los enlaces, código, citas y páginas del `nav`; informar limitaciones en vez de inventar una confirmación.

## 11. Criterios de aceptación del libro

El trabajo está listo para revisión cuando:

- Todas las entradas del `nav` tienen un archivo con contenido real.
- La Unidad 1 se entiende y practica sin Android.
- Cada tutorial declara prerrequisitos y tiene resultados observables.
- ParkFlow evoluciona de forma incremental y consistente entre tutoriales.
- Las decisiones de Room, DataStore, Compose, MVVM, Flow, autenticación, roles y sincronización concuerdan entre capítulos.
- Registro de vehículo exige foto y valida matrícula conforme a reglas documentadas.
- La operación local funciona conceptualmente sin conexión y la sincronización trata duplicados, reinicios, conflictos y errores.
- Firebase se presenta como opción evaluada, con límites actuales documentados y alternativa razonable.
- La estrategia de pruebas refleja la compatibilidad real del ecosistema Android al momento de redactar.
- Referencias y afirmaciones técnicas/normativas se pueden rastrear a fuentes primarias.
- No hay archivos duplicados usados para páginas distintas, enlaces rotos, código engañosamente presentado como ejecutable o secciones vacías.
- Los apéndices contienen únicamente POO, SOLID, KISS y DRY salvo que el responsable editorial apruebe nuevas entradas.
- `referencias.md` es la última entrada principal del `nav`.
