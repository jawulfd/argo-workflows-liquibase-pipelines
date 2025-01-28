# Resources

This folder contains the resources, like service accounts, secrets configurations,...
which are required for a proper execution of argo workflows and events

### Argo Service accounts

The [operate-workflows-sa.yaml](operate-workflows-sa.yaml) file contains the service account required to trigger workflows
from argo events

The [executor-workflows-sa.yaml](executor-workflows-sa.yaml) file contains the service account required to execute pods, get logs
and update workflows task results

### JDBC Database Secret Configuration

The [jdbc-database-secret.yaml](jdbc-database-secret.yaml) file contains a sample yaml file to configure 
the kubernetes secret to be able to execute the tekton pipelines and connect to the target database

- [jdbc-postgresql-secret.yaml](jdbc-postgresql-secret.yaml) is a sample file for postgresql database
- [jdbc-mysql-secret.yaml](jdbc-mysql-secret.yaml) is a sample file for mysql database
