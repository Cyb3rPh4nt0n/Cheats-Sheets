### Listar los metadatos de una imagen/archivo:
$ exiftool {File-or-Image}
### Listar todos los metadatos de una imagen/archivo:
$ exiftool -all {File-or-Image}
### Mostrar información de los metadatos:
$ exiftool info {File-or-Image}
### Exportar los metadatos a un archivo HTML:
$ exiftool -h {File-or-Image} > file.html
### Exportar los metadatos a formato CSV:
$ exiftool -csv {File-or-Image}
### Exportar los metadatos a formato JSON:
$ exiftool -json {File-or-Image}
### Modificar algún metadato:
$ exiftool -overwrite_original {Metadata}="{String}" {File-or-Image}
### Modificar todos los metadatos a valor NULL:
$ exiftool -all:all=NULL {File-or-Image}