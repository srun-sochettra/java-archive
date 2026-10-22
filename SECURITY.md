# Security guidance

This is a collection of local coursework examples, not a hardened service. No supported-release programme, response deadline or security audit is established here.

## Database credentials

MVCTest/src/org/example/model/Connect.java contains hard-coded database credentials. Their values are deliberately not reproduced in this documentation. Treat them as exposed if used anywhere real, rotate affected credentials and review shared history/exports. Deleting a current value does not remove historical copies.

Use an isolated development database with limited permissions. The current code does not load environment variables; adding an environment file alone would not change it. Configuration externalisation requires a separate source change and verification.

The connection helper returns null after printing a connection error. DAO callers assume a usable connection, so error handling needs review. This documentation does not fix that behaviour.

## Local files and serialization

Writer examples can overwrite files relative to the process working directory. Some path exercises include machine-specific absolute paths. Inspect and adapt paths before execution; do not run against important documents.

DeserializeExample uses ObjectInputStream.readObject without a configured input filter in the supplied source. Do not deserialize untrusted files. A local learning example is not a safe import service.

Avoid committing personal records, database dumps, generated binary files or sensitive diagnostic output. Review existing tracked content separately; this overlay does not remove it.

## Reporting

For ordinary defects, provide the module, environment and minimal reproduction with synthetic data. For sensitive concerns, use a verified private maintainer channel if available, or request one without posting secrets or exploit details. No dedicated security mailbox or enabled private-reporting feature is confirmed by the supplied repository.

These are source observations, not executed attacks or a complete vulnerability inventory.
