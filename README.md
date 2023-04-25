# DataCleaningPySpark
BillboardHot100 data set. Databricks. Pyspark. SparkSQL.

Limpieza de datos, transformación de data frames optimizando su contenido para posterior uso en analítica.

El origen de los datos es una base de datos de SQL Server traidos mediante un pipeline que creé en Azure Data Factory. Los archivos .csv fueron llevados a un contenedor en un datalake dentro de una carpeta llamada "rawdata"
En la primer notebook llamada "Billboard_raw_to_trusted", levanto los .csv alojados en el datalake, manipulo y transformo los datos utilizando Pyspark. Las tablas ya limpias y organizadas, fueron guardadas en formato parquet en un datalake dentro de una carpeta llamada "trusteddata".
En la segunda notebook llamada "Billboard_trusted_joins" mediante SparkSQL realizo los joins necesarios para poder trabajar con sus datos posteriormente en Microsoft Power BI. Los 2 tablones creados a partir de los joins, son guardados en una base de datos de SQL Server.

