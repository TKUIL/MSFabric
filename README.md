# MS Fabric Pipelines and Notebooks

This repository showcases a collection of pipelines and Jupyter notebooks developed for data engineering and processing tasks using Microsoft Fabric. These artifacts represent structured workflows and utility functions aimed at efficient data ingestion, transformation, and storage.

---

## Table of Contents

- [Overview](#overview)
- [Artifacts](#artifacts)
  - [Pipelines](#pipelines)
    - [pl_gold_f1_dataset_load.json](#pl_gold_f1_dataset_loadjson)
    - [pl_ingestion_source.json](#pl_ingestion_sourcejson)
  - [Notebooks](#notebooks)
    - [nb_metadata.ipynb](#nb_metadataipynb)
    - [nb_functions_and_classes.ipynb](#nb_functions_and_classesipynb)
    - [nb_main.ipynb](#nb_mainipynb)
- [Highlights](#highlights)
- [Notes on Implementation](#notes-on-implementation)
- [Acknowledgments](#acknowledgments)

---

## Overview

The resources in this repository include:
- **Pipelines**: Workflows designed in JSON format for use in MS Fabric, automating processes such as metadata lookup, data ingestion, and transformations across data layers (bronze, silver, gold).
- **Jupyter Notebooks**: Supplementary code snippets and utilities used to process data and facilitate complex tasks within the pipeline workflows.

These artifacts are designed primarily for showcasing functionality and implementation style. They are not intended for direct reuse or deployment without additional configuration.

---

## Artifacts

### Pipelines

#### pl_gold_f1_dataset_load.json
- **Purpose**: Automates the loading and transformation of data from source to bronze and silver layers, culminating in a processed gold dataset layer.
- **Key Activities**:
  - Metadata lookup for dynamic data processing.
  - Conditional workflows for handling entities (e.g., merging or rebuilding datasets).
  - Loading and transforming datasets between lakehouses and data warehouses.
- **Parameters**:
  - `source_id` (int): Identifier for the data source. Default: `2`.
- **Highlights**:
  - Uses SQL pivot operations for dynamic parameter processing.
  - Supports Parquet-based storage for efficient data handling.

#### pl_ingestion_source.json
- **Purpose**: Facilitates data ingestion from REST APIs, storing raw data in the bronze layer for further processing.
- **Key Activities**:
  - Dynamic metadata-driven workflows for API data ingestion.
  - JSON-based storage for raw API responses.
  - Supports conditional branching for handling `merge` and `rebuild` operations.
- **Parameters**:
  - `source_id` (int): Identifier for the API source. Default: `1`.
- **Highlights**:
  - Incorporates pagination rules for API data fetching.
  - Designed to integrate seamlessly with downstream processing pipelines.

### Notebooks

#### nb_metadata.ipynb
- **Purpose**: Contains utility functions for extracting and processing metadata, used within pipelines to drive dynamic workflows.
- **Highlights**:
  - Prepares metadata-driven SQL queries.
  - Facilitates dynamic schema handling.

#### nb_functions_and_classes.ipynb
- **Purpose**: Implements reusable functions and classes for data transformation, validation, and utility operations.
- **Highlights**:
  - Includes helper functions for string manipulation and logging.
  - Modular design for easy integration into larger workflows.

#### nb_main.ipynb
- **Purpose**: Serves as the main execution notebook, integrating metadata functions and driving end-to-end workflows for dataset processing.
- **Highlights**:
  - Combines all supporting utilities to execute complete workflows.
  - Provides examples of parameter-driven execution.

---

## Highlights

- **Dynamic Pipelines**: Leverages metadata-driven configurations for scalability and adaptability in handling diverse data sources and entities.
- **Efficient Data Handling**: Utilizes Parquet and JSON storage formats for optimized data storage and retrieval.
- **Reusable Utilities**: Modular notebooks enable streamlined execution and debugging of individual components or entire workflows.

---

## Notes on Implementation

1. **Placeholders**:
   The JSON pipelines include placeholders (e.g., `{{workspaceId}}`, `{{endpoint}}`) to prevent exposure of sensitive information. These placeholders represent environment-specific configurations and must be replaced for execution.

2. **Structure**:
   The pipelines and notebooks are designed with separation of concerns, ensuring modularity and maintainability.

3. **Security**:
   Sensitive details such as connection strings and workspace IDs have been abstracted or omitted to maintain data security and privacy.

---
