## Aggregation Pipeline FROM https://docs.mongodb.com/manual/core/aggregation-pipeline/
-  MongoDB pipeline has stages and each stage transforms the document 
  - some stages generate new documents or filter
- Pipeline Operators and Indexes 
  - `$match` - best to place this at the beginning of pipeline. 
  - `$sort`
  - `$group`
  - `$geoNear` - must appear as the first stage in aggregation pipeline

## Aggregations in MongoDB by Example FROM https://www.compose.com/articles/aggregations-in-mongodb-by-example/
- Start aggregation, call aggregate function on a collection. 
  - aggregate function takes an array
- Matching Documents
  - `$match` is like the SQL WHERE clause
- Group documents together using `$group`. `_id` required.
- `$gte` and `$lt` used to make a range