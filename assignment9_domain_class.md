# Domain Model

| Entity       | Attributes                             | Methods                           | Relationships                              |
|--------------|----------------------------------------|------------------------------------|--------------------------------------------|
| User         | userId, name, email, password          | register(), login(), delete()     | Borrows many Books via Loans               |
| Book         | bookId, title, ISBN, status            | checkOut(), return(), reserve()   | Associated with Loan                       |
| Loan         | loanId, dueDate, status                | calculateFine(), renew()          | Links User and Book                        |
| Payment      | paymentId, amount, date, status        | process(), verify()               | Linked to User and Loan                    |
| Notification | notificationId, type, message, status  | send(), markAsRead()              | Belongs to User                            |
| Staff        | staffId, name, role                    | assignTask(), approveLoan()       | Oversees Loans, manages Books              |
| Feedback     | feedbackId, content, response          | respond(), archive()              | Linked to User                             |

### 📜 Business Rules:
- A User can borrow up to **5 books** at once.
- A Book can only be loaned to **one user at a time**.
- Loans are due in **14 days**; fines apply after that.
- A Payment is required for **fines over R50**.
