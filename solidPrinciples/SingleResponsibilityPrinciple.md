# 🧱 SOLID Principles in Java

---

## 🔹 S - Single Responsibility Principle (SRP)

### 🧠 What is SRP?

> A class should have only **one reason to change**.

A class should focus on only one job or functionality. If a class takes on more responsibilities, it becomes hard to maintain and modify. SRP helps keep the code clean, testable, and easy to extend.

---

### ❌ Bad Example with Explanation

The class below violates SRP by handling **multiple responsibilities** like fetching data, printing, and saving the report:

```java
public class Report {
    public String getReportData() {
        // logic to fetch report data
        return "Report Data";
    }

    public void printReport() {
        // logic to print the report
        System.out.println("Printing Report...");
    }

    public void saveToFile() {
        // logic to save report to file
        System.out.println("Saving Report...");
    }
}
```

🧨 **What's wrong here?**
- The `Report` class is responsible for:
  - Business logic (getting report data)
  - Presentation logic (printing)
  - Persistence logic (saving)
- If any of these change, the class has to be modified, violating **SRP**.

---

### ✅ Good Example with Explanation

Let's break this into **three classes**, each focused on a single responsibility:

```java
public class Report {
    public String getReportData() {
        return "Report Data";
    }
}

public class ReportPrinter {
    public void printReport(String data) {
        System.out.println("Printing: " + data);
    }
}

public class ReportSaver {
    public void saveReport(String data) {
        System.out.println("Saving: " + data);
    }
}
```

🌟 **What's right here?**
- `Report` → only responsible for holding/generating data.
- `ReportPrinter` → only prints data.
- `ReportSaver` → only saves data.

📌 Each class now has **only one reason to change**, satisfying the SRP. This separation of concerns makes your code **modular**, **easier to test**, and **simpler to maintain**.

---

✅ **Summary:**
- Avoid stuffing multiple responsibilities into a single class.
- Split logic into separate, focused classes.
- One class → one job → one reason to change.

---

