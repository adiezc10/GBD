# Unidad 1: Sistemas de Almacenamiento de la Información
Esta unidad tiene como objetivo introducir los conceptos básicos relacionados con los mecanismos de almacenamiento, su clasificación, ventajas e inconvenientes, y sentar las bases para comprender el funcionamiento de los sistemas gestores de bases de datos (SGBD).

- [Unidad 1: Sistemas de Almacenamiento de la Información](#unidad-1-sistemas-de-almacenamiento-de-la-información)
  - [0. Introducción](#0-introducción)
  - [1. Ficheros](#1-ficheros)
    - [1.1 Tipos de ficheros y formatos](#11-tipos-de-ficheros-y-formatos)
    - [1.2 Problemas de los sistemas basados en ficheros](#12-problemas-de-los-sistemas-basados-en-ficheros)
  - [2. Bases de Datos](#2-bases-de-datos)
  - [3. Sistemas Gestores de Bases de Datos (SGBD)](#3-sistemas-gestores-de-bases-de-datos-sgbd)
  - [4. Bases de Datos Centralizadas y Distribuidas](#4-bases-de-datos-centralizadas-y-distribuidas)
  - [5. Modelo de Capas](#5-modelo-de-capas)
  - [6. Lenguaje SQL](#6-lenguaje-sql)
  - [7. Transacciones y ACID](#7-transacciones-y-acid)
  - [8. Diseño de Bases de Datos](#8-diseño-de-bases-de-datos)
  - [9. Tipos de Usuarios](#9-tipos-de-usuarios)
  - [10. Actividades de aprendizaje](#10-actividades-de-aprendizaje)

## 0. Introducción
En el contexto de los sistemas informáticos, el almacenamiento de la información es un aspecto fundamental que ha evolucionado desde simples estructuras de ficheros hasta complejos sistemas de bases de datos. 

A lo largo de la historia de la informática, el tratamiento de la información ha pasado de ser un proceso centrado en los programas (orientado al proceso) a estar centrado en los datos (orientado a la información). Esta evolución ha permitido mejorar la eficiencia, la seguridad, la integridad y la accesibilidad de los datos, especialmente en entornos multiusuario y distribuidos.

![Sistema distribuído](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhIhTq1sYW-vo483fv0pQ2BhNonPsvfcSGyjGlE3N_op8PTQlxk4tMUZCSEKUFWoLEqaZXKJAutXxZAx27UzUd1SG7JcBD3nrABEMX-6wMv777_5KUwSEQkcnaD6Py2l-nEw8Pf_6CHi_9_/s320/sistemasdistribuidos.png)

## 1. Ficheros
Los ficheros son estructuras de información que permiten almacenar datos en dispositivos físicos como discos duros, memorias USB, SSD, etc. Son gestionados por el sistema operativo y constituyen la forma más básica de almacenamiento digital. Cada fichero tiene un nombre y una extensión que indica el tipo de contenido que almacena (por ejemplo, .txt, .jpg, .mp3).

### 1.1 Tipos de ficheros y formatos
Los ficheros pueden clasificarse según:

a) Su contenido interno

- **Ficheros de texto**: contienen caracteres codificados en sistemas como ASCII o Unicode. Son legibles por humanos y por editores de texto. Ejemplos:
  - .txt: texto plano.
  - .csv: valores separados por comas.
  - .html: páginas web.
  - .xml: datos estructurados.

- **Ficheros binarios**: contienen datos codificados que no son legibles directamente. Requieren programas específicos para su interpretación. Ejemplos:
    - .exe: ejecutables.
    - .jpg, .png: imágenes.
    - .mp3, .wav: audio.
    - .docx, .xlsx: documentos de ofimática.

> **Ejemplo práctico**: si abrimos un fichero .docx con el bloc de notas, veremos una secuencia de caracteres sin sentido, ya que el editor no interpreta el formato binario. En cambio, un .txt mostrará el contenido directamente.

b) Su organización o forma de acceso
- **Ficheros secuenciales**: los datos se almacenan uno tras otro. Para acceder a un dato específico, es necesario recorrer todos los anteriores. Son eficientes para escritura continua, pero lentos para búsquedas. Ejemplo: una lista de clientes en un fichero .txt.
- **Ficheros de acceso directo** (organización directa): permiten acceder a un dato concreto sin necesidad de recorrer todo el fichero. Esto se logra mediante posiciones fijas o cálculos de desplazamiento. Ejemplo: un fichero donde cada registro ocupa exactamente 100 bytes.
- **Ficheros indexados**: utilizan estructuras auxiliares (índices) que permiten localizar rápidamente los datos. El índice actúa como una guía que relaciona claves con posiciones en el fichero. Ejemplo: un fichero de libros con un índice por ISBN.

### 1.2 Problemas de los sistemas basados en ficheros
Aunque los ficheros son útiles para almacenar información, presentan varias limitaciones cuando se utilizan como base para sistemas de gestión:
- **Redundancia**: la misma información puede estar duplicada en varios ficheros.
- **Inconsistencia**: si se actualiza un dato en un fichero pero no en otro, se genera incoherencia.
- **Dependencia física**: los programas dependen de la estructura interna del fichero, lo que dificulta su mantenimiento.
- **Falta de seguridad**: no hay control sobre quién accede a qué datos.
- **Acceso limitado**: no se pueden realizar consultas complejas sin desarrollar programas específicos.
- **Dificultad para compartir datos**: cada aplicación puede tener su propio formato, lo que complica la interoperabilidad.

> **Ejemplo**: en una empresa, el departamento de ventas y el de contabilidad pueden tener ficheros distintos con los datos de los clientes. Si un cliente cambia de dirección, ambos ficheros deben actualizarse manualmente. Si se olvida hacerlo en uno de ellos, se genera una inconsistencia.

> Actividades de aprendizaje 


## 2. Bases de Datos
Una base de datos es una colección organizada de datos que pueden ser compartidos por múltiples usuarios y aplicaciones. Se estructuran en tablas, que contienen registros (filas) y campos (columnas).

Los conceptos clave incluyen: dato, tipo de dato, campo, registro, tabla, consulta, índice, vista, informe, script, esquema. Las bases de datos permiten almacenar, consultar, actualizar y controlar información de forma eficiente.

Tipos de bases de datos: jerárquicas, en red, relacionales, orientadas a objetos, documentales, multidimensionales, deductivas. Usos: administrativos, científicos, motores de búsqueda, bibliotecas, censos, antivirus, etc.

**Actividad:** Diseña una tabla simulada en papel con campos y registros. Clasifica bases de datos reales según su tipo.

## 3. Sistemas Gestores de Bases de Datos (SGBD)
Un SGBD es un conjunto de programas que permiten definir, manipular, controlar y mantener una base de datos. Facilita el acceso concurrente, garantiza la integridad y seguridad de los datos, y permite el uso de transacciones.
Funciones principales: almacenamiento, acceso, actualización, seguridad, integridad, concurrencia, recuperación ante fallos, independencia de datos, conectividad externa, estadísticas de uso.
Componentes: procesador de consultas, gestor de transacciones, gestor de concurrencia, gestor de recuperación, gestor de archivos, gestor de memoria intermedia, diccionario de datos.
Tipos: SGBD ofimáticos (Access), corporativos (Oracle, MySQL, DB2), distribuidos, paralelos, orientados a objetos, objeto-relacionales.
**Actividad:** Relaciona funciones del SGBD con las leyes de Codd. Compara características de varios SGBD.
## 4. Bases de Datos Centralizadas y Distribuidas
Las bases de datos centralizadas se almacenan en un único servidor. Las distribuidas reparten los datos entre varios nodos conectados en red. También existen bases de datos reflejadas (copias en varios servidores) y locales (acceso desde el mismo equipo).
**Actividad:** Analiza ventajas e inconvenientes de cada tipo. Dibuja un esquema de red con distintos tipos de ubicación.
## 5. Modelo de Capas
La arquitectura ANSI-SPARC define tres niveles de abstracción: externo (vistas de usuario), conceptual (estructura lógica), interno (almacenamiento físico).
Cada nivel permite independencia respecto a los demás: lógica (cambios en el modelo sin afectar vistas) y física (cambios en el almacenamiento sin afectar el modelo).
Los SGBD operan en cinco capas: interfaz de usuario, capa de acceso, diccionario de datos, núcleo, sistema operativo.
**Actividad:** Dibuja el modelo de capas y explica el flujo de una consulta desde el usuario hasta el sistema operativo.
## 6. Lenguaje SQL
SQL es el lenguaje estándar para interactuar con bases de datos relacionales. Permite definir estructuras, manipular datos, controlar accesos y gestionar transacciones.
Se divide en sublenguajes: DML (SELECT, INSERT, UPDATE, DELETE), DDL (CREATE, ALTER, DROP), DCL (GRANT, REVOKE), TCL (COMMIT, ROLLBACK).
Ejemplos: creación de tablas con restricciones, inserción de datos, consultas con condiciones, actualizaciones y borrado de registros.
**Actividad:** Crea tablas con restricciones y realiza consultas. Investiga el concepto de SQL Injection y cómo prevenirlo.
## 7. Transacciones y ACID
Una transacción es un conjunto de operaciones que deben ejecutarse como una unidad. Las propiedades ACID garantizan su fiabilidad: Atomicidad (todo o nada), Consistencia (coherencia), Aislamiento (independencia), Durabilidad (persistencia).
Los SGBD permiten definir transacciones, controlar errores y asegurar que los cambios se confirmen (COMMIT) o se cancelen (ROLLBACK).
**Actividad:** Simula una transferencia entre cuentas con instrucciones SQL que incluyan COMMIT y ROLLBACK.
## 8. Diseño de Bases de Datos
Un mal diseño puede provocar redundancia, contradicciones, pérdida de información y problemas de integridad. La normalización y el uso adecuado de claves primarias y foráneas ayudan a evitar estos problemas.
Relaciones entre tablas: 1 a 1, 1 a n, n a n. Las relaciones n a n requieren tablas intermedias. Las claves primarias identifican registros únicos; las claves foráneas establecen vínculos entre tablas.
**Actividad:** Analiza un caso de mala estructuración y propón una solución con tablas intermedias.
## 9. Tipos de Usuarios
Los usuarios de una base de datos se clasifican según su interacción: normales (uso básico), programadores (desarrollan aplicaciones), sofisticados (consultas avanzadas), especializados (aplicaciones no tradicionales), administradores (gestión del sistema).
**Actividad:** Identifica roles en un sistema real y describe sus funciones.
## 10. Actividades de aprendizaje
Se recomienda realizar prácticas con Access o LibreOffice Base: crear tablas, establecer relaciones, diseñar formularios, generar informes, ejecutar consultas.

**Actividad:** Realiza una práctica guiada con Access que incluya creación de tablas, relaciones y consultas.

