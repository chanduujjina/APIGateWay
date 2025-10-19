## APIGateWay
```mermaid
flowchart TD
    A[Client / UI / Mobile App] --> B[API Gateway]
    B --> C[Order Service (8082)]
    B --> D[Inventory Service (8081)]
    C --> E[(Order DB)]
    D --> F[(Inventory DB)]


