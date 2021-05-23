# Fixture

To reduce duplication, we split fixtures into two parts:
- global: all tests requires this, e.g. seeding users with different roles
- local: the entities are tests specific, e.g. creating a new order


At times, the fixture can get deeply nested - if you have reach the situation where you have to create waterfall entities, you know what I mean.
