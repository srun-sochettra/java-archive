# Implementation notes

## Independent projects

Student and library management each define their own default-package Main class and related models. The I/O sandbox also has a Main and Student. These source roots are independent, not a single package hierarchy.

Student management uses collections and console validation. Hotel management is a console room-management exercise. Library management models authors/books and implements adding, listing, borrowing and returning books with formatted tables. These projects retain their state in memory rather than sharing the MVC database.

## MVC and JDBC

MVCTest separates EmployeeController, EmployeeView, the Employee model, an EmployeeDAO interface and EmployeeDAOImpl. Mutating DAO operations use prepared statements. The read-all query is static SQL. This is evidence of JDBC practice, not a claim of comprehensive validation, transactional design or security.

The DAO references an employee table with id, name, age and department. No DDL or migration was supplied. Connect embeds a local database URL and credentials and returns null on SQLException. DAO try-with-resources blocks manage JDBC objects, but dereferencing a failed null connection is a separate failure path.

## Dependency configuration

LibraryManagement's module points to formatter 1.2.4 under its local lib directory. MVCTest points to formatter 1.1.2 in the sibling distribution and a project-level PostgreSQL JDBC library. Binary availability and compatibility were not verified from the text export.

Some IDE settings select JDK 21; inherited JDK entries elsewhere do not establish a universal minimum. No root Maven/Gradle configuration was supplied.

## I/O and third-party material

The sandbox includes text/binary streams, random-access examples and serialization. Relative paths depend on the working directory; absolute path examples need local adaptation. Read and write examples do not all share the same filenames.

The bundled formatter includes generated API documentation and example source. It should remain attributed as third-party material, not counted as original application work. Its example build is not a root coursework build.

## Verification boundary

Reviewed the original README, coursework Java sources, relevant module/IDE configuration and file inventory. Bundled third-party Javadocs/examples were inventoried rather than exhaustively audited. JAR contents were not inspected.

No Java compilation, application execution, database connection, file-writing example or automated behavioural test was run. Documentation link and archive checks do not establish application correctness.
