# Students-management-system-
It's project about students management system 
students = {}

def add_student():
    roll = input("Enter Roll Number: ")

    if roll in students:
        print("Student already exists!")
        return

    name = input("Enter Name: ")
    age = input("Enter Age: ")
    course = input("Enter Course: ")

    students[roll] = {
        "Name": name,
        "Age": age,
        "Course": course
    }

    print("Student added successfully!")

def view_students():
    if not students:
        print("No student records found.")
        return

    print("\n----- Student Records -----")
    for roll, details in students.items():
        print(f"\nRoll No: {roll}")
        print(f"Name   : {details['Name']}")
        print(f"Age    : {details['Age']}")
        print(f"Course : {details['Course']}")

def search_student():
    roll = input("Enter Roll Number to search: ")

    if roll in students:
        details = students[roll]
        print("\nStudent Found")
        print(f"Name   : {details['Name']}")
        print(f"Age    : {details['Age']}")
        print(f"Course : {details['Course']}")
    else:
        print("Student not found.")

def update_student():
    roll = input("Enter Roll Number to update: ")

    if roll in students:
        students[roll]["Name"] = input("Enter New Name: ")
        students[roll]["Age"] = input("Enter New Age: ")
        students[roll]["Course"] = input("Enter New Course: ")

        print("Student updated successfully!")
    else:
        print("Student not found.")

def delete_student():
    roll = input("Enter Roll Number to delete: ")

    if roll in students:
        del students[roll]
        print("Student deleted successfully!")
    else:
        print("Student not found.")

while True:
    print("\n===== STUDENT MANAGEMENT SYSTEM =====")
    print("1. Add Student")
    print("2. View Students")
    print("3. Search Student")
    print("4. Update Student")
    print("5. Delete Student")
    print("6. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        add_student()
    elif choice == "2":
        view_students()
    elif choice == "3":
        search_student()
    elif choice == "4":
        update_student()
    elif choice == "5":
        delete_student()
    elif choice == "6":
        print("Thank you!")
        break
    else:
        print("Invalid choice! Please try again.")
