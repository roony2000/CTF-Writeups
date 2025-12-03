📝 Writeup: Information Disclosure in Version Control History (PortSwigger Lab)
Summary

This lab demonstrates how exposing the .git directory can lead to severe information disclosure. By downloading the victim application's Git repository and reviewing its commit history, it was possible to recover a previously hard-coded administrator password. Using this leaked credential, I logged into the admin panel and deleted the user carlos, successfully completing the lab.

Steps to Reproduce
1. Discover the exposed .git directory

Browsing to:

https://<LAB-ID>.web-security-academy.net/.git/

2. Download the entire repository

Using wget to recursively download the .git directory:

wget -r https://<LAB-ID>.web-security-academy.net/.git/

This retrieved all Git objects, logs, and history.

3. Navigate into the downloaded folder

cd <LAB-ID>.web-security-academy.net

Verify the .git directory is present.

4. Explore the Git history

Using:
git log --oneline

A commit stood out:
Remove admin password from config

5. Inspect the commit diff to find the leaked password

git show <COMMIT-SHA>

The diff revealed:

-ADMIN_PASSWORD=hardcoded_password_here
+ADMIN_PASSWORD=env('ADMIN_PASSWORD')


The removed line (starting with -) contained the original hard-coded admin password.

6. Log in as the administrator

Navigating to the login page and signing in with:

Username: administrator
Password: <leaked-password>

Use environment variables or secret managers for sensitive data

Conclusion

By exploiting an exposed .git directory, I was able to reconstruct the application's Git repository, recover a leaked admin password from the commit history, log into the admin panel, and complete the objective of deleting the user carlos.

Lab successfully solved. 🎉

