# PasswordGeneratorimport string
import random

def generate_password(length):
    # Define the character sets to choose from
    lower = string.ascii_lowercase
    upper = string.ascii_uppercase
    digits = string.digits
    symbols = string.punctuation

    # Combine all character sets
    all_characters = lower + upper + digits + symbols

    # Generate a password by randomly selecting characters from the combined set
    password = ''.join(random.choice(all_characters) for _ in range(length))

    return password

def main():
    # Prompt the user to specify the desired length of the password
    while True:
        try:
            length = int(input("Enter the desired length of the password: "))
            if length <= 0:
                raise ValueError("The length must be a positive integer.")
            break
        except ValueError as e:
            print(f"Invalid input: {e}. Please enter a positive integer.")

    # Generate and display the password
    password = generate_password(length)
    print(f"Generated Password: {password}")

if __name__ == "__main__":
    main()
