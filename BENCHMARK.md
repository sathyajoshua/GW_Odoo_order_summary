# Benchmarking Strategy (50k+ lines)

- **Dataset**: Create 50k+ `sale.order.line` entries across 1k orders.
- **Indexes**: Ensure indexes on `product_id`, `order_id`, `state`, and foreign keys used in domains.
- **Query**: Use `read_group` on `sale.order.line` grouped by `product_id` (and optionally `order_id` for sharding/pagination).
- **Measurement**: Use `odoo shell` or a timed controller to log execution time; target < 300ms for aggregation, < 100ms render.
- **Caching**: Cache stable aggregates per filter set in-memory (LRU) for a few seconds under load.
- **Async Jobs**: For heavy historical ranges, push to queue and return 202 + polling.
