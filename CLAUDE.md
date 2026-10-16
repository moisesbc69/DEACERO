# Proyecto: Gobierno de datos ARE 2.0 (DeAcero)

## Contexto
- ARE = Sistema de Comercio Administrado (antidumping, Connums, Estudios
  de Revisiones Administrativas para DoC/CBP). Auditado por entidades externas.
- Legado: .NET + WTools sobre SQL Server 2008 (DEAOFINET06).
- Nuevo: GCP. Pipelines dbt -> mart_are (Aceros/Alambres/USA) y
  UDN_Deacero_Solutions -> mart_comercio_administrado (Ingetek).
- Continúo el trabajo de Orquídea Solís (DGD-74, DGD-99, DGD-100).

## Objetivo actual
- Linaje de datos de los reportes de ARE.
- Insumo para: matriz cruzada KPIs vs reportes, matriz maestra de campos,
  plan de certificación de datos.
- Prioridad: Mart de Fletes (pendiente principal de Fase 1).

## Fuentes de datos
- BigQuery: dfor-prj-dev.deacero_sql_objects (objetos SQL del legado).
- Acceso: solo lectura (bigquery.jobs.create, tables.getData, tables.list).

## Reglas de trabajo
- SOLO consultas de lectura (SELECT). Nunca DDL/DML.
- Usar LIMIT al explorar; revisar el costo con --dry_run antes de
  consultas grandes.
- Guardar las consultas útiles en /queries y los resultados en /resultados.
- Documentar hallazgos en /docs, en español.
