class ContactManager:
    def __init__(self):
        self.contacts = {}

    def add_contacts(self):
        name = input("Enter name: ")
        phone = input("Enter phone number: ")
        email = input("Enter email: ")
        address = input("Enter address: ")
        self.contacts[name] = {"phone": phone, "email": email, "address": address}

    def view_contact(self):
        for name, details in self.contacts.items():
            print(f"Name: {name}, Phone: {details['phone']}")

    def search_contact(self):
        query = input("Enter name or Phone number: ")
        for name, details in self.contacts.items():
            if query in [name, details["phone"]]:
                print(f"Name: {name}, Phone: {details['phone']}, Email: {details['email']}, Address: {details['address']}")

    def update_contact(self):
        name = input("Enter name of the contact to update: ")
        if name in self.contacts:
            phone = input("Enter new phone number (press enter to skip): ")
            email = input("Enter new email (press enter to skip): ")
            address = input("Enter new address (press enter to skip): ")
            if phone:
                self.contacts[name]["phone"] = phone
            if email:
                self.contacts[name]["email"] = email
            if address:
                self.contacts[name]["address"] = address
        else:
            print("Contact not found.")

    def delete_contacts(self):
        name = input("Enter name of the contact to delete: ")
        if name in self.contacts:
            del self.contacts[name]
        else:
            print("Contact not found.")

def main():
    manager = ContactManager()
    while True:
        print("\n1.Add Contact\n2.View Contacts\n3.Search Contact\n4.Update Contact\n5.Delete Contact\n6.Exit")
        choice = input("Enter your choice: ")
        if choice == "1":
            manager.add_contacts()
        elif choice == "2":
            manager.view_contact()
        elif choice == "3":
            manager.search_contact()
        elif choice == "4":
            manager.update_contact()
        elif choice == "5":
            manager.delete_contacts()
        elif choice == "6":
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()


