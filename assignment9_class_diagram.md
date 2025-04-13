# Assignment 9 – Class Diagram (Mermaid.js)

```mermaid
classDiagram
class User {
  -userId: String
  -name: String
  -email: String
  -password: String
  +register()
  +login()
  +delete()
}

class Book {
  -bookId: String
  -title: String
  -ISBN: String
  -status: String
  +checkOut()
  +return()
  +reserve()
}

class Loan {
  -loanId: String
  -dueDate: Date
  -status: String
  +calculateFine()
  +renew()
}

class Payment {
  -paymentId: String
  -amount: Double
  -date: Date
  -status: String
  +process()
  +verify()
}

class Notification {
  -notificationId: String
  -type: String
  -message: String
  -status: String
  +send()
  +markAsRead()
}

class Staff {
  -staffId: String
  -name: String
  -role: String
  +assignTask()
  +approveLoan()
}

class Feedback {
  -feedbackId: String
  -content: String
  -response: String
  +respond()
  +archive()
}

User "1" -- "0..*" Loan : borrows
Book "1" -- "0..1" Loan : part of
Loan "1" -- "1" Payment : generates
User "1" -- "0..*" Notification : receives
User "1" -- "0..*" Feedback : submits
Staff "1" -- "0..*" Loan : manages
