# Contributing

Keep this archive understandable as independent coursework projects. Prefer a focused correction or explanatory example over converting every module to a new framework or build system.

## Before changing code

Identify the affected module, its entry point, JDK and dependencies. Do not compile unrelated default-package projects into one output directory. Preserve directory spellings unless a deliberate move updates all references and IDE settings.

Use synthetic records and an isolated development database. Do not commit database passwords, private local paths, personal records or generated binary/serialized data.

## Verification

There is no unified build or automated test suite in the supplied export. Report the exact module, JDK, classpath, commands and scenarios actually checked. A compilation result is not evidence that menus, database writes or file operations work.

Useful scenarios include invalid input, missing records, duplicate identifiers where relevant, borrow/return transitions, failed database connections and missing/unwritable files. For non-trivial fixes, add the smallest appropriate regression check without introducing a repository-wide framework solely for a minor change.

Review writer paths before executing file I/O examples. Do not run deserialization against untrusted input. For database changes, describe schema assumptions and verify against a disposable database rather than inventing a migration contract.

## Pull requests

Explain the learning objective or defect, focused change, checks performed and remaining gaps. Keep unrelated formatting, dependency changes and generated files separate. Follow [SECURITY.md](SECURITY.md) for sensitive reports.
