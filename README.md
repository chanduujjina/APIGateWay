## APIGateWay
```mermaid
flowchart TD
    A[Client / UI / Mobile App] -->|Single Entry Point| B(API Gateway)
    B -->|Route 1| C[Order Service (8082)]
    B -->|Route 2| D[Inventory Service (8081)]
    C --> E[(Order DB)]
    D --> F[(Inventory DB)]


