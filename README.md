# User Registry Script

A simple Bash script that collects and stores user registration information.

## Features

- Prompts for user details: Full Name, Department, Employee ID, and Access Level
- Displays a registration summary in the terminal
- Saves the registration record to a dated text file (`user_registry_YYYYMMDD.txt`)

## Usage

1. Make the script executable:

   ```bash
   chmod +x Script
   ```

2. Run the script:

   ```bash
   ./Script
   ```

3. Follow the prompts to enter:
   - **Full Name**
   - **Department**
   - **Employee ID**
   - **Access Level** (`Admin`, `User`, or `Guest`)

## Output

A registration record file is created in the current directory named after today's date, for example:

```
user_registry_20260228.txt
```

The file contains all entered details along with the registration timestamp.

## Requirements

- Bash shell

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/CyberPon/user_registry.sh.git
   ```

2. Navigate to the directory:

   ```bash
   cd user_registry.sh
   ```

3. Make the script executable:

   ```bash
   chmod +x Script
   ```

## Examples

### Running the Script

```bash
./Script
```

### Sample Input

```
========================================
      USER REGISTRATION SYSTEM
========================================

Enter Full Name: Jane Doe
Enter Department: Engineering
Enter Employee ID: EMP-1042
Enter Access Level (Admin/User/Guest): Admin
```

### Console Output

```
========================================
         REGISTRATION SUMMARY
========================================
Full Name: Jane Doe
Department: Engineering
Employee ID: EMP-1042
Access Level: Admin
Registration Date: 2026-02-28 10:35:00
========================================

✅ Registration saved to: user_registry_20260228.txt
```

### Resulting File Content (`user_registry_20260228.txt`)

```
=======================================
      USER REGISTRATION RECORD
=======================================
Full Name: Jane Doe
Department: Engineering
Employee ID: EMP-1042
Access Level: Admin
Registration Date: 2026-02-28 10:35:00
=======================================
```

## Troubleshooting

**Permission denied when running the script**

Make sure the script has execute permissions:
```bash
chmod +x Script
```

**Command not found (`bash: ./Script: No such file or directory`)**

Ensure you are in the correct directory and the file named `Script` exists:
```bash
ls -la Script
```

**File creation problems (output file not created)**

Check that you have write permissions in the current directory:
```bash
ls -la .
```
If not, run the script from a directory where you have write access, or change the ownership/permissions of the target directory.

**Date formatting issues on different systems**

The script uses `date '+%Y-%m-%d %H:%M:%S'` which is compatible with GNU `date` (Linux) and BSD `date` (macOS). If you encounter unexpected output, verify your system's `date` command supports this format:
```bash
date '+%Y-%m-%d %H:%M:%S'
```

## Security & Best Practices

**Input validation**

The current script does not validate user input. Consider adding checks to ensure:
- `Employee ID` follows an expected format (e.g., `EMP-XXXX`).
- `Access Level` is one of the allowed values (`Admin`, `User`, or `Guest`).

Example validation snippet:
```bash
if [[ ! "$ACCESS_LEVEL" =~ ^(Admin|User|Guest)$ ]]; then
  echo "Invalid Access Level. Please enter Admin, User, or Guest."
  exit 1
fi
```

**File permissions**

The output file is created with default permissions. To restrict access:
```bash
chmod 600 "$FILENAME"
```

**Data privacy**

Registration records contain personally identifiable information (PII). Store the output files in a secure, access-controlled location and avoid committing them to version control. Add the pattern to `.gitignore`:
```
user_registry_*.txt
```

**Future enhancements**

- Validate Employee ID format before saving.
- Restrict Access Level to predefined options using a select menu.
- Append multiple registrations to a single file rather than one file per day.
- Encrypt the output file for sensitive environments.

## License

This project does not currently include a LICENSE file. Please add one (e.g., MIT, Apache 2.0) to clarify the terms under which the code may be used, modified, and distributed.
