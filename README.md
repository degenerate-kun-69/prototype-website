# prototype-website
i kind of found the source code and put it in here so it works i guess (~￣▽￣)~
%% ATM Withdrawal Use Case Diagram
%% Actors
actor :Bank Customer: as BankCustomer

%% Use Cases
usecase (Withdraw Cash) as WithdrawCash
usecase (Authenticate User) as AuthenticateUser
usecase (Print Receipt) as PrintReceipt

%% Relationships
BankCustomer --> WithdrawCash
WithdrawCash --> AuthenticateUser : <<include>>
PrintReceipt -up-> WithdrawCash : <<extend>>

%% Notes (Pre/Post Conditions)
note right of WithdrawCash
  **Preconditions**
  - ATM operational
  - Card inserted
  - Authenticated
  - Sufficient funds

  **Postconditions**
  - Balance updated
  - Cash dispensed
  - Receipt printed (if selected)
end note

note right of AuthenticateUser
  **Precondition**
  - Card inserted

  **Postcondition**
  - User authenticated
end note

note right of PrintReceipt
  **Postcondition**
  - Receipt printed
end note
