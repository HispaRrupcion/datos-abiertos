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
    "CONTEXTO": "Contexto de ejemplo (Este caso es una prueba técnica, no es real.)",
    "COSTE": 300000,
    "IMPUTADOS": ["José", "Pepito"],
    "JUDICIAL": true,
},
```

- NIT: **Número Identificador de Trama** - Similar al NIEC, sirve para identificar los casos.
- CONTEXTO: **Breve descripción del caso de corrupción**
- COSTE: **Coste en euros (sin puntuación, ni céntimos)**
- IMPUTADOS: **Todos los involucrados, con nombre y apellidos**
- ORG: **NIEC de la organización principal vinculada al caso (si no hay una org. vinculada, establecer en 0)**
- JUDICIAL: **Si se trata de un caso de corrupción que se investiga judicialmente, marcar `true`, si es una investigación independiente, sea o no de HR, marcar `false`**.
