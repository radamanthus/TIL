# Elasticsearch

## Using Stretchy

Simple search 
```
api = Stretchy.query
api = api.boost.where(taxon: context.query, weight: 20)
api = api.range(price: { gte: '500.0', lte: '1000.0' })
api = api.fulltext(context.query)
api.response
```
