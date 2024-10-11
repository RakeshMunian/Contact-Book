# Contact-Book
contacts = {}

while True:
    print("\nContact Book")
    print("1. Create Contact")
    print("2. View Contact")
    print("3. Update Contact")  # Typo corrected: "Updatr" to "Update"
    print("4. Delete Contact")
    print("5. Search Contact")
    print("6. Count Contact")
    print("7. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        name = input("Enter your name: ")
        if name in contacts:
            print(f"Contact {name} already exists.")
        else:
            phone = input("Enter your phone number: ")
            email = input("Enter your email address: ")
            contacts[name] = {"phone": phone, "email": email}
            print(f"Contact {name} created successfully.")

    elif choice == "2":
        if contacts:  # Check if contacts dictionary is not empty
            print("\nAll Contacts:")
            for name, info in contacts.items():
                print(f"Name: {name}, Phone: {info['phone']}, Email: {info['email']}")
        else:
            print("No contacts found.")

    elif choice == "3":
        name = input("Enter the name of the contact to update: ")
        if name in contacts:
            phone = input("Enter the new phone number: ")
            email = input("Enter the new email address: ")
            contacts[name] = {"phone": phone, "email": email}
            print(f"Contact {name} updated successfully.")
        else:
            print(f"Contact {name} not found.")

    elif choice == "4":
        name = input("Enter the name of the contact to delete: ")
        if name in contacts:
            del contacts[name]
            print(f"Contact {name} deleted successfully.")
        else:
            print(f"Contact {name} not found.")

    elif choice == "5":
        name = input("Enter the name of the contact to search for: ")
        if name in contacts:
            print(f"\nContact found for {name}:")
            print(f"Name: {name}, Phone: {contacts[name]['phone']}, Email: {contacts[name]['email']}")
        else:
            print(f"Contact {name} not found.")

    elif choice == "6":
        print(f"Total number of contacts: {len(contacts)}")

    elif choice == "7":
        break  # Exit the loop

    else:
        print("Invalid choice. Please try again.")
