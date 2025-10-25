# Electron Practice Application

A simple Electron desktop application that demonstrates the basic structure and functionality of Electron framework. This application displays the versions of Node.js, Chrome, and Electron being used.

## 🚀 Features

- **Version Display**: Shows current versions of Node.js, Chrome, and Electron
- **Cross-Platform**: Runs on Windows, macOS, and Linux
- **Secure Communication**: Uses context isolation and preload scripts for secure renderer-main communication
- **Modern Architecture**: Implements Electron security best practices

## 📋 Prerequisites

Before running this application, make sure you have the following installed:

- [Node.js](https://nodejs.org/) (version 16 or higher)
- [npm](https://www.npmjs.com/) (comes with Node.js)

## 🛠️ Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/Hemanth42d/electron_js_practice.git
   cd electron_js_practice
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

## 🏃‍♂️ Running the Application

### Development Mode

To run the application in development mode:

```bash
npm start
```

### Building the Application

To package the application:

```bash
npm run package
```

### Creating Distributables

To create installer packages for distribution:

```bash
npm run make
```

This will create platform-specific distributables in the `out/make` directory:

- **Linux**: `.deb` and `.rpm` packages
- **Windows**: Squirrel installer
- **macOS**: `.zip` archive

## 📁 Project Structure

```
electron-practice/
├── main.js              # Main process entry point
├── preload.js           # Preload script for secure communication
├── render.js            # Renderer process script
├── index.html           # Application UI
├── package.json         # Project configuration and dependencies
├── forge.config.js      # Electron Forge configuration
└── README.md           # Project documentation
```

## 🔧 Architecture

### Main Process (`main.js`)

- Creates and manages the application window
- Handles application lifecycle events
- Loads the HTML file and preload script

### Preload Script (`preload.js`)

- Exposes Node.js APIs to the renderer process securely
- Uses `contextBridge` to provide version information

### Renderer Process (`render.js`)

- Handles UI interactions
- Displays version information received from the preload script

### HTML Interface (`index.html`)

- Simple UI with security headers
- Displays application content and version information

## 🔒 Security Features

- **Content Security Policy**: Prevents XSS attacks
- **Context Isolation**: Separates main and renderer contexts
- **Preload Scripts**: Secure communication between processes
- **Disabled Node Integration**: Renderer process runs in secure context

## 📦 Dependencies

### Main Dependencies

- `electron-squirrel-startup`: Handles Squirrel events on Windows

### Development Dependencies

- `electron`: Core Electron framework
- `@electron-forge/cli`: Command-line interface for Electron Forge
- Various Electron Forge makers for different platforms
- Security plugins and fuses for enhanced protection

## 🚀 Scripts

- `npm start`: Start the application in development mode
- `npm run package`: Package the application for distribution
- `npm run make`: Create platform-specific installers

## 🐛 Troubleshooting

### Common Issues

1. **Application doesn't show content**: Ensure `render.js` is properly loaded in `index.html`
2. **Version information not displaying**: Check that the preload script is correctly configured
3. **Build fails with RPM errors**: Install RPM tools on Linux: `sudo apt-get install rpm`
4. **Missing description error**: Ensure `package.json` has a valid description field

### System Requirements

- **Linux**: Requires `rpm` package for creating RPM distributables
- **Windows**: Requires Visual Studio Build Tools for native modules
- **macOS**: Requires Xcode Command Line Tools

## 📝 License

This project is licensed under the ISC License.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes and commit: `git commit -m 'Add feature'`
4. Push to the branch: `git push origin feature-name`
5. Submit a pull request

## 📚 Learn More

- [Electron Documentation](https://www.electronjs.org/docs)
- [Electron Forge Documentation](https://www.electronforge.io/)
- [Electron Security Best Practices](https://www.electronjs.org/docs/tutorial/security)

---

**Author**: [Hemanth42d](https://github.com/Hemanth42d)
**Version**: 1.0.0
