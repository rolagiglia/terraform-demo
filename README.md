# Terraform Demo

Este proyecto es un demo de Terraform que provisiona recursos básicos en Google Cloud Platform (GCP). Es ideal para aprender los fundamentos de Infrastructure as Code con Terraform y GCP.

## Descripción

El proyecto crea los siguientes recursos en GCP:

- **Bucket de Google Cloud Storage**: Un bucket con una regla de lifecycle que aborta uploads multiparte incompletos después de 1 día.
- **Dataset de BigQuery**: Un dataset vacío para almacenar datos en BigQuery.

## Requisitos Previos

Antes de ejecutar este proyecto, asegúrate de tener:

- [Terraform](https://www.terraform.io/downloads.html) instalado (versión 1.0 o superior).
- Una cuenta de Google Cloud Platform (GCP) con permisos para crear buckets de Storage y datasets de BigQuery.
- Credenciales de servicio de GCP en formato JSON. Descárgalas desde la consola de GCP y colócalas en `keys/my-creds.json`.

## Instalación

1. Clona este repositorio:
   ```bash
   git clone https://github.com/tu-usuario/terrademo.git
   cd terrademo
   ```

2. Configura tus credenciales: Coloca tu archivo de credenciales JSON en `keys/my-creds.json`.

3. Revisa y actualiza las variables en `variables.tf` si es necesario (por ejemplo, el nombre del proyecto, región, etc.).

## Uso

1. Inicializa Terraform:
   ```bash
   terraform init
   ```

2. Revisa el plan de ejecución:
   ```bash
   terraform plan
   ```

3. Aplica los cambios:
   ```bash
   terraform apply
   ```

4. Para destruir los recursos creados:
   ```bash
   terraform destroy
   ```

## Variables

- `credentials`: Ruta al archivo de credenciales JSON (por defecto: `./keys/my-creds.json`).
- `project`: ID del proyecto de GCP.
- `region`: Región de GCP (por defecto: `us-central1`).
- `location`: Ubicación del bucket (por defecto: `US`).
- `bq_dataset_name`: Nombre del dataset de BigQuery.
- `gcs_bucket_name`: Nombre del bucket de Storage (debe ser único globalmente).

## Notas

- Este demo crea recursos que pueden generar costos en GCP. Asegúrate de destruirlos después de probar.
- El bucket tiene `force_destroy = true`, lo que permite eliminarlo incluso si contiene objetos.
- Asegúrate de que tu cuenta de GCP tenga los permisos necesarios (roles como `Storage Admin` y `BigQuery Admin`).

## Contribución

Si deseas contribuir, abre un issue o envía un pull request.

## Licencia

Este proyecto está bajo la Licencia MIT.