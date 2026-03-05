# Banco de Problemas Provincial

Este proyecto es un dashboard interactivo creado para la **Agencia Neuquina de Innovación para el Desarrollo**. Su objetivo es visualizar, filtrar y detallar las diversas problemáticas relevadas a lo largo de las distintas regiones de la provincia de Neuquén.

## 🚀 Características Principales

- **Visualización Dinámica:** Carga de datos de forma dinámica y automática desde un archivo CSV alojado en **Google Sheets**, facilitando la actualización de la información sin necesidad de tocar el código fuente.
- **Filtrado por Regiones:** Menú lateral interactivo que permite filtrar las problemáticas según las diferentes regiones de la provincia (Por ejemplo: Vaca Muerta, Confluencia, Del Limay, Alto Neuquén, Comarca, etc.).
- **Estadísticas en Tiempo Real:** Contadores automáticos que reflejan la cantidad de problemáticas y regiones disponibles según los datos obtenidos.
- **Buscador Integrado:** Campo de búsqueda rápida que filtra resultados en tiempo real por título, ubicación o descripción del problema.
- **Diseño Moderno y Responsivo:** Interfaz gráfica atractiva (UI/UX) utilizando una paleta de colores coherente y la tipografía *Google Sans* para una lectura cómoda y moderna. 
- **Panel de Detalles:** Al hacer clic sobre una problemática de la tabla, se despliega un panel lateral detallado ("drawer") con toda la información extendida sobre ese problema específico.

## 🛠️ Tecnologías Empleadas

El proyecto es estático, desarrollado utilizando únicamente tecnologías nativas web ("Vanilla"):
- **HTML5:** Para la semántica y estructura del dashboard.
- **CSS3:** Variables CSS, Grid, Flexbox y transformaciones para animaciones fluidas.
- **JavaScript (ES6):** Para la lógica asíncrona (`fetch`), filtrado de datos y manipulación del DOM.
- **[PapaParse](https://www.papaparse.com/):** Librería veloz e integrada vía CDN para la conversión e interpretación del archivo CSV proveniente de Google Sheets.
- **Google Fonts (CDNFonts):** Para el renderizado de la tipografía corporativa requerida (Google Sans).

## 📍 Instrucciones de Ejecución

Dado que el entorno web moderno tiene políticas de seguridad estrictas llamadas **CORS (Cross-Origin Resource Sharing)**, el navegador bloquea la carga de la API de Google Sheets si se intenta abrir el archivo directamente haciendo "doble clic" sobre `dashboard-problems.html` y originando desde una ruta `file://`.

Para poder ejecutar el proyecto y visualizar los datos correctamente, **debes correrlo dentro de un servidor local**. 

### Con Visual Studio Code (Recomendado)
1. Abre este directorio en [Visual Studio Code](https://code.visualstudio.com/).
2. Ve a las extensiones y busca la extensión **Live Server** (creada por *Ritwick Dey*) e instálala.
3. Haz clic derecho sobre el archivo `dashboard-problems.html` y selecciona la opción **"Open with Live Server"**.
4. ¡El proyecto se abrirá automáticamente en tu navegador predeterminado y el contenido del CSV cargará sin errores de CORS!

### Alternativa con Python (Si tienes Python instalado)
1. Abre una terminal en el directorio raíz de este proyecto.
2. Ejecuta el comando para levantar un servidor web básico:
   ```bash
   python -m http.server 8000
   ```
3. Abre tu navegador y dirígete a `http://localhost:8000/dashboard-problems.html`.

## 🗃️ Formato Origen de los Datos (Excel/Google Sheets)

La información visualizada proviene de un [documento público de Google Sheets] configurado para publicar sus datos en formato CSV. 

| REGIÓN | Ubicación | nombre del problema | descripción del problema |
|--------|-----------|---------------------|--------------------------|
| CONFLUENCIA | Plottier  | Faltante cloacal    | En el barrio...        |

_**Nota interna:** Si alguna vez se altera la estructura o los nombres de los encabezados ('REGIÓN', 'Ubicación', etc.) en la primera fila de Google Sheets, deberán modificarse también en el archivo `dashboard-problems.html` de JS para asegurar que el sistema mapee correctamente todas las propiedades._

---

*Desarrollado para la gestión y seguimiento del Banco de Problemas de Neuquén - 2024 / 2026.*
