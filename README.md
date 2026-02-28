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
