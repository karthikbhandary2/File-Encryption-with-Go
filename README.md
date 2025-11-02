# File Encryption with Go

A simple command-line file encryption tool built in Go that provides secure AES-256-GCM encryption for your files.
## Features

- **AES-256-GCM Encryption**: Uses industry-standard encryption with authenticated encryption
- **PBKDF2 Key Derivation**: Secure password-based key derivation with 4096 iterations
- **Password Confirmation**: Ensures password accuracy during encryption
- **In-place Encryption**: Encrypts files directly, replacing the original content
- **Simple CLI Interface**: Easy-to-use command-line interface

## Security Details

- **Encryption Algorithm**: AES-256 in GCM mode
- **Key Derivation**: PBKDF2 with SHA-1, 4096 iterations
- **Nonce**: 12-byte random nonce generated for each encryption
- **Authentication**: GCM mode provides built-in authentication

## Installation

1. Clone the repository:
```bash
git clone https://github.com/karthikbhandary2/file-encryption.git
cd File-Encryption-with-Go
```

2. Install dependencies:
```bash
go mod tidy
```

## Usage

### Encrypt a File
```bash
go run . encrypt /path/to/your/file
```
You'll be prompted to enter and confirm a password.

### Decrypt a File
```bash
go run . decrypt /path/to/your/encrypted/file
```
You'll be prompted to enter the password used for encryption.

### Help
```bash
go run . help
```

## Examples

```bash
# Encrypt a text file
go run . encrypt document.txt

# Decrypt the encrypted file
go run . decrypt document.txt

# Display help information
go run . help
```

## Building

To build a standalone executable:

```bash
go build -o filecrypt .
```

Then use the executable:
```bash
./filecrypt encrypt myfile.txt
./filecrypt decrypt myfile.txt
```

## Project Structure

```
File-Encryption-with-Go/
├── main.go              # Main application entry point
├── filecrypt/
│   └── filecrypt.go     # Core encryption/decryption logic
├── go.mod               # Go module file
├── go.sum               # Go dependencies checksum
└── README.md            # This file
```

## Dependencies

- `golang.org/x/term` - For secure password input
- Standard Go crypto libraries (AES, PBKDF2, etc.)

## Important Notes

⚠️ **Warning**: This tool encrypts files in-place, meaning the original file content is replaced with encrypted data. Make sure to backup important files before encryption.

⚠️ **Password Recovery**: There is no password recovery mechanism. If you forget your password, the encrypted file cannot be recovered.
