
# Reportico
Reportico Open Source PHP report Designer

Reportico PHP Reporting Tool. Runs against MySQL, PostgreSQL and other PDO enable databases - 
design reports, create report menus, configure criteria, graphs, grouping, drill-down, output in HTML, PDF, & CSV, expression handling, look and feel through CSS, data transformation.

## Features

- Interactive Report Designer
- Runs Against MySQL, PostreSQL, Informix, Oracle, SQL Server, SQLite
- Produce Criteria Entry Screens
- Out in HTML, PDF, CSV
- Graphs and Database Graphics
- Report Menu generation
- Groups to organize output with headers and trailers
- Expressions and Assignments to manupulate output data prior to reporting
- Inclusion of custom PHP code to allow complex manipulation of data prior to reporting
- Drilldown

## Install

Reportico is best installed via composer or zip downloads are available from the releases page https://github.com/reportico-web/reportico/releases

To install the latest stable version use the following composer command under a web folder

composer create-project reportico-web/reportico <optional-installation-folder>

This will create a reportico folder with the latest release and with your specified name.

To run your existing report projects against this release, you will need to generate new project and move the xml files in from the old projects. 

to get started see the quickstart guide :-
http://www.reportico.org/yii2/web/index.php/quickstart

or visit the Reportico Web Site
http://www.reportico.org

## Upgrading from 4.x to 6.x

See instructions here ..

http://reportico.org/site2/release-6.0.0-beta


## PHP 8.5 vendor patches (ADOdb / Reportico / XmlReader)

These diffs target a **composer-installed Reportico 8.1.0** tree with vendored ADOdb (MacPorts PHP 8.5). Use them for upstream reference or to re-apply on a deployment host after upgrades.

They address ADOdb `(integer)` → `(int)`, `ADODB_pdo::$_nestedSQL`, and `XmlReader` XML API changes.

Files in `patches/`:

- `patches/adodb-php85-compat.patch`
- `patches/reportico-php85-compat.patch`
- `patches/reportico-8.1.0-php85-compat.patch` — combined (ADODB + reportico-web) bundle

Example (adjust `-p` and paths to match your install root, e.g. `/opt/local/www/html/reports-reportico/reportico-8.1.0`):

```bash
patch -p1 -d /path/to/reportico-8.1.0 < patches/reportico-8.1.0-php85-compat.patch
```

Operational context (mounts, SSH, web paths) for the automation host lives in the sibling **ops-etl** repo: `../ops-etl` and `.cursor/rules/onprintshop-remote.mdc` there.

## Screenshots

![Criteria Page](/images/reportico_prepare.png?raw=true "Criteria Page")


![Edit Query Page](/images/reportico_sql.png?raw=true "Edit Query Page")


![Report Output Page](/images/reportico_output.png?raw=true "Report Output Page")
