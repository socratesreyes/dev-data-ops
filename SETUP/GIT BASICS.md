# 1. Initialize a blank Git repository in this folder
git init

# 2. Add all files in the folder to the staging area
git add .

# 3. Create your first commit with a message
git commit -m "Initial commit of public cheat sheets"

# 4. Rename your default branch to 'main' (GitHub standard)
git branch -M main

# 5. Link your local repository to your remote GitHub repository
# (Replace the URL with your actual GitHub repository URL)
git remote add origin https://github.com

# 6. Push your code to GitHub and set the default upstream branch
git push -u origin main
