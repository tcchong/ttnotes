# GraphQL - A query language for APIs

> GraphQL was developed to cope with the need for more flexibility and efficiency in client-server communication.
>
> [https://www.howtographql.com](https://www.howtographql.com)
>
> “Think in graphs, not endpoints."
>
> "Describe the data, not the view."
>
> [Lessons From 4 Years of GraphQL](http://www.graphql.com/articles/4-years-of-graphql-lee-byron) by [Lee Byron](https://twitter.com/leeb), GraphQL Co-Inventor.

## What is GraphQL

* API standard
* declarative data fetching - client can specify exactly what data it needs
* single endpoint

## Design Principles

* **Hierarchical**

* **Product‐centric**

* **Strong‐typing**

* **Client‐specified queries**

* **Introspective**

## Why GraphQL

* allow for naturally querying nested information
* no more over- and underfetching
  * n+1 problem
* every change that is made to the UI, backend needs to adjusted for the new data needs
* insightful analytics
  * deprecating specific fields that are not requested by any clients any more
* GraphQL Schema Definition Language

  * serve as the contract between the client and the server to define how a client can access the data

  * frontend teams can mock test their applications by mocking the required data structures

## Schema Definition Language

* syntax for writing schemas for type system of GraphQL

```
# ! means required
type Course {
    price: Int!
    title: String!
}
```

* relation

```
type Course {
    price: Int!
    title: String!
    lectures: [Lecture]!
}

type Lecture {
    course: Course!
    title: String!
    content: String!
}
```

* follow the type to query data

## GraphQL Operation

### Query

* in the following example
  * courses field in the query -&gt; root fields of the query 
  * everything that follows the root field -&gt; payload of the query
  * return the list of all courses

```
{
    courses {
        title
        content
    }
}
```

### Mutation

* 3 kinds of mutations
  * creating new data
  * updating existing data
  * deleting existing data

### Subscription

* event-based realtime functionality
* hold steady conncetion with server

## GraphQL Schema

* represents contract between client-server

## Reference

[https://www.howtographql.com](https://www.howtographql.com)

[https://www.sitepoint.com/silver-bullet-n1-problem/](https://www.sitepoint.com/silver-bullet-n1-problem/)

[http://facebook.github.io/graphql](http://facebook.github.io/graphql)

[https://www.graphql.com/articles/4-years-of-graphql-lee-byron](https://www.graphql.com/articles/4-years-of-graphql-lee-byron)

