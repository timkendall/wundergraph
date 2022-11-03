---
title: GraphQl SSE subscriptions Example
pageTitle: WunderGraph - Examples - GraphQl SSE subscriptions
description:
---

[Check the example](https://github.com/wundergraph/wundergraph/tree/main/examples/graphql-sse-subscriptions)

## Protocol

https://github.com/enisdenjo/graphql-sse/blob/master/PROTOCOL.md

## Configuration

```typescript
const schema = `
schema {
  query: Query
  subscription: Subscription
}

type Query {
  hello: String
}

type Subscription {
  greetings: String
}
`

const greetings = introspect.graphql({
  apiNamespace: 'sse',
  url: 'http://127.0.0.1:4000/graphql/stream',
  loadSchemaFromString: schema,
  subscriptionsUseSSE: true,
})
```

## Getting started

```shell
npm install && npm start
```

## Check results

```shell
curl -N http://localhost:9991/app/main/operations/Sse
```

## SSE output

```shell
 curl -N http://localhost:9991/app/main/operations/Sse\?wg_sse\=true
```