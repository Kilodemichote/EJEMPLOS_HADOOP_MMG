# EJEMPLOS_HADOOP_MMG
🧩 **Resolver Sudoku**

**Descargamos un script de ejemplo con MapReduce**

Vamos a usar un archivo `.jar `que ya trae las clases necesarias para ejecutar el algoritmo MapReduce para resolver un Sudoku.

Descarga el archivo desde este link:

👉 [hadoop-examples-0.20.205.0.jar](https://drive.google.com/file/d/1m6uSyzNCQV1617fmhQyW59sMQ2DYef2E/view?usp=sharing)

Cuando lo tengas, muévelo a la misma carpeta donde está el repositorio `docker-hadoop`.

**Archivo .txt para procesar**

También necesitamos el archivo con el Sudoku que vamos a resolver. Descárgalo desde aquí:
👉 [puzzle1.dta](https://2935835229-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FVMoUbnSkOwuxDBZq5HyK%2Fuploads%2FJAygXsvKPKvUwThTxh7f%2Fpuzzle1.dta?alt=media&token=8291160e-3730-4125-b34d-12517d084419)

Cuando lo descargues, muévelo también a la carpeta del repo `docker-hadoop`.

**Copiar los archivos` .jar` y` .txt` al contenedor**

Para meter el` .jar `al contenedor, ejecuta:
`docker cp hadoop-examples-0.20.205.0.jar namenode:/tmp`

Y haz lo mismo con el archivo del Sudoku:
`docker cp puzzle1.dta namenode:/tmp`

🧠 **Ejecutar MapReduce**

Primero, entra al contenedor` namenode`:
`docker exec -it namenode bash`

Luego ve a la carpeta `/tmp`:
`cd /tmp`

Ahora ejecuta el algoritmo:
`hadoop jar hadoop-examples-0.20.205.0.jar sudoku puzzle1.dta`

📄 **Ver los resultados**

Si quieres guardar la solución en un archivo` .txt`, ejecuta:
`hadoop jar hadoop-examples-0.20.205.0.jar sudoku puzzle1.dta > solucion_puzzle1.txt`

Después sal del contenedor:
`exit`

Y por último, copia el archivo de vuelta a tu máquina:
`docker cp namenode:/tmp/solucion_puzzle1.txt .`

¡Listo! Ahora tienes la solución del Sudoku en tu carpeta de `docker-hadoop`.
