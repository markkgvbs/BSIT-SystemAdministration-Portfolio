# Week 1 – Building My Professional Environment

## Student Information
- Name: Mark Give V. De Leon
- Course: BSIT
- Section: 3C
- Date: 8/8/2026

## Objectives
- Install and configure the software tools required for System Administration coursework (Git, GitHub Desktop, VS Code, VirtualBox, and OS installation images).
- Create professional GitHub and LinkedIn accounts to support learning and collaboration throughout the semester.
- Build and organize a GitHub portfolio repository that will hold all weekly laboratory work.
- Publish my first technical documentation using Markdown.
- Practice using Git version control commands (clone, add, commit, push) confidently.

---

## Software Installed
- Git (with Git Bash)
- GitHub Desktop
- Visual Studio Code

---

## Professional Accounts
GitHub: https://github.com/markkgvbs
LinkedIn: https://www.linkedin.com/in/de-leon-mark-give/

Both accounts were set up with a profile photo, bio/headline, and relevant details completed as required.

---

## Installation Screenshots
See the `Week01/screenshots/` folder for screenshots of each installed software, showing the software name/version along with my name in Notepad for verification.

---

## Account Screenshots
See the `Week01/accounts/` folder for screenshots of my completed GitHub and LinkedIn profiles.

---

## Challenges Encountered

1. **Broken paste in Git Bash.** When I first tried pasting a multi-line command, Git Bash added strange escape characters and the command failed to run. I fixed this by typing commands one at a time instead of pasting large blocks, or combining multi-line commands into a single line using semicolons.

2. **Git didn't recognize my identity.** When I tried to commit for the first time, Git gave an "Author identity unknown" error because it didn't know what name and email to attach to my commits (since it's the first time). I resolved this by running `git config --global user.name` and `git config --global user.email` to set my identity for the computer.

3. **GitHub rejected password-based login.** When pushing my code for the first time, GitHub no longer accepts a plain account password through the terminal. I solved this by using the browser-based sign-in method, which opened GitHub in my browser and let me authorize Git directly instead of typing a password.

---

## Reflection

This week I learned the basics of setting up a professional development environment using Git and GitHub, along with creating the accounts and tools a System Administrator relies on daily. At first, the command line felt intimidating, especially when errors showed up that I didn't fully understand, like the identity error or the broken paste issue. Working through each error one at a time helped me realize that most Git problems have a specific, fixable cause, and reading the error message carefully usually points to the solution.

I also learned the difference between a regular repository and a special profile repository, and how a README file inside that repository can act as a public-facing summary of my skills and goals. This was a good introduction to thinking of GitHub not just as a place to store code, but as a professional presence that others, like recruiters or teammates, might actually look at.

Going forward, I think these tools will be essential for a future systems administrator. Version control matters not just for code, but for tracking configuration changes, documentation, and infrastructure setups over time. Being comfortable with the command line, rather than relying only on graphical tools, will also help me troubleshoot systems more efficiently in real environments. I still have some setup left to finish, like VirtualBox and the OS images, but this first week gave me a solid foundation to build on for the rest of the semester.

---

## References
- https://git-scm.com/doc
- https://docs.github.com
