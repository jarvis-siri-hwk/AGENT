# Technical Section: GUI Implementation

Our GUI is implemented using Java Swing and consists of a main window with three tabbed panels, each providing different functionality for managing competitors. Here's a breakdown of the key components and their interactions:

## 1. View/Edit Score Panel

This panel allows users to view and edit scores for individual competitors.

Key components:
- JTextField for entering competitor number
- JButton to trigger the view action
- JTextArea to display competitor details

When a user enters a competitor number and clicks the "View" button, the following process occurs:

```java
viewButton.addActionListener(e -> {
    int number = Integer.parseInt(competitorNumberField.getText());
    Competitor competitor = competitorList.getCompetitorByNumber(number);
    if (competitor != null) {
        detailsArea.setText(competitor.getFullDetails());
    } else {
        detailsArea.setText("Competitor not found.");
    }
});
```

This code snippet demonstrates how we can retrieve the competitor object based on the entered number and display their details. Error handling is implemented to manage cases where the competitor is not found.

## 2. Sort Competitors Panel

This panel displays all competitors in a table format and allows sorting by name or score.

Key components:
- JTable to display competitor data
- JButtons for sorting options

```java
sortByNameButton.addActionListener(e -> {
    List<Competitor> sorted = competitorList.getAllCompetitors();
    sorted.sort((c1, c2) -> c1.name.compareTo(c2.name));
    updateTable(model, sorted);
});
```

This code sorts the competitors by name and updates the table display. A similar method is used for sorting by score.

## 3. Filter Competitors Panel

This panel allows users to filter competitors based on level and competition type.

Key components:
- JComboBox for level selection
- JRadioButtons for competition type selection

```java
List<Competitor> filtered = allCompetitors.stream()
    .filter(c -> level.equals("All") || c.level.equals(level))
    .filter(c -> type.equals("All") || 
        (type.equals("Running") && c instanceof RunningCompetitor) ||
        (type.equals("Swimming") && c instanceof SwimmingCompetitor) ||
        (type.equals("Golf") && c instanceof GolfCompetitor))
    .toList();
```

# Java Programming Language

Java, conceived by James Gosling and his team at Sun Microsystems in the mid-1990s, emerged with the revolutionary "write once, run anywhere" philosophy. This concept, enabled by the Java Virtual Machine (JVM), allowed Java to quickly gain traction in a computing landscape increasingly defined by heterogeneous systems.

Java's design reflects a careful balance between simplicity and power. Its syntax, derived from C and C++, provided familiarity to existing programmers while introducing key improvements such as automatic memory management and a robust type system. These features significantly reduced common programming errors and enhanced code reliability.

The extensive standard library has been a cornerstone of Java's success, providing a rich set of tools for common programming tasks, from basic data structures to network communications and GUI development. This comprehensive ecosystem has been a key factor in Java's widespread adoption across various domains.

In its commercial context, Java has played a transformative role in the software industry. It became the de facto standard for enterprise applications, powering mission-critical systems in finance, healthcare, and government sectors. The language's stability, scalability, and robust security features made it an ideal choice for building large-scale, distributed systems.

Java's evolution has been driven by both technical innovation and industry demands. The introduction of features like generics and lambda expressions kept the language modern and relevant. The development of enterprise frameworks like Spring and Java EE (now Jakarta EE) was driven by the need for standardized, efficient approaches to building complex business applications.

Looking to the future, Java faces both challenges and opportunities. The rise of cloud computing and microservices architectures has led to increased demand for languages with faster startup times and lower memory footprints. Java has responded with initiatives like GraalVM and Project Loom. Competition from more modern languages like Kotlin and Go poses a significant challenge, but Java's vast ecosystem and continuous evolution suggest a resilient future.

As artificial intelligence and machine learning become increasingly central to software development, Java's robust libraries and performance optimizations position it well to remain relevant in these emerging fields.

# Diagrams

## Activity Diagram

![Picture1](https://github.com/user-attachments/assets/4bdd0051-1f4d-44f8-b99a-9b8cf165429d)

## Use case Diagram

![Picture2](https://github.com/user-attachments/assets/3f56f01e-c865-4efb-9e5c-ddde294f615f)

# GUI Screenshot

![Screenshot (22)](https://github.com/user-attachments/assets/57904ff2-60c6-4f17-a44b-38b52694bda2)
