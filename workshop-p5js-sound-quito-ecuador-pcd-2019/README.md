# workshop-p5js-sound-quito-ecuador-pcd-2019

Workshop "Introducción a la programación creativa sonora web con p5.js" para el Processing Community Day en Quito, Ecuador.

El workshop "Introducción a la programación creativa sonora web con p5.js" fue realizado en la Universidad San Francisco de Quito, con motivo del [Processing Community Day 2019](https://day.processing.org/), Quito, Ecuador, febrero 08 2019.

Este workshop consistirá en una introducción a la programación web, con especial énfasis en fundamentos JavaScript y la biblioteca p5.js.sound, con aplicaciones sonoras. Aprenderemos sobre arquitecturas de sintetizadores y sistemas sonoros interactivos y reactivos a webcam, teclado y ratón. Este workshop no requiere conocimientos previos de programación, está diseñado para gente sin conocimientos previos sobre programación o arte sonoro. Si sabes de alguno de estos temas, podrás aprender rápidamente los fundamentos de p5.js y usar funciones más avanzadas.

## Acerca de

El workshop "Introducción a la programación creativa sonora web con p5.js" fue diseñado y es impartido por [Aarón Montoya-Moraga](http://montoyamoraga.io/). Este workshop incluye trabajo y material que ya ha sido usado por el autor para actividades similares.

Esta versión fue enseñada enla Universidad San Francisco de Quito, Quito, Ecuador, viernes febrero 08 2019, en el contexto de una invitación realizada por [Gabriel Andrade](http://www.gandradep.com/) y con el generoso apoyo de la [Processing Foundation](https://processingfoundation.org/).

## Código de conducta

Nos regiremos por el [código de conducta de Berlin](http://berlincodeofconduct.org/es/), y por las siguientes reglas:

 * Este es un espacio seguro para experimentación sonora y artística.
 * Respeta a todos y sé amable.
 * No cometas actos ofensivos o violentos.
 * Haz preguntas, ándate por las ramas, improvisa.

## Sobre el autor

[Aarón Montoya-Moraga](http://montoyamoraga.io/) es ingeniero eléctrico, músico, programador y artista chileno. Se graduó y fue residente de investigación en el Programa de [Telecomunicaciones Interactivas](https://tisch.nyu.edu/itp) de la [Universidad de Nueva York](https://www.nyu.edu/). Enseña introducción a la programación y FLOSS para las artes en [CODED Escuela](http://codedescuela.cl/), que incluye [Pure Data](http://puredata.info/) y [ChucK](http://chuck.cs.princeton.edu/) para arte sonoro, [Python](https://www.python.org/) para poesía, [p5.js](https://p5js.org/es/) y [Processing](https://processing.org/) para artes visuales. Es colaborador del proyecto [p5.js](https://p5js.org/es/) y ha traducido a español el libro [Introducción a p5.js](https://processingfoundation.press/es/) para Processing Foundation. Dirige el sello de música [bandurria](https://bandurria.io/).

### Los estudiantes se presentan (90 segundos cada uno)

Por favor incluye esta información:

* Nombre?
* Por qué viniste a este curso?
* Experiencia programar?
* Experiencia arte visual / diseño gráfico?

[Timer de 90 segundos](https://www.google.com/search?rlz=1C5CHFA_enUS813US813&q=timer+90+seconds)

## Temario

* [Software a usar](#software-a-usar)
* [Historia de p5.js y Processing](#historia-de-p5js-y-processing)
* [Programación creativa para artes visuales y sonoras](#programaci%C3%B3n-creativa-para-artes-visuales-y-sonoras)
* [Mi comunidad](#mi-comunidad)
* [Programación en p5.js](#programaci%C3%B3n-en-p5js)
* [Referencia](#referencia)

## Software a usar

Para este workshop usaremos el [Editor Web de p5.js](https://editor.p5js.org/), por favor regístrense haciendo click en "Sign Up" en la esquina superior derecha.

Como alternativa al editor de p5.js, puedes descargar e instalar los siguientes software:

* Editor de texto: [Atom](https://atom.io/), [Sublime Text](https://www.sublimetext.com/)
* [Processing](https://processing.org/)

## Historia de p5.js y Processing

(20 minutos)

[Processing](https://processing.org/) es un [software libre, gratuito, y de código abierto](https://es.wikipedia.org/wiki/Software_libre_y_de_c%C3%B3digo_abierto) (FLOSS por sus siglas en inglés).

Processing fue creado por [Ben Fry](https://en.wikipedia.org/wiki/Ben_Fry) y [Casey Reas](https://en.wikipedia.org/wiki/Casey_Reas), para más información leer [A modern Prometheus - The History of Processing by Casey Reas and Ben Fry ](https://medium.com/processing-foundation/a-modern-prometheus-59aed94abe85).

Processing es desarrollado principalmente por la comunidad en torno a [UCLA DMA](http://dma.ucla.edu/), [Fathom Information Design](https://fathom.info/) y [NYU ITP](https://tisch.nyu.edu/itp).

La [Processing Foundation](https://processingfoundation.org/) es una fundación sin fines de lucro que promueve la comunidad en torno al uso y desarrollo de software para programación creativa en las artes.

## Programación creativa para artes visuales y sonoras

(30 mins)

* [Cinder](https://libcinder.org/), biblioteca gratuita y de código abierto para programación creativa de calidad profesional, desarrollada en C++.

* [Chuck](http://chuck.cs.princeton.edu/), entorno de programación sonora desarrollado por [Ge Wang](https://www.gewang.com/).

* [Processing](https://processing.org/): Existen proyectos relacionados como [p5.js](https://p5js.org/es/), [Processing for Android](https://android.processing.org/), [Processing for Pi](https://pi.processing.org/) y [Processing.py](https://py.processing.org/).

* [p5.js](https://p5js.org/es/), biblioteca de JavaScript creada por [Lauren McCarthy](http://lauren-mccarthy.com/)

* [openFrameWorks](https://openframeworks.cc/), biblioteca de C++ de código abierto para programación creativa.

* [Max](https://cycling74.com/), entorno de programación visual para artes sonoras, inventado por [Miller Puckette](http://msp.ucsd.edu/), desarrollado por [Cycling '74](https://cycling74.com/), integración con [Ableton Live](https://www.ableton.com/en/) y [Node.js](https://nodejs.org/en/).

* [Pure Data](http://puredata.info/), entorno de programación visual desarrollado por [Miller Puckette](http://msp.ucsd.edu/).

* [Tone.js](https://tonejs.github.io/), biblioteca de JavaScript para programación de arte sonoro, desarrollada por [Yotam Mann](https://yotammann.info/).

* [TidalCycles](http://pages.tidalcycles.org/), entorno de programación orientado a livecoding, desarrollado por [Alex McLean](https://en.wikipedia.org/wiki/Alex_McLean). Está escrito en Haskell y funciona en conjunto con [SuperCollider](https://supercollider.github.io/).

* [SuperCollider](https://supercollider.github.io/), entorno de programación sonora desarrollado originalmente por James McCartney.

## Mi comunidad

* [Afrotectopia](https://www.afrotectopia.com/), festival de artes mediales, cultura y tecnología organizado por [Ari Melenciano](http://ariciano.com/).

* [CODED Escuela](http://codedescuela.cl/), colectivo chileno de educación de artes mediales, conformada por [Aarón Montoya-Moraga](http://montoyamoraga.io/), [Camila Colussi](https://www.camilacolussi.com/), [Christian Oyarzún](http://error404.cl/), [Guillermo Montecinos]() y [Natalia Cabrera](http://www.nataliacabrera.com/). Enseñan introducción a la programación para arte gráfico con p5.js, arte sonoro con ChucK, poesía con Python, entre otros.

* [The Coding Train](https://www.youtube.com/user/shiffman): canal de Youtube dedicado a la enseñanza de programación creativa, por [Daniel Shiffman](https://shiffman.net/).

* [Kadenze](https://www.kadenze.com/): cursos en línea, incluye [Introduction to Programming for the Visual Arts with p5.js](https://www.kadenze.com/courses/introduction-to-programming-for-the-visual-arts-with-p5-js-vi/info), por [Casey Reas](http://reas.com/) y [Lauren McCarthy](http://lauren-mccarthy.com/), y también [The Nature of Code](https://www.kadenze.com/courses/the-nature-of-code-ii/info), por [Daniel Shiffman](https://shiffman.net/).

* [New Latin Wave](https://newlatinwave.com/), festival de arte y cultura latinoamericana en New York, dirigido por Amanda Riesman y [Mauricio Diaz](http://sokio.me/).

* [NYU ITP](https://tisch.nyu.edu/itp), programa posgrado MPS, New York, New York, Estados Unidos. Aquí son profesores [Daniel Shiffman](https://shiffman.net/), [Allison Parrish](https://www.decontextualize.com/) entre otros. También existe un programa de pregrado asociado en China [NYU Shanghai IMA](https://shanghai.nyu.edu/academics/majors/interactive-media-arts) y en New York [NYU IMA](https://tisch.nyu.edu/itp).

* [NYU ITP](https://tisch.nyu.edu/itp), programa posgrado MPS, New York, New York, Estados Unidos. Aquí son profesores [Daniel Shiffman](https://shiffman.net/), [Allison Parrish](https://www.decontextualize.com/) entre otros.

* [School for Poetic Computation](http://sfpc.io/), New York, New York, Estados Unidos. Aquí son profesores [Taeyoon Choi](http://taeyoonchoi.com/) y [Zach Lieberman](http://thesystemis.com/), entre otros.

* [School of Machines, Making & Make-Believe](http://schoolofma.org/), Berlin, Alemania, dirigida por [Rachel Uwa](http://schoolofma.org/about/).

* [Sinestesia](http://sinestesia.cc/), laboratorio creativo y espacio de encuentro en torno a artes mediales en Santiago de Chile, cuyos miembros incluyen a [Sergio Mora-Diaz](http://www.sergiomoradiaz.com/) y [Joaquín González](http://www.sinestesia.cc/sinestesia-lie).

* [UCLA Design Media Arts](http://dma.ucla.edu/), programa posgrado MFA, Los Angeles, California, Estados Unidos. Aquí son profesores [Casey Reas](http://reas.com/) y [Lauren McCarthy](http://lauren-mccarthy.com/), entre otros.

## Programación en p5.js

Ingresa al [Editor Web de p5.js](https://editor.p5js.org/).

Ahora vamos a programar en p5.js =) !

## Otras bibliotecas de JavaScript

* [clmtrackr](https://github.com/auduno/clmtrackr), biblioteca de detección facial, desarrollada por [Audun Mathias Øygard](https://www.auduno.com/).
* [ml5.js](https://ml5js.org/), biblioteca para aprendizaje de máquinas, desarrollada por la comunidad de [NYU ITP](https://tisch.nyu.edu/itp), incluyendo a [Daniel Shiffman](https://shiffman.net/), [Hannah Davis](http://www.hannahishere.com/),  [Cristóbal Valenzuela](https://cvalenzuelab.com/), [Alejandro Matamala](http://matamala.info/).
* [Three.js](https://threejs.org/), biblioteca gráfica 3D, desarrollada por []
* [Tone.js](https://tonejs.github.io/), biblioteca para crear aplicaciones musicales interactivas en el navegador, desarrollada por [Yotam Mann](https://yotammann.info/).

## Otros recursos interesantes

* [ml4a](http://ml4a.github.io/), libro Machine Learning for Artists.
* [Runway](https://runwayapp.ai/), herramientas de aprendizaje de máquinas.
* [Wekinator](http://www.wekinator.org/), plataforma para aprendizaje de máquinas.


## Referencia

* [p5.js/es](https://p5js.org/es/): sitio web en español de p5.js, incluye tutoriales, ejemplos y referencia.
* [Libro Introducción a p5.js](https://processingfoundation.press/es): libro introductorio, disponible en PDF paga-lo-que-quieras y en formato físico. EScrito por [Lauren McCarthy](http://lauren-mccarthy.com/), [Casey Reas](http://caesuras.net/) y [Ben Fry](https://benfry.com/), ilustrado por [Taeyoon Choi](http://taeyoonchoi.com/) y traducido al español por [Aarón Montoya-Moraga](http://montoyamoraga.io/).
* [Tutorial video Introducción a la programación con p5.js](https://www.youtube.com/watch?v=DtAHvMjMzMQ): tutorial por [Aarón Montoya-Moraga](http://montoyamoraga.io/) y [Guillermo Montecinos](http://guillemontecinos.cl/), para [Processing Foundation](https://processingfoundation.org/) y [The Coding Train](https://www.youtube.com/user/shiffman).
* [Taller introducción a la programación creativa con p5.js](https://github.com/guillemontecinos/programacion_creativa_p5js): realizado por [Guillermo Montecinos](http://guillemontecinos.cl/) y [CODED Escuela](http://codedescuela.cl/).
* [Charla en Processing Community Day 2017](https://www.youtube.com/watch?v=Ix5RTKRJW0A): charla sobre el proyecto p5.js en español, por [Aarón Montoya-Moraga](http://montoyamoraga.io/) y [Guillermo Montecinos](http://guillemontecinos.cl/).
