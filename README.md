# Parking discovery service

Maintains the geographic search projection used to find parking spaces.

## Responsibilities

- Updates its read model from supply and reservation events.
- Searches by location and other requested criteria; results are informational, not a final availability guarantee.

## Technology

TypeScript, NestJS, PostGIS, RabbitMQ.

## C4 architecture

The diagram is a C4 **container view** focused on this repository and its relevant neighbors. It is generated from [Structurizr DSL](docs/architecture/workspace.dsl) using default styles, without custom colors. Arrows show the direction of an interaction; the full model also records message flows.

![C4 container view: Parking discovery service](docs/architecture/containers.svg)

To inspect or regenerate the diagram, open `docs/architecture/workspace.dsl` in Structurizr. With the Structurizr CLI and Graphviz installed:

```sh
structurizr.sh validate -workspace docs/architecture/workspace.dsl
mkdir -p /tmp/parklink-diagram
structurizr.sh export -workspace docs/architecture/workspace.dsl -format dot -output /tmp/parklink-diagram
dot -Tsvg /tmp/parklink-diagram/structurizr-Containers.dot -o docs/architecture/containers.svg
```

## Build in the integrated workspace

```sh
npm ci
npm run build:shared
npm run build -w @parklink/parking-discovery-service
```

## Repository boundary

This repository is a snapshot of `services/parking-discovery-service` from [parklink-platform](https://github.com/1ASI0728-2620-16363-ParkLink/parklink-platform). Use the integrated workspace for the root npm configuration, shared dependencies, Docker build context, tests and local infrastructure. The repositories do not automatically synchronize.
