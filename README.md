# 📊 CodeAlpha Student Grade Tracker

This is a simple **Java console application** built to manage and analyze student grades.  
It was developed as part of the **CodeAlpha Java Programming Internship**.

---

## 💡 Features

- Input names and grades for multiple students
- Calculate:
  - 📌 Average Grade
  - 🏆 Highest Grade
  - ⚠️ Lowest Grade
- Display summary report in console
- Written using core Java (no external libraries)

---

## 🖥️ Code
import java.util.*;

public class StudentGradeTracker {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input number of students
        System.out.print("Enter number of students: ");
        int numStudents = scanner.nextInt();

        // Store student names and grades
        String[] studentNames = new String[numStudents];
        int[] grades = new int[numStudents];

        // Input names and grades
        for (int i = 0; i < numStudents; i++) {
            System.out.print("Enter name of student " + (i + 1) + ": ");
            studentNames[i] = scanner.next();

            System.out.print("Enter grade of " + studentNames[i] + ": ");
            grades[i] = scanner.nextInt();
        }

        // Calculate stats
        int total = 0;
        int highest = grades[0];
        int lowest = grades[0];

        for (int grade : grades) {
            total += grade;
            if (grade > highest) highest = grade;
            if (grade < lowest) lowest = grade;
        }

        double average = (double) total / numStudents;

        // Output report
        System.out.println("\n--- Student Grades Report ---");
        for (int i = 0; i < numStudents; i++) {
            System.out.println(studentNames[i] + " : " + grades[i]);
        }

        System.out.println("Average Grade: " + average);
        System.out.println("Highest Grade: " + highest);
        System.out.println("Lowest Grade: " + lowest);

        scanner.close();
    }
}
## 🖥️ Output
Enter number of students: 3
Enter name of student 1: Alice
Enter grade of Alice: 85
Enter name of student 2: Bob
Enter grade of Bob: 92
Enter name of student 3: Charlie
Enter grade of Charlie: 78

--- Student Grades Report ---
Alice : 85
Bob : 92
Charlie : 78
Average Grade: 85.0
Highest Grade: 92
Lowest Grade: 78

