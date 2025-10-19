# API Gateway

## With Out Eureka Service

```mermaid
flowchart TD
    A[Client / UI]
    B[API Gateway]
    C[Order Service]
    D[Inventory Service]
    E[Shipment Service]
    F[(Order DB)]
    G[(Inventory DB)]
    H[(Shipment DB)]

    A --> B
    B --> C
    B --> D
    B --> E
    C --> F
    D --> G
    E --> H
```
### Characterstics
- You define fixed URLs for services inside the API Gateway (like localhost:8081, localhost:8082).

- Each service is started manually on a specific port.

- The gateway knows where to send requests because the URLs are hardcoded.

## With Eureka Service
```mermaid
flowchart TD
    A[Client]
    B[API Gateway]
    C[Eureka Server]
    D[Order Service]
    E[Inventory Service]
    F[Shipment Service]
    G[(Order DB)]
    H[(Inventory DB)]
    I[(Shipment DB)]

    A --> B
    B --> C
    C --> D
    C --> E
    C --> F
    D --> G
    E --> H
    F --> I 
```





