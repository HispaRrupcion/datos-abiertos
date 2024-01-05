<h1>Documentación HR - Datos Abiertos</h1>

Verás que hay dos carpetas en este repositorio, una llamada `reqjson` y otra llamada `reqcases`. La primera carpeta almacena en JSON datos de utilidad para la página, mientras que la segunda almacena los datos completos de cada caso de corrupción.

## `reqjson`

Aquí encontrarás 2 archivos, `Entidades.json` y `Casos.json`.

`Entidades.json` incluye los datos que se muestran en la página de "Entidades". El formato es el siguiente:

```json
{
    "NIEC": 1,
    "NOMBRE": "EMPRESAS PÚBLICAS",
    "IMAGEN": "https://hisparrupcion.vercel.app/public/orgBanner_empresasPublicas.png",
    "DESC": "Empresas financiadas con dinero público (de tus impuestos)."
},
```

- NIEC: **Número Identificador de Entidades Corruptas** - Un número único para identificar desde la base de código a cada entidad.
- NOMBRE: **Nombre de la entidad**
- IMAGEN: **URL a la imagen que se muestra en la web junto con el perfil de la entidad**
- DESC: **Una breve descripción del propósito / funcionamiento de cada entidad**

`Casos.json` incluye los datos básicos de todos los casos de corrupción que alberga la página. El formato es el siguiente:

```json
{
    "NIT": 1,
    "NOMRE": "Nombre del caso",
    "CONTEXTO": "Contexto de ejemplo (Este caso es una prueba técnica, no es real.)",
    "COSTE": 300000,
    "IMPUTADOS": ["José", "Pepito"],
    "ORG": 2,
    "JUDICIAL": true,
},
```

- NIT: **Número Identificador de Trama** - Similar al NIEC, sirve para identificar los casos.
- NOMBE: **Nombre del caso (sin incluir "trama", "caso", o parecidos, solo el nombre)**
- CONTEXTO: **Breve descripción del caso de corrupción**
- COSTE: **Coste en euros (sin puntuación, ni céntimos)**
- IMPUTADOS: **Todos los involucrados, con nombre y apellidos**
- ORG: **NIEC de la organización principal vinculada al caso (si no hay una org. vinculada, establecer en 0)**
- JUDICIAL: **Si se trata de un caso de corrupción que se investiga judicialmente, marcar `true`, si es una investigación independiente, sea o no de HR, marcar `false`**.

## `reqcases`

Dentro de esta carpeta habrá varias carpetas cuyo nombre será un número. Ese número es el NIT de cada trama. Dentro de cada carpeta hay dos archivos, `INDEX.md` (el texto que aparece en la página del caso), y `data.json`, que luce así:

```json
{
  "NOMBRE": "NOMBRE_CASO_DE_CORRUPCION",
  "IMPLICADOS": [
    {
      "NOMBRE": "Persona Uno",
      "FOTO": "URL",
      "ESTADO": 1,
      "CARGO": "Cargo de Ejemplo"
    },
    {
      "NOMBRE": "Persona Dos",
      "FOTO": "URL",
      "ESTADO": 3,
      "CARGO": "Otro cargo de Ejemplo"
    }
  ]
  "LOCALIZACION": "Madrid",
  "COSTE": 350000,
  "ANO": "2009",
  "ORG": 2,
  "ULTIMAREV": "15-11-2023"
}
```

- NOMBRE: **Nombre completo del caso (sin incluir "trama", "caso", o parecidos, solo el nombre)**
- IMPLICADOS: **Cada persona o entidad implicada.**
  - NOMBRE: **Nombre completo del implicado**
  - FOTO: **URL a la foto del implicado (si no hay, establecer en `null`)**
  - ESTADO: **Estado del implicado. 1 si está apresado. 2 si sancionado o condenado de otra forma. 3 si fue declarado culpable pero fue absuelto. 4 si fue inocente. 5 en cualquier otro caso.**
  - CARGO: **Papel ejercido *durante el momento del caso de corrupción* (p ej. "Secretario General del PSOE" si en ese momento era secretario general, independientemente de si a dia de hoy lo es o no)**
- LOCALIZACIÓN: **Lugar en el que se desarrolla la trama. Poner nombre de Comunidad Autónoma, o "Nacional" si abarca toda España.**
- COSTE: **Coste en euros, sin céntimos ni decimales**
- ANO (año): **Año en el que se produce el caso de corrupción (si abarca varios años, año en el que se presenta ante los juzgados)**
- ORG: **NIEC de la organización vinculada si la hay (si no, establecer en 0)**
- ULTIMAREV: **En formato DIA-MES-AÑO, última vez que se revisaron y/o actualizaron `data.json` o `INDEX.md` de ese caso.**
