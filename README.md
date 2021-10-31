# proyecto21GIIN
Trabajo para asignatura de proyectos

Proyecto Presentaciones digitales contables
El proyecto de este semestre estará basado en la presentación de documentos contables
digitales por parte de municipios/ayuntamientos a un organismo de control fiscal.
El proyecto está pensado, por su complejidad, para realizarse en grupos de 3 personas.
Pero puede realizarse en grupos de 2 o hasta de forma individual si es conveniente por
vuestra situación personal/trabajo formar un grupo.
Durante el curso iros viendo la teoría a necesaria, algunos aspectos serán de repaso de
asignaturas anteriores (diagramas de clase y casos de uso) o bases de datos, y otras
nuevas como puede ser la parte gráfica.
No hace falta que la primera entrega del proyecto incluya todos los aspectos. El proyecto
está pensado para hacerse de forma incremental. Recomiendo primero hacer un esquema
general y después ir abordando cada una de las funcionalidades. También podéis dejar la
parte gráfica para el final (una vez vista la teoría) y concentrarse primero en las
funcionalidades que se pueden realizar con los conocimientos que tienen de otras
asignaturas. La separación por capas se puede hacer inicialmente o hacia el final.
Funcionalidad
Tendremos 4 funcionalidades: Usuarios, Municipios, Presentaciones, e Información. Con
más detalle el menú permitirá (entre paréntesis las subopciones de cada apartado) después
de haberse autenticado con usuario y clave.
1. Usuarios (Alta, Baja, Modificación) [Sólo visible para usuarios Administradores]
2. Municipios (Alta, Baja, Modificación) [Sólo visible para usuarios Administradores]
3. Presentaciones (Alta, Baja, Modificación) [Visible para todos los usuarios. Los
usuarios Cuentadantes pueden realizar todas las operaciones sobre sus
Presentaciones. Los usuarios Fiscales pueden visualizar el contenido de las
Presentaciones de los municipios asignados. Los usuarios Fiscales Generales
pueden realizar todas las operaciones sobre las presentaciones. Los usuarios
Administradores pueden realizar todas las operaciones sobre todas las
Presentaciones]
4. Información (Estado actual [Presentaciones realizadas, Presentaciones adeudadas],
Histórico de Presentaciones) [Visible para todos]
0. Salir
Proyectos de programación - 21GIIN
Usuarios
Dar de alta/baja/modificación a los usuarios del sistema. Operación sólo disponible para
usuarios Administradores. Los cuales tendrán un nombre/identificador (caracteres, mín. 1,
máx. 10), clave (caracteres, mín. 4, máx. 8) y tipo de usuario ([Administradores, Fiscales,
Fiscales generales, y Cuentadantes])
Municipios
Dar de alta/baja/modificación a los Municipios. Los cuales tendrán un nombre/identificador
(caracteres, máx. 30), Categoría de Municipio (entero), y usuario Cuentadante.
El usuario Cuentadante tendrá funcionalidad limitada, permitiendo sólo visualizar la
categoría del municipio.
El usuario Fiscal y Fiscal General puede visualizar los municipios.
El usuario Administrador puede realizar todas las funcionalidades sobre los Municipios.
Convocatorias
Dar de alta/baja/modificación las Convocatorias a Presentaciones. Las Convocatorias
tendrán nombre/identificador (caracteres, máx. 100), descripción de presentación
(caracteres, máx. 2000), fecha de apertura (timestamp), fecha de cierre (timestamp,
posterior a la fecha de apertura), estado de apertura (booleano), documentación
respaldatoria requerida (lista de opciones, [Libro Diario, Libro Mayor, Balance de Sumas y
Saldos, Registro de Ingreso de Caja, Registro de Movimientos de Bancos]).
El usuario Cuentadante y usuario Fiscal sólamente puede visualizar las convocatorias.
El usuario Fiscal General y el usuario Administrador pueden crear, dar de baja, y modificar
convocatorias.
Presentaciones
Dar de alta/baja/modificación a las Presentaciones correspondientes a las convocatorias.
Las presentaciones tendrán una fecha de presentación (timestamp, posterior a la fecha de
apertura de la convocatoria), estado de apertura (binario, predeterminado en Verdadero),
documentación respaldatoria (lista, archivos adjuntos establecidos como requeridos en la
convocatoria así como adicionales).
El usuario Cuentadante puede crear y modificar presentaciones. También puede cambiar el
estado de apertura de verdadero a falso, pero no a la inversa.
El usuario Fiscal puede visualizar las presentaciones de los cuentadantes que tiene
asignados.
El usuario Fiscal General puede visualizar las presentaciones de los cuentadantes y puede
modificar el estado de apertura. Puede modificar la asignación de las presentaciones a uno
o varios usuarios Fiscales.
El usuario Administrador puede realizar cualquier operación sobre las Presentaciones.
Proyectos de programación - 21GIIN
Información
Estado actual del sistema:
● Convocatorias abiertas y cerradas con cantidad de Presentaciones por estado de
apertura.
● Resumen de Presentaciones de Convocatorias por Municipio con cantidad de
documentos adjuntos presentados.
● Detalle de Presentaciones de convocatorias con histórico de modificaciones al
estado de apertura de la Presentación.
Salir
Salir del programa
Especificación
Realizar el diagrama de clases del proyecto
Realizar el diagrama de casos de uso
Tendremos cuatro tipos de usuario: Administrador (puede realizar todas las operaciones
sobre usuarios, Municipios, Convocatorias, y Presentaciones), Fiscal General (puede
realizar todas las operaciones sobre las convocatorias, excepto eliminar las que tienen al
menos una presentación), Fiscal (puede visualizar las presentaciones de los usuarios
Cuentadantes) y Cuentadante (puede crear y modificar Presentaciones para Convocatorias
abiertas).
Infraestructura
Parte de la evaluación es la “infraestructura” elegida para compartir el proyecto entre los
miembros del grupo y conmigo (sólo lectura). No se establecen preferencias mientras que
se implementen las funcionalidades. El repositorio debe ser privado para terceros y editable
para todos los miembros del grupo. El docente tendrá permisos de lectura, el cual será
asociado en la plataforma elegida (Github, Bitbucket, etc).
Base de datos
Para dar persistencia a los datos, se usarán una base de datos en la nube. Se recomienda
usar AWS. La cuenta estudiante otorga hasta $50 de crédito gratuito en la modalidad de
servidores pequeños, con acceso a bases de datos como MaríaDB o PostgreSQL. En caso
de usar otro servicio, éste debe permitir el acceso remoto.
Proyectos de programación - 21GIIN
Interfaz gráfica
El programa debe contar con una interfaz gráfica, que puede ser implementada con Java
AWT o equivalente.
Capas
La arquitectura del producto debe estar organizada en capas. Se pide una adecuada
separación de funcionalidades en presentación, negocio/lógica, y acceso a
datos/persistencia.
Entregas
Informe en PDF
● Portada (asignatura, miembros del grupo, número de entrega [1-4])
● División de tareas: Descripción, tiempo de la entrega, persona responsable
● Datos de acceso al servicio de base de datos en la nube
● Diagramas de clases, casos de uso, esquema de bases de datos
● Descripciones adicionales
Código fuente
Sólo incluir código fuente relevante y correspondiente a cada entrega.
Notas
Antes de empezar a programar hacer un esquema de cómo piensan solucionar el
problema y las posibles tareas. Pueden mandármelo por email como entrega 0, para tener
feedback.
Hay varias maneras de realizar el proyecto, cualquiera que cumpla con lo que se solicita a
nivel funcional y que siga las pautas de documentación y estructura, es válida, siempre que
se use Java.
Un punto donde podéis elegir es en el tipo de estructuras de datos (tablas, vectores, listas,
etc) que serán necesarios para guardar todos los parámetros del sistema que se solicitan.
En principio, cualquier aproximación que se haga es aceptable. No tendrán más o menos
puntos por usar una en particular. Elegir la más sencilla.
Proyectos de programación - 21GIIN
AWS ofrece hasta 20GB de almacenamiento para la capa gratuita del servicio de bases de
datos relacionales (RDS), el cual se puede ampliar aunque con impacto en los costos.
Las dudas pueden ser enviadas por email a eduardo.zamudio@campusviu.es
