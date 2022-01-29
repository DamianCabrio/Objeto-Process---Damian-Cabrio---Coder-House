# Objeto process de Node.js
### DAMIÁN CABRIO

## Correr el proyecto localmente
Primero se debe instalar los paquetes desde npm con `npm i`
Para correr el proyecto localmente se debe correr el siguiente comando `npm run dev`. Si se quiere correr el proyecto con un puerto en particular se debe agregar a este comando el parámetro `-p puerto`. Por ejemplo `npm run dev -- -p 2000`.

También se debe crear y popular un archivo .env, basándose en el archivo .env.example.
Las variables que se deben agregar al archivo .env son: `SESSION_SECRET`, `MONGODB_URL`, `FB_CLIENT_ID`, `FB_CLIENT_SECRET` y `FB_CALLBACK_URL`.

## Rutas del desafío.
Como lo pedía él desafió, se generaron las rutas `/info` y `/api/random?cant=cantidad`, utilizando el objeto `process` de Node.js.
- La ruta `/info` devuelve un JSON con la información del entorno de ejecución pedida: Argumentos de entrada, Path de ejecución, Sistema operativo, Process ID, Versión de Node.js, Carpeta del proyecto y Memoria total reservada.

- La ruta `/api/random` devuelve un JSON con una objeto de números aleatorios como clave, y la cantidad de veces que salieron como valor. La ruta acepta un parámetro `cant`, que indica la cantidad de números aleatorios que se quiere generar (Se verifica que sea un número). Si no se pasa este parámetro, se generan por defecto 100000000 números aleatorios. Al usar la función `fork` para generar los números aleatorios, el procesamiento se realiza en paralelo, y no bloquea la ejecución del proceso principal.