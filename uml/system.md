# Mini Moodle UML

版本：2026-11-06 審閱通過

依 `requirements.md` 的 R1～R5 繪製。使用者的審閱結果見 `review-02.md`。

## 類別圖

```mermaid
classDiagram
    class User {
        +id
        +username
        +passwordHash
        +role
    }
    class Course {
        +id
        +name
        +description
        +code
    }
    class Enrollment {
        +studentId
        +courseId
    }
    class Announcement {
        +id
        +title
        +body
    }
    class Message {
        +id
        +body
    }

    User "1" --> "0..*" Course : creates
    User "1" --> "0..*" Enrollment : joins
    Course "1" --> "0..*" Enrollment : contains
    Course "1" --> "0..*" Announcement : contains
    User "1" --> "0..*" Announcement : publishes
    Course "1" --> "0..*" Message : contains
    User "1" --> "0..*" Message : writes
```

`User.role` 只有教師與學生。`Course` 的建立者是教師。`Enrollment` 連接已加入的學生與課程。同一名學生對同一門課只有一筆加入紀錄。

## 學生加入課程循序圖

```mermaid
sequenceDiagram
    actor Student as 學生
    participant Page as 課程頁面
    participant App as 系統
    participant Store as 課程與加入紀錄

    Student->>Page: 輸入課碼
    Page->>App: 送出課碼
    App->>App: 確認已登入且角色為學生
    App->>Store: 查詢課碼
    alt 課碼不存在
        Store-->>App: 找不到課程
        App-->>Page: 顯示找不到課碼
    else 課碼有效
        Store-->>App: 回傳課程
        App->>Store: 查詢這名學生的加入紀錄
        alt 已加入
            Store-->>App: 已有紀錄
            App-->>Page: 顯示已加入
        else 尚未加入
            Store-->>App: 沒有紀錄
            App->>Store: 建立加入紀錄
            Store-->>App: 建立成功
            App-->>Page: 顯示課程
        end
    end
```

這張流程圖對應 R3。課碼格式與學生角色取自 R2、R1。
