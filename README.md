# contacts_list-
program for contact llist
contacts = []
def add_contact():
    name = input("Enter the contact's name: ")
    number = input("Enter the contact's phone number: ")
    email = input("Enter the contact's email address: ")
    contact = {
        'name': name,
        'number': number,
        'email': email
    }
    contacts.append(contact)
    print("Contact added successfully!")

def search_contact():
    name = input("Enter the name to search: ")
    found_contacts = []
    for contact in contacts:
        if name.lower() in contact['name'].lower():
            found_contacts.append(contact)
    if len(found_contacts) > 0:
        print("Search results:")
        for contact in found_contacts:
            print("Name:", contact['name'])
            print("Phone Number:", contact['number'])
            print("Email:", contact['email'])
            print("----------------------")
    else:
        print("No contacts found!")

def display_contacts():
    if len(contacts) > 0:
        print("Contacts:")
        for contact in contacts:
            print("Name:", contact['name'])
            print("Phone Number:", contact['number'])
            print("Email:", contact['email'])
            print("----------------------")
    else:
        print("Contact list is empty!")

def remove_contact():
    name = input("Enter the name of the contact to remove: ")
    removed = False
    for contact in contacts:
        if name.lower() == contact['name'].lower():
            contacts.remove(contact)
            removed = True
    if removed:
        print("Contact removed successfully!")
    else:
        print("Contact not found!")

def menu():
    print("Welcome to the Contact List Program!")
    print("1. Add a contact")
    print("2. Search contacts")
    print("3. Display all contacts")
    print("4. Remove a contact")
    print("5. Exit")

    while True:
        choice = input("Enter your choice (1-5): ")
        if choice == '1':
            add_contact()
        elif choice == '2':
            search_contact()
        elif choice == '3':
            display_contacts()
        elif choice == '4':
            remove_contact()
        elif choice == '5':
            print("Thank you for using the Contact List Program. Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")

menu()
