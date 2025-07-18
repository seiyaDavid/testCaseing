flowchart TD
    A[SNOW file upload/API call] --> B[Select field with issue description]
    B --> C[call Embeddings model]
    B --> D[DQIM file upload/API call -optional]
    D --> C
    C --> E[Call cluster ML model]
    E --> F[Call DQ issue identifier ML model]
    F --> G[Call Claude via Bedrock to:<br> - Label each cluster<br> - Describe the cluster/theme]
    G --> H[Compare themes/cluster between SNOW and DQIM data: Claude via Bedrock]
    G --> I[Chat with a selected cluster/theme:Claude via Bedrock]

    style A fill:#f9f,stroke:#333,stroke-width:1px
    style B fill:#bbf,stroke:#333,stroke-width:1px
    style C fill:#cfc,stroke:#333,stroke-width:1px
    style D fill:#f9f,stroke:#333,stroke-width:1px
    style E fill:#cff,stroke:#333,stroke-width:1px
    style F fill:#cff,stroke:#333,stroke-width:1px
    style G fill:#ffc,stroke:#333,stroke-width:1px
    style H fill:#ffc,stroke:#333,stroke-width:1px
    style I fill:#ffc,stroke:#333,stroke-width:1px
