'Big Data' is a catch-all term for data that won't fit the usual containers.

# Big Data

## Graph schema

Big Data often uses graph schema to organise and structure data within a fact-based model.

Graph schema uses **graph** data structures consisting of **nodes and edges** to graphically represent the structure of a dataset.
Nodes in a graph represent entities and can contain the properties of an entity.

Edges are used to represent relationships between entities and are labelled with a brief description of the relationship.

Graph schema can be represented as a diagram consisting of circles as entities with arrows representing the edges between them.
Each circle contains the name of the entity and the properties it contains, while each arrow is labelled with a description of the
relation.

Timestamps are rarely included in graph schema diagrans, you should assume that each node represents the most up-to-date information.

Another method of representing graph schema is to simply have the name of an entity in a circle, with properties linked to it via
a dashed line. The dashed lines do not represent relationships, they simply show that the property belongs to that entity.
