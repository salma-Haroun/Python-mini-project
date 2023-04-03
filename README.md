# Python-mini-project
import random
import string

def generate_password(length, uppercase, lowercase, numbers, special_characters):
    characters = ''
    if uppercase:
        characters += string.ascii_uppercase
    if lowercase:
        characters += string.ascii_lowercase
    if numbers:
        characters += string.digits
    if special_characters:
        characters += string.punctuation
    password = ''.join(random.choice(characters) for i in range(length))
    return password

def main():
    while True:
        length = int(input("Enter password length (8-20): "))
        if length < 8 or length > 20:
            print("Invalid length! Length should be between 8 and 20.")
            continue
        uppercase = input("Include uppercase letters? (y/n): ").lower() == 'y'
        lowercase = input("Include lowercase letters? (y/n): ").lower() == 'y'
        numbers = input("Include numbers? (y/n): ").lower() == 'y'
        special_characters = input("Include special characters? (y/n): ").lower() == 'y'
        password = generate_password(length, uppercase, lowercase, numbers, special_characters)
        print("Your password is:", password)
        choice = input("Generate another password? (y/n): ").lower()
        if choice == 'n':
            break

if __name__ == '__main__':
    main()
