# Mermaid 실습
- 순서도 실습
    - 첫번째 샘플


```{mermaid}
classDiagram
direction BT %% TB, BT, RL, LR 모두 가능

    class Person{
        <<abstract>>
        +name: str
        +phoneNumber: str
        +emailAddress: str
        +purchaseParkingPass()
    }

    class Student{
        
        +studentNumber: int
        +averageMark: int
        +isEligibleToEnroll(str) bool
        +getSeminarsTaken(): int
    }

    class Professor{
        -salary: int
        #staffNumber: int
        -yearsOfService: int
        +numberOfService: int
    }
    class Address{
        +street: str
        +city: str
        +state; str
        +postalCode: int
        +country: str
        -vaildate() bool
        +outputAsLable() str
    }

    Person <|-- Student
    Person <|-- Professor
    Student "0..*"<--"1..5" Professor : supervise
    Person "0..1"-->"1" Address : lives in
```

```mermaid
classDiagram
    class BankAccount
    BankAccount: String owner
    BankAccount: Bigdecimal balance
    BankAccount: deposit(amount)
    BankAccount: withdrawal(amount)
```

```mermaid
sequenceDiagram
    actor A as 사용자
    participant B as 서버
    
    A ->> B: 서비스 상태 요청
    
    alt 가능
        B -> A: 서비스 가능 상태입니다.
    else 불가능
        B -> A: 현재 서비스 중단 상태입니다.
    else 점검중
        B -> A: 점검중... 기다려 주세요
    end
```

```mermaid
sequenceDiagram
    participant A as Data Updater
    participant B as DB
    loop 1시간마다 수행
        A ->> B: send update data
        B -->> A: update result
    end
```

```mermaid
sequenceDiagram
    autonumber
    participant U as User
    participant C as Client
    participant S as Server
    participant DB as Database
    
    U ->> C: Fill username
    U ->> C: Fill password
    C ->> U: Enable "Login"button
    U ->> C: Click "Login"button

    C ->>+ S: POST/login
        S ->>+ DB: SELECT FROM users
        note over S,DB: See login.py for impl. details
        DB -->>- S: result
    S -->>- C: {authenticated: true}
    C ->> U: redirect/home
```



## 여기는  수업 끝 입니다.