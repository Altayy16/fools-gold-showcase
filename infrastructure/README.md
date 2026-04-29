# Infrastructure & DevOps Architecture

This directory contains the actual container orchestration files used to run *Fools Gold*.

## Architecture Highlights

This `compose.yaml` demonstrates a production-ready, decoupled architecture:
* **Laravel Reverb (Realtime):** A dedicated container running Laravel Reverb on port 8080 to handle high-concurrency WebSocket connections for the turn-based game state. This translates directly to the real-time requirements of modern SaaS applications (similar to Supabase Realtime).
* **Dedicated Queue Worker:** Background jobs (like processing game rewards or matchmaking) are offloaded to a dedicated PHP CLI container running `queue:work`, ensuring the main web application remains lightning-fast.
* **Nginx Edge Routing:** The `default.conf` is optimized for performance, utilizing Gzip compression and aggressive browser caching (Cache-Control: immutable) for static game assets.
* **Redis:** Utilized both as a high-speed cache and the primary driver for the background job queues.
* **Database:** MySQL 8.4 is used as the primary relational database. The complex relational modeling, indexing, and strict schema designs used here are highly transferable to PostgreSQL environments.