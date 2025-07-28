# ContactMaster
contacts = {
    "yash": {"phone": "9876543210", "email": "yaswanth668reddy@gmail.com"},
    "Bob": {"phone": "1234567890", "email": "bob@gmail.com"}
}

def add_contact():
    name = input("Enter name: ").strip()
    if name in contacts:
        print("Contact already exists.")
        return
    phone = input("Enter phone number: ").strip()
    email = input("Enter email address: ").strip()

    contacts[name] = {"phone": phone, "email": email}
    print(f"Contact {name} added successfully!")

def delete_contact():
    name = input("Enter name to delete: ").strip()
    if name in contacts:
        del contacts[name]
        print(f"Contact {name} deleted.")
    else:
        print("Contact not found.")

def search_contact():
    name = input("Enter name to search: ").strip()
    if name in contacts:
        print(f"\nName: {name}")
        print(f"Phone: {contacts[name]['phone']}")
        print(f"Email: {contacts[name]['email']}")
    else:
        print("Contact not found.")

def view_contacts():
    if not contacts:
        print("No contacts found.")
        return
    print("\n--- All Contacts ---")
    for name, info in contacts.items():
        print(f"\nName: {name}")
        print(f"Phone: {info['phone']}")
        print(f"Email: {info['email']}")

def main():
    while True:
        print("\n=== ContactMaster Menu ===")
        print("1. Add Contact")
        print("2. Delete Contact")
        print("3. Search Contact")
        print("4. View All Contacts")
        print("5. Exit")

        choice = input("Enter your choice (1-5): ").strip()

        if choice == '1':
            add_contact()
        elif choice == '2':
            delete_contact()
        elif choice == '3':
            search_contact()
        elif choice == '4':
            view_contacts()
        elif choice == '5':
            print("Exiting ContactMaster. Goodbye!")
            break
        else:
            print("Invalid choice. Please enter a number between 1 and 5.")

if __name__ == "__main__":
    main()
