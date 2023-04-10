---
description: How-to host a static website within Google Cloud Storage bucket
---

# Host a static site in GCS

{% embed url="https://cloud.google.com/storage/docs/hosting-static-website" %}

Once the bucket has been provisioned such above link explains, from GCP SDK:

1. SDK account initialization and so on:\
   `gcloud init`
2. After having the SDK running, we need to configure Hugo appending the following block to `config.toml` file

```toml
[deployment]
# El tipo de implementación se establece en gcs
# Esto indicará a Hugo que el destino es Google Cloud Storage
# GCP se debe haber autenticado previamente en su máquina
# para que Hugo pueda acceder a sus proyectos
# Por ejemplo, use `gcloud auth login` para autenticarse
type = "gcs"

# La región donde se ubicará el bucket de Google Cloud Storage
region = "europe-southwest1"

# El nombre del bucket de Google Cloud Storage donde se cargará el sitio web
bucket = "preventa.tech"

# La ruta dentro del bucket donde se cargará el sitio web
# En este ejemplo, se carga el sitio web en la raíz del bucket
path = "/"

# Si establece el valor en true, Hugo eliminará todos los archivos existentes en el bucket antes de cargar los nuevos
# Tenga cuidado al usar esto ya que se eliminarán todos los archivos en el bucket especificado
delete = false

# Si establece el valor en true, se habilitará la compresión gzip en los archivos antes de cargarlos en el bucket
# Esto puede mejorar el tiempo de carga del sitio web y reducir los costos de almacenamiento en GCP
gzip = false

# Si establece el valor en true, Hugo actualizará automáticamente las URL de los enlaces internos para que se ajusten a la URL del sitio en GCP
canonifyurls = false

```

3. From here we need to setup de Cloud Load Balancer with a SSL Certificate
