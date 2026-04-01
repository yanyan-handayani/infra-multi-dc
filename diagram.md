flowchart LR
    JKT["Cyber 1 Jakarta
Primary Site
MinIO Master
MariaDB Master
WireGuard Hub"]:::primary

    CKR["Diskominfo Bekasi Cikarang
Replica Site
MinIO Replica
MariaDB Slave"]:::replica

    BTM["NDC Batam
Replica Site
MinIO Replica
MariaDB Slave"]:::replica

    BDG["Diskominfo Jabar Bandung
Replica Site
MinIO Replica
MariaDB Slave
Planned Public Endpoint"]:::replica

    JKT ---|"WireGuard Hub-Spoke"| CKR
    JKT ---|"WireGuard Hub-Spoke"| BTM
    JKT ---|"WireGuard Hub-Spoke"| BDG

    JKT -->|"MinIO Replication"| CKR
    JKT -->|"MinIO Replication"| BTM
    JKT -->|"MinIO Replication"| BDG

    CKR -->|"MinIO Reverse Sync"| JKT
    BTM -->|"MinIO Reverse Sync"| JKT
    BDG -->|"MinIO Reverse Sync"| JKT

    JKT -->|"MariaDB Replication"| CKR
    JKT -->|"MariaDB Replication"| BTM
    JKT -->|"MariaDB Replication"| BDG

    classDef primary fill:#1f4b99,color:#fff,stroke:#0b1f4d,stroke-width:2px;
    classDef replica fill:#2d6a4f,color:#fff,stroke:#1b4332,stroke-width:2px;
