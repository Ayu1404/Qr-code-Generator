# **QR Code Generator**

A simple and effective command-line tool that generates QR codes from user-provided URLs. The application uses Node.js and integrates `inquirer` for user input, `qr-image` for QR code generation, and `fs` for file management.

---

## **Features**
- **User Input via Command Line**:
  - Prompts users to input a URL using the `inquirer` package.
- **QR Code Generation**:
  - Converts the entered URL into a QR code image using `qr-image`.
- **File Handling**:
  - Saves the generated QR code as a PNG file.
  - Optionally stores the entered URL in a `.txt` file for future reference (this feature can be extended).

---

## **Technologies Used**
- **Node.js**: JavaScript runtime for executing the application.
- **inquirer**:
  - Used for creating interactive prompts to collect user input.
- **qr-image**:
  - Generates QR codes in various formats, such as PNG and SVG.
- **fs (File System)**:
  - A native Node.js module for handling file input and output operations.

---

## **Getting Started**

### **Prerequisites**
- **Node.js**: Ensure that Node.js is installed on your system.
- **npm**: Comes bundled with Node.js for package management.

---

### **Installation**
1. Clone the repository:
   ```bash
   git clone https://github.com/Ayu1404/QRCode-Generator.git
   cd QRCode-Generator
   ```

2. Install dependencies:
   ```bash
   npm install
   ```
   Ensure the following dependencies are included in your `package.json`:
   - `inquirer`
   - `qr-image`

3. Run the application:
   ```bash
   node index.js
   ```

---

## **How to Use**
1. **Launch the Application**:
   - Run `node index.js` in your terminal.
2. **Enter a URL**:
   - Type the desired URL when prompted (e.g., `https://example.com`).
3. **View the Output**:
   - The application generates a PNG file of the QR code (`URL.png`) in the current directory.

---

## **How It Works**
1. **Collecting User Input**:
   - The `inquirer.prompt()` method displays a message prompting the user to input a URL.
2. **Generating the QR Code**:
   - The input URL is passed to the `qr.image()` function from the `qr-image` package, which creates the QR code.
3. **Saving the QR Code**:
   - The QR code is saved to a file (`URL.png`) in the current directory using the `fs.createWriteStream()` method.

---

## **Example Usage**
### Input:
```bash
Type Your URL: https://example.com
```

### Output:
- Generates a file named `URL.png` in the directory.
- The PNG file contains the QR code for `https://example.com`.

---

## **Error Handling**
- **TTY Error**:
  - Occurs if the prompt cannot be rendered in the terminal environment.
- **Other Errors**:
  - Handles unexpected errors gracefully with fallback logic or informative messages.

---

## **Extending Functionality**
- **URL Logging**:
  - Enhance the application to save user-provided URLs to a `.txt` file for record-keeping.
  - Example:
    ```javascript
    fs.writeFile("URL.txt", URL, (err) => {
      if (err) throw err;
      console.log("The URL has been saved to URL.txt");
    });
    ```
- **Multiple QR Formats**:
  - Extend the functionality to support additional file formats like SVG or PDF.

---

## **Contributing**
Contributions are welcome! To contribute:
1. Fork this repository.
2. Create a new branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. Commit your changes:
   ```bash
   git commit -m "Add your feature"
   ```
4. Push to your branch:
   ```bash
   git push origin feature/your-feature-name
   ```
5. Open a pull request.

---

## **License**
This project is licensed under the MIT License, allowing you to modify and distribute the project with proper attribution.

---

## **Acknowledgments**
- Inspired by the practical need for a simple tool to generate QR codes.
- Thanks to the authors of the `inquirer` and `qr-image` packages for their fantastic open-source contributions.
