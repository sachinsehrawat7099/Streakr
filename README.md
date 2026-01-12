flowchart TD
    UI[Frontend] --> GW[API Gateway]

    GW --> US[User Service]
    GW --> HS[Habit Service]
    GW --> BS[Battle Service]

    HS --> K[Kafka Topics]
    BS --> K
    US --> K

    K --> SS[Scoring Service]
    SS --> NS[Notification Service]
    SS --> AS[Analytics Service]

    K --> MLDS[ML Data Ingestion]
    MLDS --> FS[Feature Store]
    FS --> MLTR[ML Training]
    MLTR --> MLS[ML Inference Service]
    MLS --> NS
