# Templates

This folder contains the workflows templates which are referenced in [liquibase-workflow.yaml](../workflows/liquibase-workflow.yaml)
and in [liquibase-rollback-workflow.yaml](../workflows/liquibase-rollback-workflow.yaml)

[Liquibase Workflows Templates](#Liquibase-Workflows-Templates)

[Liquibase Command Reference](#Liquibase-Command-Reference)

## Liquibase Workflows Templates

### Liquibase Rollback Templates

File [liquibase-update-templates.yaml](liquibase-update-templates.yaml) contains the base liquibase command parametrize so
it can be reutilized passing the rollback command to be executed

### Liquibase Tag Templates

File [liquibase-tag-templates.yaml](liquibase-tag-templates.yaml) contains the workflows templates for liquibase tag and
tag-exists commands

### Liquibase Update Templates

File [liquibase-update-templates.yaml](liquibase-update-templates.yaml) contains the base liquibase command parametrize so
it can be reutilized passing the update command to be executed

### Liquibase Utilities Templates

File [liquibase-utilities-templates.yaml](liquibase-utilities-templates.yaml) contains the workflows templates for commands:

- liquibase diff
- liquibase snapshot
- liquibase status
- liquibase validate

### Utilities Templates

File [utilities-templates.yaml](utilities-templates.yaml) contains utilities workflows templates like git-clone, which
are not part of liquibase commands

## Liquibase Command Reference

#### Liquibase diff

The diff command is typically used at the completion of a project to verify all expected changes are in the changelog or 
to detect drift between a model schema and a database's actual schema

Reference [Liquibase diff command](https://docs.liquibase.com/commands/inspection/diff.html)

#### Liquibase rollback

The rollback command is typically used to revert all changes that were made to the database after the tag you specify

Reference [Liquibase rollback command](https://docs.liquibase.com/commands/rollback/rollback.html)

#### Liquibase rollback-sql

The rollback-sql command is typically used to inspect the SQL Liquibase uses to revert changes associated with a tag you specify when you run the rollback command. 
It is best practice to use the rollback-sql command before running the rollback command to ensure that you eliminate any potential risks.

Reference [Liquibase rollback-sql command](https://docs.liquibase.com/commands/rollback/rollback-sql.html)

#### Liquibase snapshot

The snapshot command is typically used when you want to see changes in your target database or keep a record of your current database state.
You can use the output of snapshot with the diff and diff-changelog commands.

Reference [Liquibase snapshot command](https://docs.liquibase.com/commands/inspection/snapshot.html)

#### Liquibase status

The status command states the number of undeployed changesets. Running status lists all undeployed changesets. 
It also lists the id, author, and file path name for each undeployed changeset. The status command does not modify the database.

Reference [Liquibase status command](https://docs.liquibase.com/commands/change-tracking/status.html)

#### Liquibase tag

The tag command is typically used to mark the current database state, version, release, or any other information 
by adding the tag to the last row in the DATABASECHANGELOG table

Reference [Liquibase tag command](https://docs.liquibase.com/commands/utility/tag.html)

#### Liquibase tag-exists

The tag-exists command is typically used to identify whether the specified tag exists in the database or specifically in the DATABASECHANGELOG table

Reference [Liquibase tag-exists command](https://docs.liquibase.com/commands/utility/tag-exists.html)

#### Liquibase update

The update command deploys any changes that are in the changelog file and that have not been deployed to your database yet.

Reference [Liquibase update-testing-rollback command](https://docs.liquibase.com/commands/update/update.html)

#### Liquibase update-testing-rollback

update-testing-rollback tests rollback support by deploying all pending changesets to the database, executes a rollback sequentially 
for the equal number of changesets that were deployed, and then runs the update again deploying all changesets to the database.

Reference [Liquibase update-testing-rollback command](https://docs.liquibase.com/commands/update/update-testing-rollback.html)

#### Liquibase update-sql

The update-sql command outputs the expected SQL of an update operation so that you can evaluate it. 
The command does not automatically check SQL for correctness and does not anticipate database deployment errors resulting from malformed SQL

Reference [Liquibase update-sql command](https://docs.liquibase.com/commands/update/update-sql.html)

#### Liquibase validate

The validate command checks your changelog and identifies any possible errors with Liquibase syntax 
that may cause the update command to fail

The validate command only looks for possible errors in the changelog. It does not check for possible errors 
that might result from applying the changes to a specific database.

Reference [Liquibase validate command](https://docs.liquibase.com/commands/utility/validate.html)
