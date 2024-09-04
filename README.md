
import random
import string

def generate_password(length):
    characters = string.ascii_letters + string.digits + string.punctuation
    return ''.join(random.choice(characters) for _ in range(length))

def main():
    while True:
        try:
            length = int(input("Enter the desired length of the password (min 8): "))
            if length < 8:
                print("Password length must be at least 8 characters.")
            else:
                break
        except ValueError:
            print("Invalid input. Please enter a positive integer.")

    password = generate_password(length)
    print("Generated Password:", password)

if __name__ == "__main__":
    main()
  


