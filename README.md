class PasswordManager:
    def __init__(self):
        self.passwords = {}

    def add_password(self, website, password):
        self.passwords[website] = password

    def get_password(self, website):
        return self.passwords.get(website, "Password not found")

    def list_websites(self):
        return list(self.passwords.keys())


def main():
    password_manager = PasswordManager()

    while True:
        print("Password Manager Menu:")
        print("1. Add Password")
        print("2. Get Password")
        print("3. List Websites")
        print("4. Exit")

        choice = input("Enter your choice: ")

        if choice == "1":
            website = input("Enter website: ")
            password = input("Enter password: ")
            password_manager.add_password(website, password)
            print("Password added successfully!")
        elif choice == "2":
            website = input("Enter website: ")
            password = password_manager.get_password(website)
            print(f"Password for {website}: {password}")
        elif choice == "3":
            websites = password_manager.list_websites()
            print("List of websites:")
            for website in websites:
                print(website)
        elif choice == "4":
            print("Exiting Password Manager")
            break
        else:
            print("Invalid choice. Please choose a valid option.")


if __name__ == "__main__":
    main()
