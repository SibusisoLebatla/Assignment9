# Reflection – Domain & Class Diagram Design

### 1. Challenges Faced

While designing the domain model and class diagram, a major challenge was abstracting real-world functionality into manageable code elements. It was particularly tricky to decide where to draw the line between responsibilities of classes such as `Loan`, `Payment`, and `Book`. Should a payment belong to the `Loan` or be its own class? This took some back-and-forth.

Mermaid.js syntax was initially a challenge, especially getting the relationships and multiplicities to render correctly. Reading Mermaid documentation helped resolve this.

### 2. Alignment with Previous Assignments

This class diagram reflects the requirements from Assignment 4, use cases from Assignment 5, and behavior from Assignment 8:

- From use cases, `User` actions like borrowing and returning books led to methods in `Book` and `Loan`.
- State diagrams in Assignment 8 (e.g., `Book` transitioning from "Available" to "CheckedOut") clearly informed the status attribute and methods like `checkOut()` and `return()`.
- Activity workflows like “Fine Payment” directly influenced the `Payment` class and its `process()` method.

### 3. Trade-offs Made

One key trade-off was avoiding inheritance even though `Staff` and `User` could have shared a parent class. This was done to simplify the diagram and avoid unnecessary complexity.

Another trade-off was not implementing subclasses for `Notification` (like SMS or Email) to keep the diagram clean.

### 4. Lessons Learned

- Object-oriented design is all about balance. It’s easy to over-engineer or under-engineer a model.
- Relationships and multiplicities are crucial for showing real-world interactions.
- Aligning with earlier assignments (use cases and activity diagrams) helped guide correct class responsibilities.
- Diagrams are a communication tool, not just a technical artifact — clarity is key.
