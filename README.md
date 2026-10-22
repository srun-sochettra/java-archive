# Java Archive

**Console projects and experiments from learning Java, OOP, JDBC and file I/O.**

A coursework collection by **Srun Sochettra**, studying Information Technology at the National University of Management. The projects progress from in-memory record management to an MVC employee application backed by PostgreSQL, alongside small text, binary and serialization exercises.

This is an archive of independent learning projects, not one application or a shared build.

## Explore the projects

| Project | Focus | Data storage |
| --- | --- | --- |
| [Student management](assigments/StudentManagent/src/Main.java) | Student records, collections and input validation | In memory |
| [Hotel management](assignments/HotelManagement/src/HotelManagement.java) | Console room-management exercise | In memory |
| [Library management](LibraryManagement/src/Main.java) | Books, authors, borrowing/returns and formatted tables | In memory |
| [Employee MVC](MVCTest/src/org/example/Main.java) | Controller/view separation, DAO interfaces and JDBC operations | PostgreSQL |
| [File I/O exercises](testing/test/src/) | Text, binary, random-access files and object serialization | Local files |

The original directory spellings, including `assigments` and `StudentManagent`, are preserved so links match the source. The bundled `text-table-formatter-1.1.2/` tree contains third-party documentation and examples; it is not presented as original coursework.

## Running a project

### Choose one module

Open the relevant project directory in IntelliJ IDEA, select a JDK and inspect its source root and dependencies. Some checked-in project settings select **JDK 21**. That is the best source-backed starting point here, not a verified minimum for every exercise.

Do not compile all source folders together: multiple projects define default-package classes such as Main and Student. Each project needs its own output directory and classpath.

There is no root Maven or Gradle build in the supplied export. The Ant build under the table formatter's examples belongs to that bundled dependency, not the coursework collection.

### Standard-library starting point

The student exercise imports only Java standard-library classes. As a suggested command-line route, run these commands from the repository root with a suitable JDK:

```sh
javac -d build/student assigments/StudentManagent/src/Main.java
java -cp build/student Main
```

These commands were not executed during this refresh. They target only that independent source file, not the entire archive.

### Table-formatting dependencies

Library management imports `org.nocrala.tools.texttablefmt`. Its IntelliJ module references `LibraryManagement/lib/text-table-formatter-1.2.4.jar`. The MVC module references the sibling formatter 1.1.2 JAR and a project-level PostgreSQL JDBC library named `postgresql-42.7.10`.

Those are configuration references, not proof that the required binaries are present or correctly attached in your checkout. The Repomix text export does not include JAR contents. Inspect the original repository and configure the actual classpaths before running dependent projects. Do not assume the two formatter versions are interchangeable without checking.

### Employee MVC and PostgreSQL

[Connect.java](MVCTest/src/org/example/model/Connect.java) uses a local PostgreSQL connection and hard-coded credentials. Treat the password as exposed if it has ever been used for a real database; rotate it and replace the configuration before connecting to anything important. This overlay does not alter source or credentials.

The DAO expects an `employee` table with `id`, `name`, `age` and `department` fields, including an ID returned by insertion. No schema migration or database provisioning script is included in the supplied export. Review the DAO and create an isolated development database deliberately; do not assume an arbitrary existing database matches it.

The MVC entry point is `org.example.Main`. The JDBC driver and database must be configured separately from the table formatter.

### File I/O experiments

Run individual examples with a deliberate working directory. Several writers create or overwrite relative files, and some path exercises contain machine-specific absolute Windows paths. Serialization examples use `student.ser`; binary examples use several different filenames. Read the selected example before running it, and do not deserialize files from untrusted sources.

## What this archive demonstrates

- Java classes, encapsulation, collections and console input.
- Validation and menu-driven interactions.
- A library domain model with authors, books and borrowing state.
- MVC/DAO separation and JDBC parameter binding for employee mutations.
- Text/binary streams, random-access files and Java serialization.

These are learning implementations. No production-readiness, security audit, performance result or automated test coverage is claimed.

## Known boundaries

- In-memory project records do not survive application exit.
- Dependency setup is manual and spread across IntelliJ module files.
- The JDBC connection helper prints errors and returns null on connection failure; callers can fail beyond the intended SQL exception handling.
- Some I/O examples depend on local files or machine-specific paths.
- No automated assertion-based test suite or unified verification command was found in the supplied export. The `testing` folder contains executable examples, not evidence of passing tests.

See [implementation notes](docs/implementation-notes.md), [contributing](CONTRIBUTING.md) and [security guidance](SECURITY.md).

## Licence

No root project licence is included in the supplied export. This refresh does not assign one. Bundled third-party formatter material retains its own notices; those do not automatically license the original coursework. Confirm code and dependency permissions separately before redistribution.
