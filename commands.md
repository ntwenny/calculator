-- **Initial Setup** --

# 1. Create a new repository on GitHub (github.com/new)

# - Give it a name (e.g., "calculator")

# - Leave it empty (don't add README, .gitignore, or license)

# 2. Initialize your local folder as a Git repo and then add the downloaded files from this link https://drive.google.com/drive/folders/1QE6YdqnP5uQpCR_UgLb9Ayvc6Y5pO16Q?usp=sharing.

git init

# 3. Add all files to staging

git add .

# 4. Make your first commit

git commit -m "Initial commit"

# 5. Connect to your GitHub repository (replace with your URL)

git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git

# 6. Push to GitHub

git push -u origin main

# Note: If your default branch is "master" instead of "main", use:

# git branch -M main (to rename it to main)

# Then push as above

---

-- **Start** --

# Start on main

git checkout main

# Create new branch

git checkout -b add-subtract

# Add subtract button to calculator.html (after Add button):

# <button onclick="subtract()">Subtract</button>

# Add subtract function to script.js:

# function subtract() {

# const num1 = parseFloat(document.getElementById('num1').value);

# const num2 = parseFloat(document.getElementById('num2').value);

# const result = num1 - num2;

# document.getElementById('result').textContent = 'Result: ' + result;

# }

git add .
git commit -m "Add subtract function"
git push origin add-subtract

-- **Branching and Merge conflicts** --

# Branch 1: Blue theme

git checkout main
git checkout -b blue-theme

# Change h1 color to blue in style.css

git add style.css
git commit -m "Make title blue"

# Merge blue-theme into main locally

git checkout main
git merge blue-theme
git push origin main

# Branch 2: Red theme (this will conflict with blue!)

git checkout -b red-theme

# Change h1 color to red in style.css

git add style.css
git commit -m "Make title red"
git push origin red-theme

# Go to GitHub and create a Pull Request for red-theme -> main

# GitHub will show a merge conflict!

# Click "Resolve conflicts" button

# You'll see something like:

# <<<<<<< red-theme

# color: red;

# =======

# color: blue;

# >>>>>>> main

# Choose one color, remove the conflict markers

# Click "Mark as resolved" then "Commit merge"

# Now you can merge the PR

-- Other commands --

# Start working on multiply feature

git checkout -b add-multiply

# Make changes but DON'T commit

# Add multiply button and function

git status # Shows uncommitted changes

# Stash & stash popping

git stash # Saves your work

git checkout main # Now clean

# Popp stash

git checkout add-multiply
git stash pop # Gets your work back

# Continue and commit

git add .
git commit -m "Add multiply function"

# Create a pull request on github.com

-- **Other good commands to know** --

# See all branches

git branch

# See commit history

git log --oneline

# Undo last commit (keep changes)

git reset --soft HEAD~1

# Undo last commit (delete changes) - BE CAREFUL

git reset --hard HEAD~1

# See what changed

git diff

# Check current status

git status
