
# Student Information CRUD application

## Project Overview
This project demonstrates how to implement CRUD (Create, Read, Update, Delete) operations using C# and SQL Server within a Windows Forms Application. It provides a user-friendly interface for managing student records.

## Key Features
- **User Management**: Add, view, update, and delete user records.
![image](https://github.com/user-attachments/assets/6c19fa54-e979-453c-941d-b030426ed7d8)

## Tools and Technologies
- **C#**: Main programming language for the application.
- **Windows Forms**: Framework for building the desktop application.
- **SQL Server**: Database management system for storing user data.

### Prerequisites

- Visual Studio 2022 or later
- SQL Server (Express or any version)
- SQL Server Management Studio (SSMS)

### Steps
**Create the Database**:
    - Open the `.sql` file located in folder.
    - Copy the queries from the `.sql` file and execute them in your new database to set up the schema and initial data.
    - Use `Ctrl+F` to search for `connectionString` within the project files.
        ```csharp
        private readonly string connectionString = "Server=(localdb)\\login;Database=FinanceTracker;Trusted_Connection=True;";
    - Update this to:
        ```csharp
        private readonly string connectionString = "Server=<YOUR DATABASE SERVER/SOURCE>;Database=<DATABASENAME>;Trusted_Connection=True;";
### C# Code Implementation
#### insert data function sample
```csharp
SqlConnection con = new SqlConnection("Data Source=DESKTOP-JELVURO;Initial Catalog=CRUD_OPERATION;Integrated Security=True");
con.Open();
SqlCommand cmd = new SqlCommand("update ut set name=@name,age=@age where id=@id", con);
cmd.Parameters.AddWithValue("@id", int.Parse(textBox1.Text));
cmd.Parameters.AddWithValue("@name", textBox2.Text);
cmd.Parameters.AddWithValue("@age", double.Parse(textBox3.Text));

cmd.ExecuteNonQuery();
con.Close();

MessageBox.Show("Succesfully Updated");
```
### Event Handling
- Implement event handlers for each button (e.g., `Create`, `Edit`, `Delete`).
- When a button is clicked, the corresponding CRUD operation will be executed (e.g., creating a new record or deleting an existing one).

## User Flow
1. When the application is opened, existing records are displayed in the `DataGridView`.
2. Users can:
   - **Insert** new records by clicking the "Insert" button and submitting the form.
   - **Delete** records by selecting a row and confirming deletion.
   - **Update** user can update any data from data grid view.

## Challenges and Considerations
- **Error Handling**: Implement error handling for database connection failures or invalid inputs.

## **Build and Run the Application**:
    Open the project in Visual Studio, build it, and run the application.

## How to Run the Project
1. **Clone the Repository**: Clone this repository to your local machine.
   ```bash
   git clone https://github.com/maharin-afroj/student-information
   ```
2. **Set Up the Database**: Configure your SQL Server or SQLite database and update the connection according to the `script.sql` file.
3. **Build the Project**: Open the project in Visual Studio and build the solution.
4. **Run the Application**: Once built, run the application and manage records through the Windows Forms interface.
