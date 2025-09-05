# Real-Time Updates via Bus

- Odoo's `bus` module provides a publish/subscribe channel.
- Backend: on `stock.move` create/write, send event to `(dbname, "order_summary_channel")`.
- Frontend: subscribe to that channel and refresh the popup table when an event arrives.
- For external dashboards, you can proxy bus events through a socket server (e.g., Socket.IO) if needed.
