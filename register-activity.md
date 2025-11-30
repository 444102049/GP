```mermaid
flowchart TD

    A([Start]) --> B[Show_Login_Register]

    B --> C{Existing_user?}

    %% Register path
    C -->|No| R1[Input_New_Data]
    R1 --> R2[Validate_Reg]
    R2 --> R3{Email_Used?}
    R3 -->|Yes| R4[Show_Email_Error]
    R4 --> B
    R3 -->|No| R5[Create_Account]
    R5 --> R6[Create_Session]
    R6 --> E([End])

    %% Login path
    C -->|Yes| L1[Input_Credentials]
    L1 --> L2[Validate_Login]
    L2 --> L3{Valid?}
    L3 -->|No| L4[Show_Login_Error]
    L4 --> B
    L3 -->|Yes| L5[Create_Session]
    L5 --> E
