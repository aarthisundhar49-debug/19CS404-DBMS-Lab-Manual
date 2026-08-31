# Experiment 8: PL/SQL Cursor Programs

## AIM
To write and execute PL/SQL programs using cursors and exception handling to manage runtime errors effectively and display appropriate messages.

## THEORY

In PL/SQL, cursors are used to handle query result sets row-by-row. 

There are two types of cursors:

- Implicit Cursors: Automatically created by PL/SQL for single-row queries.
- Explicit Cursors: Declared and controlled by the programmer for multi-row queries.

Types of Explicit Cursors:

1. Simple Cursor: Basic cursor to iterate over multiple rows.

2. Parameterized Cursor: Accepts parameters to filter the result dynamically.

3. Cursor FOR Loop: Simplifies cursor operations (open, fetch, close).

4. %ROWTYPE Cursor: Fetches entire row into a record using %ROWTYPE.

5. Cursor with FOR UPDATE: Used for row-level locking and updating the rows while looping.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:

- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

**Exception Handling**

PL/SQL provides a robust mechanism to handle runtime errors using exception handling blocks. When an error occurs during execution, control is passed to the EXCEPTION section, where specific or general errors can be handled gracefully.

### Components of Exception Handling:
- Predefined Exceptions: Automatically raised by PL/SQL for common errors (e.g., NO_DATA_FOUND, TOO_MANY_ROWS, ZERO_DIVIDE).
- User-defined Exceptions: Declared explicitly in the declaration section using the EXCEPTION keyword.
- WHEN OTHERS: A generic handler for all exceptions not handled explicitly.

```sql
BEGIN
   -- Statements
EXCEPTION
   WHEN exception_name THEN
      -- Handling code
   WHEN OTHERS THEN
      -- Handling for unknown errors
END;
```

### **Question 1: Simple Cursor with Exception Handling**

**Write a PL/SQL program using a simple cursor to fetch employee names and designations from the `employees` table. Implement exception handling for the following cases:**

1. **NO_DATA_FOUND**: When no rows are fetched.
2. **OTHERS**: Any other unexpected errors during execution.

**Steps:**

- Create an `employees` table with fields `emp_id`, `emp_name`, and `designation`.
- Insert some sample data into the table.
- Use a simple cursor to fetch and display employee names and designations.
- Implement exception handling to catch the relevant exceptions and display appropriate messages.
<img width="630" height="637" alt="image" src="https://github.com/user-attachments/assets/8f62a8bd-2db0-4c4b-875b-805742c17a48" />

**Output:**  
The program should display the employee details or an error message.
<img width="352" height="122" alt="image" src="https://github.com/user-attachments/assets/ebe04c36-20ce-445f-b2c1-56d6b2039647" />

---

### **Question 2: Parameterized Cursor with Exception Handling**

**Write a PL/SQL program using a parameterized cursor to retrieve and display employees with a salary in a given range. Implement exception handling for the following errors:**

1. **NO_DATA_FOUND**: When no employees meet the salary criteria.
2. **OTHERS**: For any unexpected errors during the execution.

**Steps:**

- Modify the `employees` table by adding a `salary` column.
- Insert sample salary values for the employees.
- Use a parameterized cursor to accept a salary range as input and fetch employees within that range.
- Implement exception handling to catch and display relevant error messages.
<img width="386" height="573" alt="image" src="https://github.com/user-attachments/assets/dc7661d4-915c-44e4-9755-064993ca18fc" />

**Output:**  
The program should display the employee details within the specified salary range or an error message if no data is found.
<img width="377" height="132" alt="image" src="https://github.com/user-attachments/assets/68fafd75-eb89-442d-bcde-8a5e691c0cc6" />

---

### **Question 3: Cursor FOR Loop with Exception Handling**

**Write a PL/SQL program using a cursor FOR loop to retrieve and display all employee names and their department numbers from the `employees` table. Implement exception handling for the following cases:**

1. **NO_DATA_FOUND**: If no employees are found in the database.
2. **OTHERS**: For any other unexpected errors.

**Steps:**

- Modify the `employees` table by adding a `dept_no` column.
- Insert sample department numbers for employees.
- Use a cursor FOR loop to fetch and display employee names along with their department numbers.
- Implement exception handling to catch the relevant exceptions.
<img width="585" height="696" alt="image" src="https://github.com/user-attachments/assets/5ecb3a4a-0172-4812-824a-1fc09cfc6f2b" />

**Output:**  
The program should display employee names with their department numbers or the appropriate error message if no data is found.
<img width="338" height="117" alt="image" src="https://github.com/user-attachments/assets/7e94625e-655a-497d-8178-e641bf746d8b" />

---

### **Question 4: Cursor with `%ROWTYPE` and Exception Handling**

**Write a PL/SQL program that uses a cursor with `%ROWTYPE` to fetch and display complete employee records (emp_id, emp_name, designation, salary). Implement exception handling for the following errors:**

1. **NO_DATA_FOUND**: When no employees are found in the database.
2. **OTHERS**: For any other errors that occur.

**Steps:**

- Modify the `employees` table by adding `emp_id`, `emp_name`, `designation`, and `salary` fields.
- Insert sample data into the `employees` table.
- Declare a cursor using `%ROWTYPE` to fetch complete rows from the `employees` table.
- Implement exception handling to catch the relevant exceptions and display appropriate messages.
<img width="572" height="678" alt="image" src="https://github.com/user-attachments/assets/7fb1d641-36d7-4fcc-8b11-def78e7fd68a" />

**Output:**  
The program should display employee records or the appropriate error message if no data is found.
<img width="318" height="130" alt="image" src="https://github.com/user-attachments/assets/e970654a-fe64-4260-80a2-cb8a7fd11cc1" />

---

### **Question 5: Cursor with FOR UPDATE Clause and Exception Handling**

**Write a PL/SQL program using a cursor with the `FOR UPDATE` clause to update the salary of employees in a specific department. Implement exception handling for the following cases:**

1. **NO_DATA_FOUND**: If no rows are affected by the update.
2. **OTHERS**: For any unexpected errors during execution.

**Steps:**

- Modify the `employees` table to include a `dept_no` and `salary` field.
- Insert sample data into the `employees` table with different department numbers.
- Use a cursor with the `FOR UPDATE` clause to lock the rows of employees in a specific department and update their salary.
- Implement exception handling to handle `NO_DATA_FOUND` or other errors that may occur.
<img width="711" height="823" alt="image" src="https://github.com/user-attachments/assets/065ae271-3a82-4230-ae91-6e7afa59320a" />

**Output:**  
The program should update employee salaries and display a message, or it should display an error message if no data is found.
<img width="305" height="75" alt="image" src="https://github.com/user-attachments/assets/98a19fc3-7742-47c1-bbf5-956ce9d4d8c6" />

---

## RESULT
Thus, the program successfully executed and displayed employee details using a cursor. 

