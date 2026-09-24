# A02 – How to Use Git, WebStorm, and GitHub

Author: Ahabab Chowdhury (UCID: ac2788)<br>
Course: IS 117<br>
**Repository** link: https://github.com/ac2788/A02

This tutorial shows a beginner how to install **Git**, set up the WebStorm editor, create a **GitHub** account, and use them together to save and share code. Words in bold are defined in the Glossary at the end.

---

## Part 1: Directions on Using Git, WebStorm, and GitHub

### Step 1: Install Git

1. Go to https://git-scm.com/downloads and download **Git** for your operating system (Windows, macOS, or Linux).
2. Run the installer. On Windows, the default options are fine. Leave "Git from the command line and also from 3rd-party software" selected so WebStorm can find **Git**.
3. Check that it installed. Open a terminal (Command Prompt, PowerShell, or Terminal on Mac) and type:
   ```
   git --version
   ```
   You should see something like `git version 2.x.x`.
4. Tell **Git** who you are. Use the same email you will use for **GitHub**:
   ```
   git config --global user.name "Your Name"
   git config --global user.email "you@example.com"
   ```

### Step 2: Create a GitHub Account

1. Go to https://github.com/signup.
2. Enter your email, create a password, and pick a username. For this class, use your UCID as your username (for example, `ac2788`).
3. Verify your email address.
4. (Optional) Students can get free extra features through the GitHub Student Developer Pack at https://education.github.com/pack.

### Step 3: Install WebStorm

1. Go to https://www.jetbrains.com/webstorm/download/ and download WebStorm.
2. WebStorm is free for non-commercial use. Students can also get a free license for all JetBrains tools at https://www.jetbrains.com/community/education/#students by signing up with their school email.
3. Run the installer and open WebStorm.
4. Connect WebStorm to **GitHub**: go to `File > Settings > Version Control > GitHub` (on Mac: `WebStorm > Settings`), click `+`, choose "Log In via GitHub", and approve the login in your browser.
5. Make sure WebStorm sees **Git**: go to `Settings > Version Control > Git` and click "Test". It should show your **Git** version.

### Step 4: Create a Repository on GitHub

1. Log in to **GitHub** and click the `+` icon in the top-right corner, then "New repository".
2. For "Repository name", type `A02`. Use a capital A. The name is case-sensitive.
3. Choose "Public".
4. Check "Add a README file".
5. Click "Create repository". Your **repository** is now at `https://github.com/yourUCID/A02`.

### Step 5: Clone the Repository into WebStorm

To **clone** means to download a full copy of the **repository** to your computer.

1. On your **repository** page on **GitHub**, click the green "Code" button and copy the HTTPS URL (for example, `https://github.com/ac2788/A02.git`).
2. In WebStorm, go to `File > New > Project from Version Control` (or click "Get from VCS" on the Welcome screen).
3. Paste the URL, choose a folder on your computer, and click "Clone".
4. WebStorm opens the project. The **GitHub** copy is now set up as the **remote** named `origin`.

You can also **clone** from the terminal:
```
git clone https://github.com/ac2788/A02.git
```

### Step 6: Make Changes and Commit

1. In WebStorm, open `README.md` and make your edits. Changed files turn blue in the Project panel.
2. Open the Commit window: `Git > Commit` (or press `Ctrl+K` on Windows / `Cmd+K` on Mac).
3. Check the boxes next to the files you want to include.
4. Write a clear **commit** message that says what you did, for example:
    - `Task: Create Repository`
    - `Feature: added workflow for using github`
    - `Fix: changed readme.md for definition of terms`
5. Click "Commit". This saves a snapshot of your changes in your local **repository** only.

Terminal version:
```
git add README.md
git commit -m "Feature: added workflow for using github"
```

### Step 7: Push Your Changes to GitHub

A **push** sends your local **commit** history up to the **remote** **repository** on **GitHub**.

1. In WebStorm, go to `Git > Push` (or press `Ctrl+Shift+K` / `Cmd+Shift+K`).
2. Review the list of commits and click "Push".
3. Refresh your **repository** page on **GitHub**. Your changes and **commit** message should appear.

Tip: In the Commit window you can click "Commit and Push" to do Steps 6 and 7 at once.

Terminal version:
```
git push origin main
```

### Step 8: Fetch and Pull Changes

If you edit files on the **GitHub** website or on another computer, you need to bring those changes down.

1. **Fetch** checks the **remote** for new commits without changing your files: `Git > Fetch`.
2. **Pull** downloads the new commits and combines them into your files: `Git > Pull` (or `Ctrl+T` / `Cmd+T` to "Update Project").

Terminal version:
```
git fetch origin
git pull origin main
```

Always **pull** before you start working so your copy is up to date.

### Step 9: Work with Branches

A **branch** lets you work on a new feature without changing the main version of your project.

1. In WebStorm, click the **branch** name in the bottom-right corner (or top-left in the new UI), then "New Branch".
2. Name it something clear, like `add-glossary`, and click "Create".
3. Make your changes, **commit**, and **push** the new **branch** to **GitHub**.
4. When the work is done, switch back to `main`, then open the **branch** menu, select `add-glossary`, and choose "Merge into Current". This will **merge** your work into `main`.
5. **Push** `main` to **GitHub**.

On **GitHub**, you can also **merge** a **branch** by opening a Pull Request and clicking "Merge pull request".

Terminal version:
```
git checkout -b add-glossary
git add .
git commit -m "Feature: added glossary"
git push origin add-glossary
git checkout main
git merge add-glossary
git push origin main
```

### Step 10: Fix a Merge Conflict

A **merge conflict** happens when two people (or two branches) change the same line of a file differently, and **Git** can't decide which version to keep.

1. When WebStorm finds a **merge conflict**, it opens a Conflicts window. Click "Merge...".
2. WebStorm shows three panels: your version (left), the result (middle), and the incoming version (right).
3. Click the arrows to accept the changes you want, or type the correct text in the middle panel.
4. Click "Apply", then **commit** the fixed file.

In a plain text editor, a conflict looks like this:
```
<<<<<<< HEAD
Your version of the line
=======
The other version of the line
>>>>>>> add-glossary
```
Delete the markers, keep the correct text, save, then **commit**.

### Step 11: Submit the Assignment

1. Make sure all your commits have been pushed and appear on **GitHub**.
2. Copy your **repository** URL: `https://github.com/ac2788/A02`.
3. Paste the link into the Canvas assignment and submit.

---

## Part 2: Glossary