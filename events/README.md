# Events

This folder contains the resources to configure argo eventbus, event source and sensor
in order to execute workflows in response to GitHub webhooks

### Argo Eventbus

The EventBus acts as the transport layer of Argo-Events by connecting the EventSources and Sensors.
It is a namespaced object as it is required in each namespace where EventSources and Sensors are deployed

In the file [eventbus.yaml](eventbus.yaml), an EventBus with jetstream configuration can be found.
In order to check available versions or increase the compatibility with new versions of jetstream, the controller-config.ymal
can be found inside the config map argo-events-controller-manager

Reference [Argo Event Bus](https://argoproj.github.io/argo-events/concepts/eventbus/)

### Argo Event Source

An EventSource defines the configurations required to consume events from external sources.

In the file [github-event-source.yaml](github-event-source.yaml), an event source configuration for GitHub can be found
with the webhook configuration and webhook secret

Reference [Argo Event Source](https://argoproj.github.io/argo-events/concepts/event_source/)

### Argo Sensor

Sensor defines a set of event dependencies (inputs) and triggers (outputs). 
It listens to events on the eventbus and acts as an event dependency manager to resolve and execute the triggers.

In the file [github-sensor.yaml](github-sensor.yaml), a sensor configuration for GitHub events which triggers liquibase workflows
can be found. It processes the payload to get the clone url and git revision to clone, and also generate a dynamic name using the commit id

Reference [Argo Sensor](https://argoproj.github.io/argo-events/concepts/sensor/)
