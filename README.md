# Image Vault
This project is a Python-based tool for encrypting and decrypting image files using AES (Advanced Encryption Standard). It supports AES encryption in CBC mode and includes features for key management, encryption, and decryption. The tool is interactive and stores encryption keys securely in a log file.

## Features

1. **Image Encryption**:
   - Encrypts image files using AES in CBC mode.
   - Generates a random 256-bit key for each encryption.
   - Saves the initialization vector (IV) and encrypted data to a `.bin` file.

2. **Image Decryption**:
   - Decrypts `.bin` files back to their original image format.
   - Retrieves the encryption key from a log file or allows manual key input.

3. **Key Management**:
   - Keys are securely stored in a JSON log file (`key_log.json`).
   - Keys are linked to their corresponding encrypted files for easy retrieval.

4. **Interactive User Prompts**:
   - Guides the user through encryption or decryption processes.

5. **Error Handling**:
   - Handles file reading, encryption, and decryption errors gracefully.

## Requirements

To run this project, you need Python 3.x and the following libraries:

- `pycryptodome`
- `os`
- `json`

You can install `pycryptodome` using pip:

```bash
pip install pycryptodome
```

## Usage

### 1. Clone the Repository

```bash
git clone https://github.com/Dharan10/image_vault.git
cd image_vault
```

### 2. Run the Script

Run the script using Python:

```bash
python image_encryptor.py
```

### 3. Select an Operation

You will be prompted to select an operation:

- **Encrypt an Image**
- **Decrypt an Encrypted Image**

### 4. Encryption Process

1. Provide the name of the image file to encrypt (e.g., `example.jpg`).
2. The script generates a random 256-bit key and saves it in `key_log.json`.
3. The encrypted file is saved as `example.jpg.bin`.
4. The encryption key is displayed in the terminal and stored in the log file.

### 5. Decryption Process

1. Provide the name of the encrypted file (e.g., `example.jpg.bin`).
2. The script retrieves the encryption key from `key_log.json`. If not found, you can input the key manually.
3. Provide the name for the decrypted image (e.g., `decrypted_example.jpg`).
4. The decrypted image is saved with the specified name.

## Example


### Encryption

```bash
Do you want to encrypt or decrypt an image? (encrypt/decrypt): encrypt
Enter the name of the image file to encrypt (with extension): example.jpg
Image successfully encrypted and saved to example.jpg.bin
Key has been saved securely to the log file. And the key is 1234567890abcdef...
```

### Decryption

```bash
Do you want to encrypt or decrypt an image? (encrypt/decrypt): decrypt
Enter the name of the encrypted file (with extension): example.jpg.bin
Enter the name for the output decrypted image (with extension): decrypted_example.jpg
Image successfully decrypted and saved to decrypted_example.jpg
```

## File Structure

```bash
image_encryptor.py      # Main script
key_log.json            # Log file for storing encryption keys
example.jpg             # Original image (input)
example.jpg.bin         # Encrypted file (output)
decrypted_example.jpg   # Decrypted image (output)
```

## Security Notes

- **Key Storage**: Keys are stored in plaintext in `key_log.json`. Ensure the file is protected or implement additional encryption for the log file.
- **Manual Key Input**: If the key is not found in the log, you can manually input it.

## Future Enhancements

1. Encrypt the `key_log.json` file for enhanced security.
2. Add file type validation for input files.
3. Support for encrypting and decrypting other file types.
4. Add command-line arguments for automation.
5. Build a graphical user interface (GUI) for easier use.



