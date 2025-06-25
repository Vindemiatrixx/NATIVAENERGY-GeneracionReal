# Sobre la obtención de lo tsv:

- Obtener los tsv por el link : https://www.coordinador.cl/operacion/graficos/operacion-real/generacion-real/
- Este link al final contiene "generacion real horaria por central"
- Dentro de esta sección seleccionar descargar por UNIDAD, escoger la fecha y el formato en tsv.

# TSV:

- El tsv descargado debe quedar guardarse o moverse al directorio data/
- El nombre da un poco lo mismo, porque en el código debe modificarse el nombre del archivo a operar.

# Ejecución del código:

## modificar.ipynb:

- Este es el archivo principal y el único a usar.
- Se debe cambiar el nombre del archivo, archivo que debe estar en la carpeta data/
```python
archivo = "" # <- Aquí va el nombre del archivo, por ejemplo "2025-6"
df = pd.read_csv(f"data/{archivo}.tsv", sep='\t')
```
- Esto generará una carpeta con el mismo nombre que el archivo de entrada, digamos 2025-06/ como ejemplo.

# Sobre la data generada:

- El programa genera un archivo .parquet para cada día, listo para ser cargado al datalake en la ruta Prueba/Generacion_Real/data/año/mes/

# Cargar la data:

- Para cargar los archivos, por ahora se debe hacer manualmente, por lo que es necesario que la persona que lo realice tenga acceso al datalake.
- Se debe crear la carpeta año/ si es que no está creada y dentro de esta carpeta la carpeta mes/ si no está creada.
- Una vez creados los dos directorios, dentro del directorio mes/ se debe cargar todos los archivos .parquet correspondientes.

# Actualizar la tabla:

- Dentro de las pipelines de generacion real se debe ejecutar la pipeline de: "Merge_gen_real".
- Esperar a que termine sin errores y listo, la tabla tendrá los datos.

# Sobre ignore.ipynb

- Por ahora ignorar, es algo que no recuerdo para que lo tengo pero si no lo he borrado es porque debe tener algo que me sirve.
- No sirve para nada por ahora y tampoco en el futuro para esta implementación.s