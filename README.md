```mermaid
flowchart TD
    A[Client / UI / Mobile App]
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


