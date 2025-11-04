[metal_bands_db_doc.md](https://github.com/user-attachments/files/23342948/metal_bands_db_doc.md)
# 🎸 Base de datos SoundVault

> Este proyecto nace de mi interés por aprender MySQL y mejorar mis técnicas en bases de datos. Es un proyecto personal que refleja mi gusto por la música metal y sus diversos subgéneros.
La base de datos actualmente contiene información detallada sobre 188 bandas de metal que abarcan desde la era clásica de los años 60 hasta lanzamientos modernos de 2025. Los datos están organizados en tres tablas interconectadas que cubren bandas, géneros y países.
Este es un proyecto en constante evolución - la idea es seguir agregando más bandas y expandir la información con álbumes, miembros, y otros datos relevantes.

[![License: MIT](https://img.shields.io/badge/Licencia-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![CSV](https://img.shields.io/badge/Formato-CSV-green.svg)]()
[![Bandas](https://img.shields.io/badge/Bandas-188-red.svg)]()
[![Países](https://img.shields.io/badge/Países-39-blue.svg)]()

---

## 📊 Descripción General

Esta base de datos contiene información detallada sobre **188 bandas de metal** que abarcan desde la era clásica de los años 60 hasta lanzamientos modernos de 2025. Los datos están organizados en tres tablas interconectadas que cubren bandas, géneros y países.

### Estadísticas Rápidas
- 🎵 **35 géneros de metal** (desde Atmospheric Black Metal hasta Thrash)
- 🌍 **39 países** representados
- 📅 **6 décadas** de historia del metal (1967-2025)
- 🤘 Bandas legendarias: Metallica, Iron Maiden, Black Sabbath, Burzum, y muchas más

---

## 🗂️ Estructura de la Base de Datos

```
┌─────────────┐         ┌──────────────┐         ┌─────────────┐
│    pais     │         │     Banda    │         │   genero    │
├─────────────┤         ├──────────────┤         ├─────────────┤
│ id_pais (PK)│◄────┐   │ id_banda (PK)│   ┌────►│id_genero(PK)│
│ nombre_pais │     └───│ nombre       │───┘     │nombre_genero│
└─────────────┘         │ año_inicio   │         └─────────────┘
                        │ id_pais (FK) │
                        │ id_genero(FK)│
                        └──────────────┘
```

### Tablas

#### 🎤 `bandas_final.csv`
Tabla principal con información de las bandas.

| Campo | Tipo | Descripción |
|-------|------|-------------|
| `nombre` | varchar | Nombre de la banda |
| `año_inicio` | smallint | Año de formación |
| `id_genero` | smallint | Referencia al género |
| `id_pais` | smallint | Referencia al país |

#### 🎶 `generos.csv`
Catálogo de géneros y subgéneros del metal.

| Campo | Tipo | Descripción |
|-------|------|-------------|
| `id_genero` | mediumint | ID del género (Clave Primaria) |
| `nombre` | varchar | Nombre del género |

#### 🌎 `paises.csv`
Catálogo de países.

| Campo | Tipo | Descripción |
|-------|------|-------------|
| `id_pais` | smallint | ID del país (Clave Primaria) |
| `nombre` | varchar | Nombre del país |

---

## 🎵 Clasificación por Género

La base de datos incluye una taxonomía completa de subgéneros del metal:

### Familia Black Metal
- **Atmospheric Black Metal** - Enfoque ambiental y naturaleza
- **Symphonic Black Metal** - Elementos orquestales
- **Melodic Black Metal** - Riffs melódicos y hooks
- **Post-Black Metal** - Experimental y atmosférico
- **Ambient Black Metal** - Minimalista y atmosférico

### Familia Death Metal
- **Death Metal** - Estilo brutal clásico
- **Melodic Death Metal** - Aproximación melódica sueca
- **Progressive Death Metal** - Estructuras complejas

### Metal Tradicional
- **Heavy Metal** - Los cimientos
- **Power Metal** - Rápido y melódico
- **Thrash Metal** - Agresivo y veloz
- **Speed Metal** - Riffs a alta velocidad

### Metal Moderno
- **Nu Metal** - Influencias alternativas
- **Metalcore** - Fusión con hardcore punk
- **Industrial Metal** - Elementos electrónicos
- **Groove Metal** - Riffs orientados al groove

### Géneros Especializados
- **Folk Metal** - Instrumentos tradicionales
- **Doom Metal** - Lento y pesado
- **Progressive Metal** - Composiciones complejas
- **Southern Metal** - Influencia blues

---

## 🌍 Distribución Geográfica

### Principales Países por Cantidad de Bandas

| País | Géneros Destacados | Bandas Ejemplo |
|------|-------------------|----------------|
| 🇺🇸 **Estados Unidos** | Thrash, Nu Metal, Death | Metallica, Slayer, Pantera |
| 🇩🇪 **Alemania** | Thrash, Power | Kreator, Rammstein, Helloween |
| 🇸🇪 **Suecia** | Melodic Death Metal | At The Gates, Dark Tranquility |
| 🇳🇴 **Noruega** | Black Metal | Burzum, Darkthrone, Gorgoroth |
| 🇬🇧 **Inglaterra** | NWOBHM | Iron Maiden, Judas Priest |
| 🇦🇷 **Argentina** | Heavy Metal, Thrash | Hermética, Horcas, Malón |
| 🇫🇮 **Finlandia** | Melodic Death, Folk | Children of Bodom, Finntroll |

### Diversidad Geográfica
La base de datos abarca **5 continentes** incluyendo bandas de:
- 🇰🇪 Kenia (Nelecc)
- 🇮🇩 Indonesia (Pure Wrath)
- 🇦🇺 Australia (Be'lakor)
- 🇲🇽 México (Nostalghia)
- 🇮🇸 Islandia (Sólstafir)

---

## 📅 Línea de Tiempo Histórica

```
1960s-1970s  │ ████░░░░░░ Black Sabbath, Judas Priest, Iron Maiden
1980s        │ ████████░░ Metallica, Slayer, Megadeth, Bathory
1990s        │ ██████████ Burzum, Darkthrone, Children of Bodom
2000s        │ ███████░░░ Agalloch, DevilDriver, Be'lakor
2010s-2020s  │ █████████░ Grima, Blackbraid, Afsky, Pure Wrath
```

### Momentos Destacados por Era
- **1968-1975**: Nacimiento del Heavy Metal (Black Sabbath, Rainbow, Motörhead)
- **1981-1989**: Explosión del Thrash Metal (Big 4, Thrash alemán)
- **1991-1996**: Segunda Ola del Black Metal (escena noruega)
- **2010-2025**: Renacimiento del Atmospheric Black Metal

---

## 🚀 Comenzando

### Requisitos Previos
- Cualquier lector de CSV (Excel, Google Sheets, LibreOffice)
- MySQL/PostgreSQL (para importar la base de datos)

### Inicio Rápido

#### Importar a MySQL

```sql
-- Crear base de datos
CREATE DATABASE metal_bands CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
USE metal_bands;

-- Crear tablas
CREATE TABLE pais (
    id_pais SMALLINT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(100) NOT NULL UNIQUE
);

CREATE TABLE genero (
    id_genero MEDIUMINT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(100) NOT NULL UNIQUE
);

CREATE TABLE banda (
    id_banda MEDIUMINT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(100) NOT NULL,
    año_inicio VARCHAR(10),
    id_pais SMALLINT,
    id_genero MEDIUMINT,
    FOREIGN KEY (id_pais) REFERENCES pais(id_pais),
    FOREIGN KEY (id_genero) REFERENCES genero(id_genero)
);

-- Cargar datos usando LOAD DATA INFILE o herramientas de importación
```

---


## 🐛 Problemas Conocidos y Calidad de Datos

### Limitaciones Actuales

⚠️ **Codificación de Caracteres**: Algunos nombres de bandas con caracteres especiales pueden mostrarse incorrectamente (cirílico, acentos)

⚠️ **Datos Faltantes**:
- Algunas bandas tienen "?" o "-" como año de formación

### Mejoras Planificadas
- [ ] Consolidar países duplicados
- [ ] Normalizar nomenclatura de géneros
- [ ] Corregir codificación a UTF-8
- [ ] Reemplazar "?" y "-" con valores NULL
- [ ] Agregar restricciones de validación de datos
- [ ] Incluir metadata adicional (álbumes, miembros)

---

## 📈 Casos de Uso

Esta base de datos es perfecta para:
- 📊 **Análisis de Datos**: Explorar tendencias en la evolución de la música metal
- 🎓 **Proyectos Educativos**: Aprender diseño de bases de datos y SQL
- 🔍 **Descubrimiento Musical**: Encontrar bandas por país y género
- 📱 **Desarrollo de Apps**: Construir una enciclopedia de bandas de metal
- 📉 **Visualización**: Crear gráficos de geografía musical del metal

---

## 📜 Licencia

Este proyecto está licenciado bajo la Licencia MIT - siéntete libre de usar estos datos para cualquier propósito.

---

## 🙏 Agradecimientos

- Metal Archives ([metal-archives.com](https://www.metal-archives.com/)) por la referencia de clasificación de géneros
- La comunidad global del metal por mantener viva la música
- Todas las bandas incluidas en esta base de datos por sus contribuciones a la música metal

---

## 📧 Contacto

¿Preguntas, sugerencias o quieres discutir sobre metal? ¡Abre un issue o inicia una discusión!

---

**🤘 ¡Mantente brutal, mantente metal! 🤘**

---
