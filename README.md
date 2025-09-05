# Order Summary API — Assessment Scaffold

This Odoo module skeleton helps demonstrate the **Senior Backend** assessment:
- Optimized ORM aggregation (`read_group`) for large datasets
- JWT-protected HTTP endpoint: `/api/v1/order-summary`
- Real-time notifications via Odoo `bus` when `stock.move` changes

## Files
- `controllers/order_summary.py` — HTTP API returning aggregated rows
- `models/stock_move.py` — publishes bus events on stock changes
- `utils/jwt_utils.py` — minimal HS256 verification helpers
- `__manifest__.py` — depends on `sale_management`, `stock`, `bus`

## Notes
- This is a scaffold for demonstration, not a production-ready module.
- For real deployments: use **PyJWT**, **system parameters** for secrets, add **access controls**, and index heavy fields in Postgres.
