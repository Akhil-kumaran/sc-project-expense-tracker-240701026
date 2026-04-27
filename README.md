# Smart Expense Tracker with Login System using Streamlit

A beginner-friendly full-stack Streamlit mini project for tracking personal expenses with user registration, login, logout, CSV file storage, and dashboard analytics.

## Project Structure

```text
Smart Expense Tracker/
|-- app.py
|-- requirements.txt
|-- csv_structure.md
|-- README.md
|-- data/
|   |-- users.csv
|   |-- expenses.csv
```

The `data` folder and CSV files are created automatically when the app runs.

## Modules Included

- User registration with username, email, and password
- Secure password storage using salted PBKDF2 hashing
- User login using email and password
- Logout using `st.session_state`
- Add expense form with amount, category, description, and date
- CSV file storage using Pandas
- Expense dashboard with table, total amount, transaction count, and highest spending category
- Category-wise analysis with totals, bar chart, and pie chart
- Recent transaction summary
- Error handling for empty fields, duplicate email, incorrect login, invalid expense amount, and no expense data

## CSV File Storage

The application stores data in two CSV files:

```text
data/users.csv
data/expenses.csv
```

### users.csv

```csv
id,username,email,password_hash,salt,created_at
```

This file stores registered user details. Passwords are not saved directly. The app stores a salted hash of each password.

### expenses.csv

```csv
id,user_id,amount,category,description,expense_date,created_at
```

This file stores each expense entry and links it to the logged-in user through `user_id`.

## How to Run in VS Code

1. Open this project folder in VS Code.
2. Open the terminal in VS Code.
3. Create a virtual environment:

```powershell
python -m venv .venv
```

4. Activate the virtual environment:

```powershell
.\.venv\Scripts\Activate.ps1
```

5. Install dependencies:

```powershell
pip install -r requirements.txt
```

6. Run the Streamlit app:

```powershell
streamlit run app.py
```

7. Open the local URL shown in the terminal, usually:

```text
http://localhost:8501
```

## Viva Explanation

This project is a Streamlit-based expense tracker. It uses CSV files as the backend data storage and Streamlit widgets for the frontend interface. New users register with username, email, and password. Passwords are stored securely as salted hashes instead of plain text.

After login, Streamlit `session_state` stores the active user session. The user can add expenses by entering amount, category, description, and date. Expenses are saved in `data/expenses.csv` with the logged-in user's id, so each user sees only their own records.

The dashboard reads the latest CSV data and displays all transactions, total expense, number of transactions, highest spending category, category-wise totals, bar chart, pie chart, and recent transactions. When a new expense is added, the page reruns and the dashboard updates immediately.

## Resume Project Listing

Smart Expense Tracker Dashboard using Python, Streamlit, CSV files, Pandas, and Matplotlib. Implemented user authentication, session management, secure password hashing, expense entry, tabular reports, and category-wise spending analytics.
