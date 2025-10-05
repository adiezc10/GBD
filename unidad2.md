# Unidad 2: Diseño lógico de bases de datos

- [Unidad 2: Diseño lógico de bases de datos](#unidad-2-diseño-lógico-de-bases-de-datos)
- [1. Introducción al diseño lógico](#1-introducción-al-diseño-lógico)
  - [1.1. ¿Qué es el diseño lógico?](#11-qué-es-el-diseño-lógico)
  - [1.2. Fases del diseño de bases de datos](#12-fases-del-diseño-de-bases-de-datos)
  - [1.3. Modelos de datos: conceptual, lógico y físico](#13-modelos-de-datos-conceptual-lógico-y-físico)
- [2. Representación del problema: el modelo entidad/relación (E/R)](#2-representación-del-problema-el-modelo-entidadrelación-er)
- [3. El modelo E/R ampliado](#3-el-modelo-er-ampliado)
- [4. Construcción de diagramas E/R](#4-construcción-de-diagramas-er)


# 1. Introducción al diseño lógico

## 1.1. ¿Qué es el diseño lógico?
El diseño lógico de bases de datos es la fase intermedia entre el análisis del problema y la implementación física de la base de datos Consiste en **representar la información relevante** de un dominio del mundo real mediante un modelo que pueda ser interpretado por un sistema gestor de bases de datos (SGBD).

El diseño lógico:
- **No depende del SGBD** que se vaya a utilizar.
- Representa los datos mediante estructuras como tablas, atributos, claves y relaciones.
- Se basa en el modelo conceptual, normalmente representado mediante diagramas entidad/relación (E/R), que veremos en esta unidad.

> Ejemplo: En una empresa que gestiona pedidos, el diseño lógico incluiría tablas como Clientes, Pedidos, Productos, con sus respectivos campos y relaciones entre ellas.

## 1.2. Fases del diseño de bases de datos
El proceso completo de diseño de una base de datos se divide en tres fases:
- **Diseño conceptual**
  - Representa el problema desde el punto de vista del usuario.
  - Utiliza diagramas E/R para modelar entidades, relaciones, atributos, cardinalidades, etc.
- **Diseño lógico**
  - Traduce el modelo conceptual a un modelo relacional.
  - Define tablas, claves primarias y foráneas, restricciones de integridad, etc.
- **Diseño físico**
  - Implementa el modelo lógico en un SGBD concreto.
  - Incluye aspectos como tipos de datos, índices, rendimiento, almacenamiento.

Saltarse el diseño conceptual puede ahorrar tiempo en problemas simples, pero en sistemas complejos puede generar incoherencias y pérdida de calidad.

## 1.3. Modelos de datos: conceptual, lógico y físico

| Modelo       | Descripción | Herramientas |
|--------------|--------------|--------------|
| Conceptual   | Representa el problema desde el punto de vista del usuario.     | Diagramas E/R     |
| Lógico       | Traduce el modelo conceptual a estructuras que entiende el SGBD.   | Modelo relacional    |
| Físico       | Implementa el modelo lógico en un SGBD concreto.   | SQL (DDL), índices, tipos de datos     |

> Ejemplo:
>  - Conceptual: Entidades Empleado, Departamento, relación Trabaja_en.
>  - Lógico: Tablas Empleados, Departamentos, con claves primarias y foráneas.
>  - Físico: Script SQL que crea las tablas en MySQL.

# 2. Representación del problema: el modelo entidad/relación (E/R)

2.1. Entidades y ocurrencias
2.2. Atributos: tipos, dominios y notaciones
2.3. Relaciones: participación, cardinalidad y modalidad
2.4. Relaciones reflexivas y no binarias
2.5. Entidades débiles
2.6. Ejemplo completo de diagrama E/R

# 3. El modelo E/R ampliado

3.1. Generalización y especialización
3.2. Jerarquías y herencia

# 4. Construcción de diagramas E/R

4.1. Herramientas gráficas para modelado
4.2. Buenas prácticas en la representación
4.3. Documentación de restricciones no representables

