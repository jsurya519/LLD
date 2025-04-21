# Single Responsibility Principle (SRP)

## Definition
A class should have only one reason to change, meaning it should only have one job/responsibility.

Keeping classes focused makes code easier to maintain, test, and extend.

---

## Bad Example (Violates SRP)

```java
public class Invoice {
    public void calculateTotal() {
        // Calculate invoice total
    }

    public void printInvoice() {
        // Print invoice
    }

    public void saveToDatabase() {
        // Save invoice to DB
    }
}
