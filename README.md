# Training Schedule Management System

## Overview
The **Training Schedule Management System** is a C++ console-based application designed to manage training schedules for administrators and faculty members. The system provides separate login functionalities for admins and faculty, allowing them to access specific modules after authentication. Admins log in with hardcoded credentials, while faculty credentials are verified against a CSV file (`facultyLogin.csv`). The system includes basic input validation and a limited number of login attempts for security.

## Features
- **Admin Login**: Authenticate using a predefined username (`admin`) and password (`12345`) to access admin-specific modules.
- **Faculty Login**: Authenticate using credentials stored in a CSV file (`facultyLogin.csv`) to access faculty-specific modules.
- **Input Validation**: Handles invalid input (e.g., non-numeric choices) and limits login attempts to three before denying access.
- **Modular Design**: Separate header files (`adminLogin.h`, `facultyLogin.h`) for admin and faculty functionalities.
- **Exit Option**: Allows users to exit the application gracefully.

## Prerequisites
- **C++ Compiler**: GCC or any C++11 compatible compiler.
- **Operating System**: The code references a file path (`/Users/KI20449224/Downloads/Project_Flies/data/facultyLogin.csv`), which is specific to a macOS environment. Modify the path for other operating systems.
- **CSV File**: A `facultyLogin.csv` file containing faculty credentials in the format: `username,password,technology`.

## Installation
1. **Clone or Download the Project**:
   - Download the project files to your local machine.
   - Ensure the `adminLogin.h` and `facultyLogin.h` header files are in the same directory as the main source file.

2. **Set Up the CSV File**:
   - Create a `facultyLogin.csv` file in the appropriate directory (e.g., `/Users/KI20449224/Downloads/Project_Flies/data/`).
   - Example content for `facultyLogin.csv`:
     ```
     faculty1,pass123,Java
     faculty2,pass456,Python
     ```

3. **Compile the Code**:
   - Open a terminal in the project directory.
   - Compile the code using a C++ compiler, e.g.:
     ```bash
     g++ main.cpp -o training_system
     ```

4. **Run the Application**:
   - Execute the compiled program:
     ```bash
     ./training_system
     ```

## Usage
1. **Launch the Application**:
   - Run the program to display the home page with three options:
     - `1`: Admin Login
     - `2`: Faculty Login
     - `3`: Exit

2. **Admin Login**:
   - Enter the username: `admin`
   - Enter the password: `12345`
   - On successful login, the admin modules are accessed (defined in `adminLogin.h`).
   - Incorrect credentials prompt the user to try again (up to three attempts).

3. **Faculty Login**:
   - Enter the username, password, and technology name as stored in `facultyLogin.csv`.
   - On successful login, the faculty modules are accessed (defined in `facultyLogin.h`).
   - Incorrect credentials prompt the user to try again (up to three attempts).

4. **Exit**:
   - Select option `3` to exit the application.

## File Structure
```
Training_Schedule_Management_System/
├── main.cpp                # Main source file with login logic
├── adminLogin.h            # Header file for admin functionalities
├── facultyLogin.h          # Header file for faculty functionalities
├── data/
│   └── facultyLogin.csv    # CSV file storing faculty credentials
└── README.md               # This file
```

## Notes
- **File Path**: Update the file path in the `facultyLogin()` function to match your system's directory structure.
- **Security**: The admin credentials are hardcoded for simplicity. In a production environment, consider using a secure method for storing and verifying credentials.
- **Error Handling**: The program handles invalid input for menu choices and limits login attempts to prevent unauthorized access.
- **Dependencies**: The application assumes the existence of `admin` and `faculty` classes with methods `adminModules()` and `facultyModules()` defined in the respective header files.

## Limitations
- The admin login uses hardcoded credentials, which is not secure for real-world applications.
- The faculty login relies on a local CSV file, which must be properly formatted and accessible.
- The program uses recursive calls to `main()` for retrying login, which is not ideal. Consider using loops for better control flow.
- The file path for `facultyLogin.csv` is hardcoded and specific to a single system.

## Future Improvements
- Implement secure credential storage (e.g., encrypted files or a database).
- Replace recursive `main()` calls with a loop-based control structure.
- Add support for dynamic file path configuration.
- Enhance input validation for faculty login (e.g., handle spaces or special characters).
- Add password masking for secure input.

## Contributing
Contributions are welcome! Please submit pull requests or open issues for bugs, improvements, or new features.

## License
This project is licensed under the MIT License.
