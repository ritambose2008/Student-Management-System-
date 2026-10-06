# Student-Management-System-
A simple Student Management System built with python
students = []


def add_student():
    roll = input("Enter Roll Number: ")
    name = input("Enter Student Name: ")
    age = input("Enter Age: ")
    course = input("Enter Course: ")

    student = {
        "roll": roll,
        "name": name,
        "age": age,
        "course": course
    }

    students.append(student)
    print("\nStudent added successfully!\n")


def view_students():
    if not students:
        print("\nNo students found.\n")
        return

    print("\n--- Student List ---")

    for student in students:
        print("Roll Number:", student["roll"])
        print("Name:", student["name"])
        print("Age:", student["age"])
        print("Course:", student["course"])
        print("--------------------")


def search_student():
    roll = input("Enter Roll Number to search: ")

    for student in students:
        if student["roll"] == roll:
            print("\nStudent Found!")
            print("Roll Number:", student["roll"])
            print("Name:", student["name"])
            print("Age:", student["age"])
            print("Course:", student["course"])
            return

    print("\nStudent not found.\n")


def delete_student():
    roll = input("Enter Roll Number to delete: ")

    for student in students:
        if student["roll"] == roll:
            students.remove(student)
            print("\nStudent deleted successfully!\n")
            return

    print("\nStudent not found.\n")


while True:
    print("\n===== STUDENT MANAGEMENT SYSTEM =====")
    print("1. Add Student")
    print("2. View Students")
    print("3. Search Student")
    print("4. Delete Student")
    print("5. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        add_student()

    elif choice == "2":
        view_students()

    elif choice == "3":
        search_student()

    elif choice == "4":
        delete_student()

    elif choice == "5":
        print("Thank you for using Student Management System!")
        break

    else:
        print("Invalid choice. Please try again.")