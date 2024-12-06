#Student Grade Tracker
class StudentGrades:
    def __init__(self):
        self.grades = {}

    def input_grades(self):
        num_subjects =int (input("Enter the number of subjects: "))
        for _ in range(num_subjects):
            subject = input("Enter subject name: ")
            grade =float(input(f"Enter Marks to show grade for {subject}: "))
            self.grades[subject] = grade

    def calculate_average(self):
        if not self.grades:
            return 0
        return sum(self.grades.values()) / len(self.grades)

    def get_letter_grade(self, average):
        if average >= 90:
            return 'A'
        elif average >= 80:
            return 'B'
        elif average >= 70:
            return 'C'
        elif average >= 60:
            return 'D'
        else:
            return 'F'

    def calculate_gpa(self, average):
        if average >= 90:
            return 4.0
        elif average >= 80:
            return 3.0
        elif average >= 70:
            return 2.0
        elif average >= 60:
            return 1.0
        else:
            return 0.0

    def display_results(self):
        average = self.calculate_average()
        letter_grade = self.get_letter_grade(average)
        gpa = self.calculate_gpa(average)

        print("\n--- Student Grade Report ---")
        print(f"Subjects: {', '.join(self.grades.keys())}")
        print(f"Average Grade: {average:.2f}")
        print(f"Letter Grade: {letter_grade}")
        print(f"GPA: {gpa:.2f}")

def main():
    student = StudentGrades()

    # Input grades from the user
    student.input_grades()

    # Display the results
    student.display_results()

if __name__ == "__main__":
    main()
