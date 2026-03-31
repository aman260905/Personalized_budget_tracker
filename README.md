# personalized_budget_tracker

# 1. Data Persistence (The Storage Engine)

Instead of losing your data every time you close the program, the code uses the csv module to create a "permanent" record.
* **Initialization:** It checks if budget_data.csv exists. If not, it creates it and adds headers (Category, Amount).
* **Appending:** Every time you add an expense, it "writes" a new row to that file, meaning your data survives a computer restart.

# 2. Descriptive Statistics (The "Math" Layer)
The calculate_stats method performs manual data aggregation. Since you aren't using pandas, it loops through the file and calculates:
* **The Mean(μ):** The average cost of your purchases (Total / Count).
* **Variance & Standard Deviation (σ):** It calculates how much your individual spending fluctuates from the average.
* Example: If you always spend $10, your deviation is low. If you spend $1 one day and $100 the next, your "Volatility" score will be high, alerting you to inconsistent habits.

# 3. Logical Decision Making (The "Advisor")
The provide_logic_advice function uses Conditional Logic to evaluate your status. It takes your user-defined budget_limit and compares it to your total spending
* Safe Zone: If spending < 80% of limit.
* Warning Zone: If spending is between 80% and 100%.
* Critical Zone: If spending > 100%.

# 4. User Interaction (The "Loop")
The while True loop in the main() function keeps the program running. It provides a menu-driven interface, allowing you to cycle through tasks (Add, View, Exit) until you explicitly choose to quit.

# Installation & Setup Guide
* Step 1: Prerequisites Before running the project, ensure you have Python installed on your systemVersion:  
Python 3.6 or higher is recommended.
* Check Installation: Open your Terminal (Mac/Linux) or Command Prompt (Windows) and type:    
python--version

# Step 2: Project Setup
You can set up the project in one of two ways:

* Option A: Using Git (Recommended for GitHub submission)   

  1) Open your terminal.

  2) Clone this repository (https://github.com/aman260905/Personalized_budget_tracker.git):   
     git clone https://github.com/aman260905/Personal_Budget_tracker.git
  3) Enter the project folder:   
  cd Personal-Budget-Manager
* Option B: Manual Download

  Create a new folder on your computer named BudgetManager.

  Save the Python code I provided into a file named main.py inside that folder.

# Step 3: Running the Application
Navigate to the folder where main.py is located and run:

python main.py
# Step 4: Understanding the File Output
Once you run the program and add your first expense, the application will automatically generate a file in the same directory:

* **budget_data.csv:** This is your database. You can open this file with Excel, Notepad, or TextEdit to see your raw data, but the Python script will manage it for you.
