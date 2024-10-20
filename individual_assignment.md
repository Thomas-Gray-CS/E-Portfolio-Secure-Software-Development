System Implementation Assignment - Driverless Car

Below is the Python code to support the operation of a driverless car, as well as an accompanying file that explains my thought processes and decision making while completing this. This contributes to and shows how I meet Learning Outcomes:
1) Appraise and critically evaluate object-oriented programming compared to other programming paradigms.
2) Design and implement programs that demonstrate appropriate use of object-oriented design principles.
3) Select and use appropriate data structures for a given problem..


### Python Code To Support The Operation Of A Driverless Car                                                                                                      


  ```
     import uuid # imports UUID for use in student ID security

import bcrypt # import bcrypt for use in password hashing


class Student: # defines a class for each student record

    def __init__(self, name, year_group, form): # defines each attribute that objects in this class will have
        self.student_id = uuid.uuid4().hex  # Generate a unique ID using UUID
        self.name = name # sets name
        self.year_group = year_group # sets year group
        self.form = form # sets form
        self.classes = set() # creates a set for classes, so they cannot be repeated

    def add_class(self, class_title): # function for adding a class to a student
        self.classes.add(class_title)

    def remove_class(self, class_title): # function for removing a class from a student
        self.classes.discard(class_title)

    def get_student_details(self): # function to return all attributes for a student
        return {
            "ID": self.student_id,
            "name": self.name,
            "year": self.year_group,
            "form": self.form
        }
    
    def __repr__(self):
        return "student details({self.student_id}, {self.name}, {self.year_group}, {self.form})" # provides all student details

class StudentRecords: # class for the entire student record
    def __init__(self):
        self.students = {} # dictionary of students to link to student class

    def add_student(self, name, year_group, form): # adds student to the student class
        student = Student(name, year_group, form)
        self.students[student.student_id] = student
        
    def display_student(self, student_id): # prints student in the student class if student found
        if student_id in self.students:
            student = self.students[student_id]
            print("{student.student_id}, {student.name}, {student.year_group}, {student.form}.")
        else:
            print("Student {student_id} not found.") # prints student if not found

    def remove_student(self, student_id): # function to remove a student
        if student_id in self.students:
            del self.students[student_id]
            print("Student deleted.") # indicates student deleted
        else:
            print("Student {student_id} not found.") # prints that student not found

admin_users = {} # dictionary for admin login details

def hash_password(password): # function to hash passwords
    salt = bcrypt.gensalt()
    hashed_password = bcrypt.hashpw(password.encode('utf-8'), salt) # hashes password and adds salt
    return hashed_password # returns hashed password for use

admin_users["T.Gray"] = hash_password("Password1234") # test record to indicate how passwords will be stored
admin_users["B.McDonald"] = hash_password("TestPass99") # test record to indicate how passwords will be stored
admin_users["M.Jordan"] = hash_password("MockPass123!") # test record to indicate how passwords will be stored

users = {} # dictionary for general users, with same functions as admin_users

def hash_password(password):
    salt = bcrypt.gensalt()
    hashed_password = bcrypt.hashpw(password.encode('utf-8'), salt)
    return hashed_password

users["H.Ford"] = hash_password("Number1Pass")
users["D.Leland"] = hash_password("WeWantPass")
users["Q.Regan"] = hash_password("HelloWorld!")

def admin_check(): # function to check if user is admin
    admin_rights = input("Admin Login Y/N? ")
    if admin_rights == "Y": # if admin, calls the admin login function
        admin_login()
    elif admin_rights == "N": # if not admin, calls general login function
        login()

def admin_login(): # function just for admin logins
    username = input("Enter your username: ") # user enters username
    password = input("Enter your password: ") # user enters password
    if username not in admin_users:
        print("Username not found") # indicates if not found
        return False
    if bcrypt.checkpw(password.encode('utf-8'), admin_users[username]): 
        print("Login successful") # indicates that username and password are correct
        admin_functions() # calls admin functions
        return True
    else:
        print("Password incorrect.") # indicates password incorrect and doesn't proceed
        return False
    
def admin_functions(): # functions that are called after successful admin login 
    admin_option = int(input("What would you like to do today? To search for a student, press 1. To add a student, press 2. To delete a student, press 3. ")) # allows users to select what to do, and confirms a number is used
    records = StudentRecords() # links student records for ease of use
    if admin_option == 1:
        student_id = input("Enter student ID: ") # allows admin to search for students
        records.display_student(student_id)
        menu_choice = input("To retun to menu, press 1: ")
        if menu_choice == 1:
            admin_functions()
    elif admin_option == 2: # allows admins to create students
        name = input("Enter student name: ")
        year_group = input("Enter year group: ")
        form = input("Enter form: ")
        records.add_student(name, year_group, form) # adds student to student record class, which in turn adds to student class
        print("Student added")
        menu_choice = input("To retun to menu, press 1: ")
        if menu_choice == 1:
            admin_functions()
    elif admin_option == 3:
        student_id = input("Enter student ID: ")
        records.remove_student(student_id) # removes student on linked student ID
        print("Student removed")
        menu_choice = input("To retun to menu, press 1: ")
        if menu_choice == 1:
            admin_functions()

def read_only_functions(): # function just for read only users
    student_id = input("Please enter a student ID: ") # search on student ID
    records = StudentRecords()
    if student_id in records.students:
        print(records.students[student_id].get_student_details()) # if ID found, full record printed
        menu_choice = input("To retun to menu, press 1")
        if menu_choice == 1:
            read_only_functions()
    else:
        print("Student not found.") # indicates student ID is wrong
        read_only_functions()

def login(): # function for general read only login
    username = input("Enter your username: ") # user enters username
    password = input("Enter your password: ") # user enters password
    if username not in users:
        print("Username not found") # indicates username not found
        return False
    if bcrypt.checkpw(password.encode('utf-8'), users[username]): # checks password
        print("Login successful")
        read_only_functions() # calls read only functions for use
        return True
    else:
        print("Password incorrect.") # indicates password incorrect
        return False

admin_check() # calls admin check to start the process of the application
      ```

---
### README File Explaining The System Implementation

[System Implementation](/pdf/system-implementation.pdf)


