---
type: Project Guide
title: Pediatric Office Automation System
description: JavaFX desktop application with nurse, doctor, and patient views backed by SQLite.
resource: https://github.com/darshchaurasia/pediatric-office-system
tags:
- java
- javafx
- sqlite
- coursework
sources:
- resource: https://github.com/darshchaurasia/pediatric-office-system/blob/f9b3ccc25b4b2cbfd013d6ee30022b88f8556c81/.classpath
  title: .classpath
- resource: https://github.com/darshchaurasia/pediatric-office-system/blob/f9b3ccc25b4b2cbfd013d6ee30022b88f8556c81/src/ui/main.java
  title: src/ui/main.java
- resource: https://github.com/darshchaurasia/pediatric-office-system/blob/f9b3ccc25b4b2cbfd013d6ee30022b88f8556c81/src/db/DatabaseConnector.java
  title: src/db/DatabaseConnector.java
- resource: https://github.com/darshchaurasia/pediatric-office-system/blob/f9b3ccc25b4b2cbfd013d6ee30022b88f8556c81/src/util/module-info.java
  title: src/util/module-info.java
- resource: https://github.com/darshchaurasia/pediatric-office-system/blob/f9b3ccc25b4b2cbfd013d6ee30022b88f8556c81/README.md
  title: README.md
---

# Pediatric Office Automation System

A JavaFX desktop application with nurse, doctor, and patient portals. The application manages patient records, visits, prescriptions, allergies, immunizations, health issues, and messages through DAO classes backed by SQLite.

## Build requirements

- JDK 21, matching the checked-in Eclipse classpath.
- JavaFX 21 SDK, configured as the Eclipse user library `JavaFX21`.
- Eclipse with Java support and the JavaFX/e(fx)clipse container referenced by `.classpath`, or equivalent manually configured JavaFX libraries.
- The three checked-in dependencies in `lib/`: `sqlite-jdbc-3.45.2.0.jar`, `slf4j-api-2.0.12.jar`, and `slf4j-simple-2.0.12.jar`.

## Build and run from source

1. Import the repository as an existing Eclipse project.
2. Select JDK 21 and resolve the JavaFX classpath containers. Point `JavaFX21` at your installed SDK libraries.
3. Confirm `src/` is the source directory and `bin/` is the compiler output directory. Retain the JAR entries under `lib/`.
4. Use **Project > Clean**, then build the project. Compiled `.class` files are generated locally and are excluded from Git.
5. Run [src/ui/main.java](src/ui/main.java), whose fully qualified class name is `ui.main`, with JavaFX configured in the launch settings.
6. Set the working directory to the repository root so the relative SQLite path resolves to `database/th43.db`.

The entry screen opens nurse, doctor, and patient views. DB Browser for SQLite is optional for inspecting the database.

The module declaration currently lives at `src/util/module-info.java`; if your IDE requires a module descriptor at the source root, resolve that project-layout issue before using a modular build. This documentation update does not relocate source files. A JavaFX build and desktop launch have not been verified in this update.

## Repository map

| Path | Purpose |
| --- | --- |
| [src/ui/](src/ui/) | Application entry point and screens. |
| [src/model/](src/model/) | Patient and clinical record models. |
| [src/dao/](src/dao/) | Database access for records and messages. |
| [src/db/DatabaseConnector.java](src/db/DatabaseConnector.java) | SQLite connection using `jdbc:sqlite:database/th43.db`. |
| [src/util/](src/util/) | UI helper and module declaration. |
| [lib/](lib/) | JDBC and logging libraries required by the project. |
| [database/](database/) | Existing SQLite database. |
| [.classpath](.classpath) | Eclipse source, dependency, and output configuration. |

## Contributing

Bug reports, feature requests, and pull requests are welcome. Keep source changes separate from locally generated compiler output.

## Rights and contact

All rights are reserved under the existing project notice. Reproduction or distribution requires the owner's prior written permission.

Contact: darshchaurasia@gmail.com
