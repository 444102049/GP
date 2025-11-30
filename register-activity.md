```mermaid
%%{init: {'theme': 'default'}}%%
flowchart TD

    %% Start
    A([Start]) --> B[Show Login/Register Screen]

    %% Decision
    B --> C{Existing user?}

    %% Register path
    C -->|No| R1[Input New Data]
    R1 --> R2[Validate Registration]
    R2 --> R3{Email Used?}
    R3 -->|Yes| R4[Show Email Error]
    R4 --> B
    R3 -->|No| R5[Create Account]
    R5 --> R6[Create Session]
    R6 --> E([End])

    %% Login path
    C -->|Yes| L1[Input Credentials]
    L1 --> L2[Validate Login]
    L2 --> L3{Valid?}
    L3 -->|No| L4[Show Login Error]
    L4 --> B
    L3 -->|Yes| L5[Create Session]
    L5 --> E
