
# Import SQL File into MySQL Using Laragon Terminal

This guide explains how to create a database in MySQL and import an SQL file into it using Laragon's terminal for quick setup.

---

## **Steps to Import SQL File**

### **1. Create a Database in MySQL**
1. Open the **Laragon Terminal** or any terminal of your choice.
2. Access MySQL:
   ```bash
   mysql -u root -p
   ```
   - You will be prompted to enter your MySQL root password. Press **Enter** if no password is set.

3. Once logged into MySQL, create a database:
   ```sql
   CREATE DATABASE database_name;
   ```
   Replace `database_name` with the name of your desired database.

4. Exit MySQL:
   ```sql
   exit;
   ```

---

### **2. Prepare for Quick Import**
- Place your SQL file in the **C:\** drive for easier access. For example: `C:\file.sql`.

---

### **3. Import the SQL File**
1. Open the **Laragon Terminal** or redirect to the terminal start option from Laragon.
2. Run the following command to import the SQL file:
   ```bash
   mysql -u root -p database_name < C:\file.sql
   ```
   - Replace `database_name` with the name of the database you created.
   - Replace `C:\file.sql` with the actual path to your SQL file (ensure it’s on the C: drive).

---

### **4. Verify the Import**
1. Log back into MySQL:
   ```bash
   mysql -u root -p
   ```
2. Use the database:
   ```sql
   USE database_name;
   ```
3. Check if the tables are imported successfully:
   ```sql
   SHOW TABLES;
   ```

---

## **Tips**
- If your SQL file is large, ensure the MySQL configuration (`my.ini`) has sufficient limits set for:
  - `max_allowed_packet`
  - `innodb_log_file_size`

- For paths with spaces, enclose the file path in double quotes:
  ```bash
  mysql -u root -p database_name < "C:/My Folder/file.sql"
  ```

---

## **Example**
If your SQL file is named `example.sql` and the database name is `my_database`, the command will look like this:
```bash
mysql -u root -p my_database < C:\example.sql
```

---

### Author
[Your Name] - A quick and efficient guide for setting up MySQL databases in Laragon.
