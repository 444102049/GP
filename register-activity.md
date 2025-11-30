```mermaid
flowchart TD
    A([Start]) --> B[Display Register or Login page]

    B --> C{Did the user choose Register or Login?}

    %% Register path
    C -->|Register| R1[Enter new user data: name, email, phone, password]
    R1 --> R2[Validate registration data]
    R2 --> RQ{Is email already used?}
    RQ -->|Yes| R3[Show Email already exists error]
    R3 --> B
    RQ -->|No| R4[Create new account]
    R4 --> R5[Create user session]
    R5 --> E([End])

    %% Login path
    C -->|Login| L1[Enter email and password]
    L1 --> L2[Validate login data]
    L2 --> LQ{Are credentials val
