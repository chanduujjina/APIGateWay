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

| Feature                  | Without Eureka                                                    |
| ------------------------ | ----------------------------------------------------------------- |
| **Service registration** | Manual — you configure URLs in `application.yml`                  |
| **Discovery**            | Static — Gateway uses hardcoded routes                            |
| **Scaling**              | Difficult — adding new service instances requires updating config |
| **Fault tolerance**      | Limited — Gateway can’t detect if a service goes down             |
| **Dev simplicity**       | ✅ Easy for small setups                                           |
| **Cloud readiness**      | ❌ Not ideal for dynamic or containerized environments             |


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

🧠 Characteristics
| Feature                  | With Eureka                                                   |
| ------------------------ | ------------------------------------------------------------- |
| **Service registration** | ✅ Automatic (services register on startup)                    |
| **Discovery**            | ✅ Dynamic — Gateway looks up service names from Eureka        |
| **Scaling**              | ✅ Easy — Add new instances, Eureka auto-discovers them        |
| **Fault tolerance**      | ✅ Gateway avoids dead services automatically                  |
| **Dev complexity**       | ⚙️ Slightly more setup (needs Eureka Server)                  |
| **Cloud readiness**      | ✅ Perfect for containerized environments (Docker, Kubernetes) |




