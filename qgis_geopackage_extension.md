# GeoPackage 1.0 Extension

**DRAFT**

Extension follows template from Annex I of the OGC [GeoPackage 1.0 Specification](http://www.geopackage.org/).

## Extension Title

**QGIS map styling information**

## Introduction

Store QGIS projects with their resources like images in print templates in a GeoPackage file.

## Extension Author

Pirmin Kalberer, author_name `pka`.

## Extension Name or Template

`qgis`

## Extension Type

Extension of Existing Requirement in Clause 2.

## Applicability

This extension applies to additional tables `qgis_projects`, `qgis_resources` 
and `layer_styles`.

## Scope

Read-write

## Requirements

Definition of extension and interdependencies with other extensions if
any.

### GeoPackage

#### Extension tables

An Extended GeoPackage with QGIS support MAY contain the following tables or views:

**qgis_projects**

| Column | type | Desctiption |
| --- | --- | --- | --- |
| name | text NOT NULL UNIQUE | Project name (file name) |
| xml | text NOT NULL | Project file content (.qgs) in XML format |

**qgis_resources**

| Column | type | Desctiption |
| --- | --- | --- | --- |
| name | text NOT NULL UNIQUE | Name of resource (file name) |
| mime_type | text NOT NULL | [Mime type](http://www.iana.org/assignments/media-types/media-types.xhtml) of resource  (`image/png`, `image/svg+xml`, ...)
| content | blob NOT NULL | Binary content of resource |

**layer_styles**

QGIS style library. Used styles are included in project XML.

| Column | type | Desctiption |
| --- | --- | --- | --- |
| id | INTEGER | PRIMARY KEY |
| f_table_catalog | varchar(256) | |
| f_table_schema | varchar(256) | |
| f_table_name | varchar(256) | |
| f_geometry_column | varchar(256) | |
| styleName | varchar(30) | |
| styleQML | text | |
| styleSLD | text | |
| useAsDefault | boolean | |
| description | text | |
| owner | varchar(30) | |
| ui | text | |
| update_time | timestamp | |


Additional metadata (authorship, licensing, ...) can be stored in the
[GeoPackage metadata tables](http://www.geopackage.org/spec/#extension_metadata).

### GeoPackage SQLite Configuration

None

### GeoPackage SQLite Extension

None
