# observability
This project provides a complete observability stack using Docker, leveraging Grafana for visualization, Loki for log aggregation, and Tempo for distributed tracing. The setup is fully containerized, making it easy to deploy and manage.

Key Components:

Grafana: A visualization tool that serves as the central interface for viewing and analyzing logs, metrics, and traces. Grafana is configured to seamlessly integrate with Loki and Tempo.

Loki: A highly efficient log aggregation system that collects logs from various sources, stores them in a compressed format, and makes them available for querying in Grafana.

Tempo: A distributed tracing backend that allows you to track requests across different services, providing deep insights into system performance and issues.

Deployment:

The observability stack is set up using Docker, making it easy to deploy and scale. A Docker Compose file orchestrates the deployment of Grafana, Loki, and Tempo, ensuring they work together seamlessly. This setup provides a robust foundation for monitoring and improving system performance.