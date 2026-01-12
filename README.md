flowchart TD
    %% Client Layer
    UI[Frontend / Mobile App] --> GW[API Gateway]

    %% Core Microservices
    GW --> US[User Service]
    GW --> HS[Habit Service]
    GW --> BS[Battle Service]

    %% Event Streaming
    US --> K[(Kafka Topics)]
    HS --> K
    BS --> K

    %% Real-Time Processing
    K --> SS[Scoring Service]
    SS --> NS[Notification Service]
    SS --> AS[Analytics Service]

    %% Machine Learning Pipeline
    K --> MLDS[ML Data Ingestion Service]
    MLDS --> FS[(Feature Store)]
    FS --> MLTR[ML Training Pipeline]
    MLTR --> MLS[ML Inference Service]

    %% ML
