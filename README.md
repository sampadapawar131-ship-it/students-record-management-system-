# Student Record Management System

students = []

# Add Student
def add_student():
    name = input("Enter student name: ")
    age = input("Enter age: ")
    marks = input("Enter marks: ")
    subject = input("Enter subject: ")

    student = {
        "Name": name,
        "Age": age,
        "Marks": marks,
        "Subject": subject
    }

    students.append(student)
    print("Student record added successfully!\n")


# View Students
def view_students():
    if len(students) == 0:
        print("No student records found.\n")
    else:
        print("\nStudent Records:")
        for i, student in enumerate(students, start=1):
            print(f"\nStudent {i}")
            for key, value in student.items():
                print(f"{key}: {value}")


# Edit Student
def edit_student():
    name = input("Enter student name to edit: ")

    for student in students:
        if student["Name"] == name:
            student["Age"] = input("Enter new age: ")
            student["Marks"] = input("Enter new marks: ")
            student["Subject"] = input("Enter new subject: ")

            print("Student record updated successfully!\n")
            return

    print("Student not found!\n")


# Delete Student
def delete_student():
    name = input("Enter student name to delete: ")

    for student in students:
        if student["Name"] == name:
            students.remove(student)
            print("Student record deleted successfully!\n")
            return

    print("Student not found!\n")


# Main Menu
while True:
    print("\n===== Student Record Management System =====")
    print("1. Add Student")
    print("2. View Students")
    print("3. Edit Student")
    print("4. Delete Student")
    print("5. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        add_student()

    elif choice == "2":
        view_students()

    elif choice == "3":
        edit_student()

    elif choice == "4":
        delete_student()

    elif choice == "5":
        print("Exiting program...")
        break

    else:
        print("Invalid choice! Please try again.")