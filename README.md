```mermaid
flowchart TD
    A[Client / UI / Mobile App]
    B[API Gateway]
    C[Order Service]
    D[Inventory Service (8081)]
    E[(Order DB)]
    F[(Inventory DB)]

    A --> B
    B --> C
    B --> D
    C --> E
    D --> F
```


