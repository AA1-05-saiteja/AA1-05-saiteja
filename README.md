import java.util.ArrayList;
import java.util.List;

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

public class Main {
    public static void main(String[] args) {
        Course course = new Course("Java Programming");

        Student student1 = new Student("Saiteja", 1);
        Student student2 = new Student("Chandrahas ", 2);
        Student student3 = new Student(" Pavan", 3);

        course.enrollStudent(student1);
        course.enrollStudent(student2);
        course.enrollStudent(student3);

        course.displayCourseInfo();
    }
}
