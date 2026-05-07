# file_mamnagement_system--os
import os

# Create File
def create_file():
    name = input("Enter file name: ")

    try:
        file = open(name, "w")
        file.close()
        print(" File created successfully!")

    except Exception as e:
        print("Error:", e)


# Write Data into File
def write_file():
    name = input("Enter file name: ")

    try:
        data = input("Enter data to write: ")

        file = open(name, "a")
        file.write(data + "\n")
        file.close()

        print("Data written successfully!")

    except Exception as e:
        print("Error:", e)


# Read File
def read_file():
    name = input("Enter file name: ")

    if os.path.exists(name):

        try:
            file = open(name, "r")

            print("\n File Content:\n")
            print(file.read())

            file.close()

        except Exception as e:
            print("Error:", e)

    else:
        print(" File does not exist!")


# Delete File
def delete_file():
    name = input("Enter file name: ")

    if os.path.exists(name):

        try:
            os.remove(name)
            print("File deleted successfully!")

        except Exception as e:
            print("Error:", e)

    else:
        print(" File does not exist!")


# Main Program
while True:

    print("\n====== FILE MANAGEMENT SYSTEM ======")
    print("1. Create File")
    print("2. Write File")
    print("3. Read File")
    print("4. Delete File")
    print("5. Exit")

    choice = input("Enter your choice: ")

    if choice == '1':
        create_file()

    elif choice == '2':
        write_file()

    elif choice == '3':
        read_file()

    elif choice == '4':
        delete_file()

    elif choice == '5':
        print("Exiting program...")
        break

    else:
        print("Invalid choice! Please try again.")  
