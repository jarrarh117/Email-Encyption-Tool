# Secure Email Encryption Tool

A web-based application that enables end-to-end encrypted email communication using hybrid RSA and AES cryptography. Send secure messages that only intended recipients can decrypt.

## Features

- **Hybrid Encryption**: Combines RSA-2048 and AES-256-GCM for secure and efficient encryption
- **Automatic Key Generation**: RSA key pairs generated automatically during registration
- **User Directory**: Browse registered users and their public keys
- **Gmail Integration**: Seamlessly send encrypted messages via Gmail
- **Client-Side Encryption**: All cryptographic operations performed in the browser using Web Crypto API
- **Secure Authentication**: SHA-256 password hashing with Firebase authentication
- **Real-Time Operations**: Instant encryption and decryption without server-side processing

## How It Works

1. **Registration**: Users create an account with automatic RSA key pair generation
2. **Encryption**: Messages are encrypted with AES-256, then the AES key is encrypted with recipient's RSA public key
3. **Transmission**: Encrypted message and key are sent via email
4. **Decryption**: Recipient uses their private RSA key to decrypt the AES key, then decrypts the message

## Prerequisites

- Node.js (for package management)
- Firebase account and project
- Modern web browser with Web Crypto API support
- XAMPP or similar local server (for development)

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd "Secure Email Encryption Tool/Project"
```

2. Install dependencies:
```bash
npm install
```

3. Set up Firebase:
   - Create a Firebase project at [Firebase Console](https://console.firebase.google.com/)
   - Enable Firestore Database
   - Enable Email/Password authentication
   - Copy your Firebase configuration

4. Configure Firebase:
   - Replace the Firebase configuration in `index.html`, `login.html`, and `signUp.html` with your credentials
   - **Important**: For production, move credentials to environment variables

5. Set up local server:
   - Install XAMPP or similar
   - Place project files in the server directory
   - Start the server

6. Access the application:
   - Open `login.html` in your browser
   - Register a new account or log in

## Usage

### Registration
1. Navigate to the sign-up page
2. Enter username, email, and password
3. RSA key pair is automatically generated and stored

### Sending Encrypted Messages
1. Log in to your account
2. Click "Display Users" to browse registered users
3. Select a recipient or manually enter their email and public key
4. Click "Email Encryption"
5. Compose your message
6. Click "Encrypt & Send" - opens Gmail with encrypted content

### Decrypting Messages
1. Copy the encrypted message and encrypted AES key from received email
2. Click "Email Decryption"
3. Paste encrypted text and key
4. Your private key is auto-filled from local storage
5. Click "Decrypt & Show" to view the original message

## Project Structure

```
Project/
├── index.html          # Main application interface
├── login.html          # User login page
├── signUp.html         # User registration page
├── style.css           # Application styles
├── image.png           # Logo/branding
├── package.json        # Dependencies
└── README.md           # Documentation
```

## Security Features

- **RSA-2048**: Asymmetric encryption for key exchange
- **AES-256-GCM**: Symmetric encryption for message content
- **SHA-256**: Password hashing
- **Web Crypto API**: Browser-native cryptographic operations
- **Local Storage**: Private keys stored client-side only
- **Firebase Security**: Firestore for secure user data management

## Technologies Used

- HTML5, CSS3, JavaScript (ES6+)
- Firebase (Authentication & Firestore)
- Web Crypto API
- CryptoJS (SHA-256 hashing)
- Gmail API integration

## Team Contributions

**Muhammad Jarrar Haider**
- Frontend development
- Firebase configuration and integration
- User authentication (signup/login forms)
- Browser local storage implementation
- UI/UX design and styling

**Muhammad Jarrar Haider**
- Email text encryption implementation
- AES key generation
- AES-GCM encryption/decryption algorithms
- Random key generator integration

**Muhammad Jarrar Haider**
- RSA key pair generation
- Public/private key management
- AES key encryption using RSA public key
- AES key decryption using RSA private key

## Important Notes

⚠️ **Security Warning**: 
- Firebase API keys are currently hardcoded in HTML files
- Before deploying to production, move credentials to environment variables
- Implement Firebase security rules to restrict database access
- Never commit sensitive credentials to version control

⚠️ **Browser Compatibility**:
- Requires modern browser with Web Crypto API support
- Tested on Chrome, Firefox, and Edge

## Future Enhancements

- File attachment encryption
- Group messaging support
- Key rotation and management
- Mobile application
- End-to-end encrypted chat interface
- Multi-factor authentication

## License

This project is for educational purposes. Please ensure compliance with local encryption laws and regulations.

## Support

For issues or questions, please open an issue in the repository or contact the development team.

---

**Note**: This tool is designed for educational purposes to demonstrate cryptographic principles in web applications. For production use, conduct thorough security audits and implement additional security measures.
