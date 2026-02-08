✅ HOW TO RUN THIS PROJECT IN VS CODE (WINDOWS ONLY)

🟢 STEP 1: Install Required Software (One Time Only)
Make sure you have:
✔ Python (3.10+ recommended)
Download from:
👉 https://www.python.org/downloads/windows/

⚠️ During install:
✅ Check “Add Python to PATH”

✔ VS Code
Download:
👉 https://code.visualstudio.com/

Install normally.
✔ VS Code Python Extension


Open VS Code → Extensions (Ctrl+Shift+X)
Search: Python → Install (by Microsoft)

🟢 STEP 2: Extract Project ZIP
Right-click ZIP → Extract All
Move folder to Desktop (recommended)

You should have:
Desktop\Onion_Ventilation_ML_Project

🟢 STEP 3: Open Project in VS Code
Open VS Code
Click File → Open Folder

Select:
Desktop\Onion_Ventilation_ML_Project


Click Select Folder
Now whole project appears in left panel.

🟢 STEP 4: Open VS Code Terminal

Press:
        Ctrl + `   (backtick key under Esc)
OR
Menu → Terminal → New Terminal

You will see:
PS C:\Users\...\Onion_Ventilation_ML_Project>

🟢 STEP 5: Create Virtual Environment
In terminal:
python -m venv venv

Wait.

🟢 STEP 6: Activate Virtual Environment
Run:
venv\Scripts\activate

You should see:
(venv) PS C:\Users\...\Onion_Ventilation_ML_Project>

If you see (venv) → success ✅

🟢 STEP 7: Install Dependencies
Run:
pip install -r requirements.txt

Wait till done.

🟢 STEP 8: Select Python Interpreter in VS Code (Important)
Press:
Ctrl + Shift + P

Type:
Python: Select Interpreter

Choose:
venv\Scripts\python.exe
This links VS Code to your environment.

🟢 STEP 9: Go to Code Folder

In terminal:
cd Code

Now:
(venv) PS ...\Onion_Ventilation_ML_Project\Code>

🟢 STEP 10: Run Prediction Program
Run:
python predict.py

Output:
Predicted Speed: 3
✅ Project working.

🟢 STEP 11: Edit Input (Optional)
Open:
Code\predict.py

Change:
predict_speed(920, 42, 48, 75, 82)

Put your own values.
Save → Run again.

🟢 STEP 12: Stop Environment (After Use)
When finished:
deactivate



✅ ALL COMMANDS (COPY VERSION)
1)cd Desktop\Onion_Ventilation_ML_Project
2)python -m venv venv
3)venv\Scripts\activate
4)pip install -r requirements.txt
5)cd Code
6)python predict.py