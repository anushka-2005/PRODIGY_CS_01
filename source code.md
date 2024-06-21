def caesar_cipher_encrypt(text, shift):
    encrypted_text = ""
    for char in text:
        if char.isalpha():
            shift_amount = shift % 26
            if char.islower():
                encrypted_text += chr((ord(char) - ord('a') + shift_amount) % 26 + ord('a'))
            elif char.isupper():
                encrypted_text += chr((ord(char) - ord('A') + shift_amount) % 26 + ord('A'))
        else:
            encrypted_text += char
    return encrypted_text

def caesar_cipher_decrypt(text, shift):
    decrypted_text = ""
    for char in text:
        if char.isalpha():
            shift_amount = shift % 26
            if char.islower():
                decrypted_text += chr((ord(char) - ord('a') - shift_amount) % 26 + ord('a'))
            elif char.isupper():
                decrypted_text += chr((ord(char) - ord('A') - shift_amount) % 26 + ord('A'))
        else:
            decrypted_text += char
    return decrypted_text

def main():
    while True:
        print("Caesar Cipher Program")
        print("1. Encrypt")
        print("2. Decrypt")
        print("3. Exit")
        choice = input("Choose an option (1/2/3): ")

        if choice == '1':
            text = input("Enter the message to encrypt: ")
            shift = int(input("Enter the shift value: "))
            encrypted_text = caesar_cipher_encrypt(text, shift)
            print("Encrypted Message: ", encrypted_text)
        elif choice == '2':
            text = input("Enter the message to decrypt: ")
            shift = int(input("Enter the shift value: "))
            decrypted_text = caesar_cipher_decrypt(text, shift)
            print("Decrypted Message: ", decrypted_text)
        elif choice == '3':
            break
        else:
            print("Invalid choice. Please try again.")

if _name_ == "_main_":
    main()
