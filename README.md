# task-1
student  grades
import java.util.ArrayList;
import java.util.Scanner;

class StudentGrade {
    String name;
    double grade;

    public StudentGrade(String name, double grade) {
        this.name = name;
        this.grade = grade;
    }
}

public class StudentGradesCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        ArrayList<StudentGrade> grades = new ArrayList<>();

System.out.println("Enter the number of students: ");
        int numStudents = scanner.nextInt();
        scanner.nextLine(); // Consume newline left-over

        for (int i = 0; i < numStudents; i++) {
            System.out.println("Enter student " + (i + 1) + "'s name: ");
            String name = scanner.nextLine();
            System.out.println("Enter student " + (i + 1) + "'s grade: ");
            double grade = scanner.nextDouble();
            scanner.nextLine(); // Consume newline left-over
            grades.add(new StudentGrade(name, grade));
        }

        double sum = 0;
        double highest = Double.NEGATIVE_INFINITY;
        double lowest = Double.POSITIVE_INFINITY;

        for (StudentGrade grade : grades) {
            sum += grade.grade;
            highest = Math.max(highest, grade.grade);
            lowest = Math.min(lowest, grade.grade);
        }

        double average = sum / grades.size();

        System.out.println("\nResults:");
        System.out.println("Average grade: " + average);
        System.out.println("Highest grade: " + highest);
        System.out.println("Lowest grade: " + lowest);
    }
}


How to Run

1. Save the code in a file named StudentGradesCalculator.java.
2. Compile the program using javac StudentGradesCalculator.java.
3. Run the program using java StudentGradesCalculator.

Example Use Case


Enter the number of students: 3
Enter student 1's name: John
Enter student 1's grade: 85
Enter student 2's name: Alice
Enter student 2's grade: 92
Enter student 3's name: Bob
Enter student 3's grade: 78

Results:
Average grade: 85.0
Highest grade: 92.0
Lowest grade: 78.0
