.. title: blog2025 technical notes
.. slug: blog2025-technical-notes
.. date: 2025-04-16
.. tags: nikola, python, blog
.. author: Aubrey Moore
.. category: nikola

## Nikola installation
Nikola was installed following directions at <https://getnikola.com/getting-started.html>

## Updating the blog
Load the blog source directory into vscode:
```
# Navigate to the blog site repository directory
cd ~/Desktop/nikola-env/blog2025

# Activate virtual environment
source ../bin/activate

# Open directory in vscode
code .
```
## Creating a new post
Open a terminal and type ``nikola new_post``, then edit the new file in the ``posts`` directory.

## Deploying updates to GitHub pages
Open a terminal and type ``nikola github_deploy``.


