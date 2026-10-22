# Repository refresh

## Identity

Keep **java-archive** as the slug and use **Java Archive** as the display title. It honestly describes a mixed collection of earlier projects and experiments without implying a single polished application.

Suggested description:

> Java coursework archive: console management projects, an MVC/JDBC employee app, and file I/O and serialization exercises.

Suggested topics: java, coursework, oop, jdbc, postgresql, mvc, console-application.

No GitHub settings, rename, commit or push was performed.

## Apply

Extract into the existing repository root. Replace README.md and add CONTRIBUTING.md, SECURITY.md and the two documents under docs/. Preserve source, third-party material, local files, IDE configuration and Git history. This is a documentation overlay, not a full repository archive.

## Editorial decisions

The README provides a project map and separates independent modules, in-memory examples and PostgreSQL-backed work. It replaces the unsupported universal JDK minimum with the checked-in JDK 21 configuration, explains differing formatter references and avoids pretending a database schema or root build exists.

The guides document exposed credentials and unsafe import/file-operation boundaries without copying secrets or changing code. No licence, screenshot, build result, dependency binary or database provisioning script was invented.

## Verification

Checked local links, source references, ZIP integrity and delivered text bytes. Selected source claims were checked against the supplied Java/configuration files. No compilation, database access, application run or behavioural tests were performed.

To revert, restore the previous README and remove the four added documents through version control. No runtime migration is involved.
