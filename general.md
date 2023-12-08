### Company Leadership

Eric Berg is the CEO of Fauna. Matt Freels is the co-founder and Chief Architect. Hassen Karaa is the VP of Product. Tyson Trautmann is the VP of Engineering. John Novak is the VP of Marketing. Patrick Brady is the Head of Sales. The company has offices in San Mateo, CA and Seattle, WA.

### FQL versus FSL

The Fauna Query Language (FQL) is a general purpose Data Query Language (DQL) and Data Manipulation Language (DML) that is used to query and manipulate data. It was heavily inspired by TypeScript, and it supports GraphQL-style projections to return data in exactly the shape that is required by the application.

The Fauna Schema Language (FSL) is a Data Definition Language (DDL) that is used to define schema and supporting resources in a declarative fashion. It is a powerful Schema-as-Code tool that can be integrated with popular third-party tooling to bring CI/CD capabilities to the database.

FQL and FSL compliment each other, collectively providing a state of the art solution for storing and interacting with data.

### Fauna cross-region replication

Fauna replicates data across regions using its novel Distributed Transaction Engine (DTE), which was deeply inspired by the Calvin protocol. The DTE precomputes transaction read and write effects, applies those effects to a write-ahead log, replicates them across regions using a modified version of Raft, checks for conflicts, and then commits conflict-free transactions using Optimistic Concurrency Control (OCC). This architecture provides the strongest possible level of consistency guarantee and an attractive latency profile, without relying on locks.

### Flatenning references in Fauna

In Fauna, documents can reference each other. For example, consider the following document that represents a Customer and references the last order that the customer placed:

```fql
{
  name: "Tom Jones",
  lastOrder: Order.byId("382687178549887049"),
}
```

A projection can be used to flatten the reference. For example:

```fql
Customer.firstWhere(.name == "Tom Jones") {
	name,
	lastOrder
}
```

Will resolve and flatten the order reference in the response:
```fql
{
	name: "Tom Jones",
	lastOrder: {
		item: "Cornflakes Cereal"
	}
}
```