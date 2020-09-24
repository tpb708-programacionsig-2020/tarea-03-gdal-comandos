# TPB708 Programación de aplicaciones en sistemas de información geográfica
## Tarea 03

### Fecha de entrega y entregables
La fecha y hora límite para la entrega es **jueves 1 de octubre de 2020 a las 5:00 p.m.**

Debe enviarle al profesor por correo electrónico un archivo de texto con los comandos resultantes.

**ESTA TAREA ES PARA REALIZARSE EN FORMA INDIVIDUAL**.

### Objetivos
Aplicar [utilitarios de línea de comandos de GDAL](https://gdal.org/programs/).

### Desarrollo
Se recomienda ejecutar estos comandos en un ambiente Conda que contenga el paquete GDAL.

0. Descargue la capa de cantones del Sistema Nacional de Información Territorial (SNIT, [https://www.snitcr.go.cr/](https://www.snitcr.go.cr/)) en un archivo GeoJSON llamado "cantones.geojson":  
```shell
# Descarga de la capa de cantones del IGN en el SNIT (https://www.snitcr.go.cr/)
ogr2ogr -f GeoJSON -s_srs EPSG:5367 -t_srs EPSG:4326 -makevalid cantones.geojson WFS:"http://geos.snitcr.go.cr/be/IGN_5/wfs" "IGN_5:limitecantonal_5k"

# Información sobre la capa descargada
ogrinfo -al -so cantones.geojson
```

Utilice el comando ```ogr2ogr``` y el archivo "cantones.geojson" para realizar los siguientes ejercicios. El valor porcentual de cada uno se muestra entre paréntesis.

1. (25%) Extraiga en un shapefile los cantones de la provincia de Heredia con área menor o igual que 20 km2.
2. (25%) Extraiga en un archivo GeoPackage los campos de provincia, cantón y área de los cantones de la provincia de San José con área menor o igual que 20 km2.
3. (25%) Extraiga en un archivo KML los campos de provincia, cantón y área de los cantones con área menor o igual que 20 km2 de las provincia de San José o de Heredia.
4. (25%) Extraiga en un archivo GeoJSON los campos de provincia, cantón y área de los cantones con área menor o igual que 20 km2 de la provincia de San José o con área mayor o igual que 2000 km2 de la provincia de Limón.
