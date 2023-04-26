# DataCleaningPySpark
BillboardHot100 data set. Databricks. Pyspark. SparkSQL.

Limpieza de datos, transformación de data frames optimizando su contenido para posterior uso en analítica.

El origen de los datos es una base de datos de SQL Server traidos mediante un pipeline que creé en Azure Data Factory: A partir de una búsqueda, consigo el esquema de la base de datos y mediante una query de SQL, solo selecciono las tablas necesarias. A través de un ForEach, con un copy los archivos .csv fueron llevados a un contenedor en un datalake (Azure Data Lake Gen2) dentro de una carpeta llamada "rawdata" y a continuación realizo las modificaciones necesarias (éstos procesos son descriptos en el próximo párrafo) insertando las dos notebooks de Databricks dentro del ForEach.

Los archivos .csv fueron llevados a un contenedor en un datalake (Azure Data Lake Gen2) dentro de una carpeta llamada "rawdata"
En la primer notebook usada en Azure Databricks llamada "Billboard_raw_to_trusted", levanto los .csv alojados en el datalake, manipulo y transformo los datos utilizando Pyspark: casteo/eliminación de columnas, eliminación de registros duplicados y/o nulos, etc. Las tablas ya limpias y organizadas, fueron guardadas en formato parquet en un datalake (Azure Data Lake Gen2) dentro de una carpeta llamada "trusteddata".
En la segunda notebook usada en Azure Databricks llamada "Billboard_trusted_joins", mediante SparkSQL realizo los joins necesarios para poder trabajar con sus datos posteriormente en Microsoft Power BI. Los 2 tablones creados a partir de los joins, son guardados en una base de datos de SQL Server.

