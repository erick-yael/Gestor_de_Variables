# 📊 Gestor de Variables 

> **Sistema integral para la gestión, carga masiva y categorización inteligente de variables e indicadores de gestión pública.**

---

## 🚀 Descripción

Esta aplicación web, desarrollada en **Flask**, permite administrar variables e indicadores utilizados en el seguimiento de políticas públicas, con un enfoque en ejes de corrupción, prevención, detección, sanción y fiscalización.

El sistema ofrece una interfaz dinámica para **editar, filtrar, ordenar y exportar** datos, además de potentes herramientas para **cargar información desde archivos CSV o carpetas comprimidas (ZIP)** que contienen conjuntos de datos y diccionarios, detectando duplicados y asignando automáticamente categorías (Proceso, Eje, Tema) mediante **modelos de Machine Learning**.

---

## 🛠️ Características principales

- **Carga masiva de datos**:
  - Archivos **CSV** con detección inteligente de duplicados.
  - **Carpetas ZIP** con estructura `conjunto_de_datos/`, `diccionario_de_datos/` y `metadatos/` (soporta formato antiguo y nuevo).

- **Categorización automática**:
  - Asigna **Proceso, Eje y Tema** basándose en el nombre de la variable usando un pipeline de **TF-IDF + Naive Bayes**.
  - Sistema de **fallback por palabras clave** cuando los modelos no tienen suficiente confianza.

- **Interfaz de usuario avanzada (SPA)**:
  - Tabla editable con **filtros, ordenamiento múltiple (Shift+Click)** y edición directa en celdas.
  - **Redimensionamiento visual** de filas y columnas arrastrando bordes.
  - Paginación, selección masiva y exportación a CSV.

- **Historial de cargas**: Registra cada importación (CSV o ZIP) en una tabla `cargas` de Supabase.

- **Modelos ML reentrenables**: Entrena los modelos con los datos etiquetados existentes y haz rollback si es necesario.

- **Exposición segura**: Túnel público mediante **ngrok** para acceder desde cualquier lugar.

---

## 📂 Estructura del proyecto

El código está organizado en un **notebook de Google Colab** (`propuesta_cargar_datos_pagina.ipynb`) que contiene todos los bloques:

- **Bloques 1-4**: Configuración, constantes y funciones auxiliares.
- **Bloques 5-7**: Procesamiento de CSV y carpetas ZIP.
- **Bloque 8**: Interfaz completa (CSS, HTML, JS).
- **Bloques 9-10**: API Flask y rutas.
- **Bloque 11**: Inicio del servidor Flask y túnel ngrok.

Puedes ejecutar todo el notebook secuencialmente en Colab para poner en marcha la aplicación.

---

## ⚙️ Requisitos previos

- **Python 3.10+**
- **Cuenta de Supabase** (con tablas `variables` y `cargas` creadas)
- **Token de ngrok** (gratuito)
- **Git** (para clonar o subir el proyecto)

---

## 🔧 Configuración e instalación

### 1. Clona el repositorio (o descarga el notebook)

```bash
git clone https://github.com/erick-yael/Gestor_de_Variables.git
cd Gestor_de_Variables

