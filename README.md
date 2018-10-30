# student-grades
database of student grades with outputs showing highest grades

import java.util.ArrayList;

public class Student implements CalculateGrade {

    // class fields

    private String name;
    private int studentNumber;
    private String course;
    private int currentYear;
    private boolean registrationStatus;
    private ArrayList<Integer> gradeList;

    // constructor for all fields of Student class

    public Student() {
       gradeList = new ArrayList<Integer>();
    }

    // getter and setters for all fields of Student class

    public String getName() {
        return this.name;
    }
    public int getStudentNumber() {
        return this.studentNumber;
    }
    public String getCourse() {
        return this.course;
    }
    public int getCurrentYear() {
        return this.currentYear;
    }
    public boolean getRegistrationStatus() {
        return this.registrationStatus;
    }
    public int getGradeList(int index) {
        return gradeList.get(index);
    }
    public void setName(String studName) {
        this.name = studName;
    }
    public void setStudentNumber(int studNum) {
        this.studentNumber = studNum;
    }
    public void setCourse(String courseName) {
        this.course = courseName;
    }
    public void setCurrentYear(int currYear) {
        this.currentYear = currYear;
    }
    public void setRegistrationStatus(boolean regStatus) {
        this.registrationStatus = regStatus;
    }
    public void setGradeList(int grade) {
        gradeList.add(grade);
    }

    public int calculateGradeAverage() {

        int mark = 0;

        for (int i = 0; i < 10; i++) {
            mark += gradeList.get(i);
        }
        int avgMark = mark / 10;
        return  avgMark;
    }
    public String assignGrade() {

        int avgGrade = calculateGradeAverage();

        if (avgGrade >= 80) {
            return "A";
        }
        else if (avgGrade >= 70) {
            return "B";
        }
        else if (avgGrade >= 60) {
            return "C";
        }
        else if (avgGrade >= 50) {
            return "D";
        }
        else if (avgGrade >= 40) {
            return "E";
        }
        else {
            return "F";
        }
    }
}
