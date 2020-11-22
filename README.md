# Scrapper-senado
Web scrapper para conseguir todos los resultados de las votaciones del senado en Chile.

### Importante
- Los archivos que estan subidos aqui tienen los datos hasta (21/11/2020), fecha cuando lo corri por ultima vez
- Esto fue hecho como un proyecto de prueba, cosas importantes que agregaria si fuera a usar los datos
  - [ ] Guardar mejor los archivos csv
    - [ ] Crear un diagrama de entidad relacion
    - [ ] Guardar en csv (o alguna base de datos) los datos normalizados
  - [ ] Agregar campos importantes (.json y .csv)
    - [ ] Parsear fechas, numeros de sesiones y votos
    - [ ] Agregar campos como temas de votaciones 
  

## Tecnologias
- Python
  - `Requests` (Para conseguir la informacion)
  - `beautiful soup` (Para parsear html)
  - `pandas` (Para guardar como .csv)
  - `json` (Para guardar .json)
  - `jupyter notebook` (Para desarrollo)
  
  
## http://senado.cl/
 
- https://www.senado.cl/appsenado/index.php?mo=sesionessala&ac=votacionSala&legiini=361&legiid=491
- Legislaturas, sesiones y votaciones
  - Cada legislatura
    - Tiene varias sesiones (aprox 100)
    - Cada una de esas sesiones tiene 0 o mas votaciones
    

## Como funciona
- Una clase para cada entidad
  - `Legislatura`, `Sesion`, `Votacion`
- Primero obtenemos todas las legislaturas disponibles, desde el select principal
- Luego por cada una de estas legislaturas, cargamos su pagina base
  - Leemos el select para ver todas las sesiones
  - Por cada sesion entramos a cada votacion
  
## Encoding resultados
- 1: Si
- 2: No
- 3: Abstencion
- 4: Pareo
- -1: No disponible (En caso de que un senador no haya participado de una votacion, por ahora solo disponible en csv)


