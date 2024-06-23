import java.util.ArrayList;
import java.util.List;

// Student Class
class Student {
    private String name;
    private int id;

    public Student(String name, int id) {
        this.name = name;
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public int getId() {
        return id;
    }

    public void displayInfo() {
        System.out.println("Student ID: " + id + ", Name: " + name);
    }
}

// Course Class
class Course {
    private String courseName;
    private List<Student> students;

    public Course(String courseName) {
        this.courseName = courseName;
        this.students = new ArrayList<>();
    }

    public void enrollStudent(Student student) {
        students.add(student);
        System.out.println(student.getName() + " has been enrolled in " + courseName);
    }

    public void displayCourseInfo() {
        System.out.println("Course: " + courseName);
        for (Student student : students) {
            student.displayInfo();
        }
    }
}

// Student Management System Class
public class StudentManagementSystem {
    public static void main(String[] args) {
        // Create Students
        Student student1 = new Student("Student1", 1);
        Student student2 = new Student("Student2", 2);
        Student student3 = new Student("Student3", 3);
        Student student4 = new Student("Student4", 4);
        Student student5 = new Student("Student5", 5);

        // Create a course
        Course course = new Course("Introduction to Java");

        // Enroll students in the course
        course.enrollStudent(student1);
        course.enrollStudent(student2);
        course.enrollStudent(student3);
        course.enrollStudent(student4);
        course.enrollStudent(student5);

        // Display course information
        course.displayCourseInfo();
    }
}
