# Setting up Your Github Org

Please follow the below instructions to set-up your Github organization and repo (note: only one person per team needs to do this).

## Creating a Github Organization

1. Go to [github](https://github.com)
2. Click the "+" button in the upper righthand corner
3. Select "New organization" from the dropdown
4. Select the free tier
5. Input a name for your organization (eg graceshopper-team-awesome)
6. Input your personal email, select "My personal account", and click "Next"
7. Add all your teammates to this organization by searching for their Github usernames. Please also add your fellow and your instructor. Members should be made owners. *Note* you can add people after this step, so feel free to continue on if you're missing some usernames.
8. Click "Complete set-up"
9. No need to fill out this next page ("Welcome to Github"). You can scroll to the bottom and click "Submit".

## Creating and Initializing your repo

1. Go to your organizations homepage (eg https://github.com/graceshopper-team-awesome)
2. Select the green button "Create a new repository"
3. Enter the name of your repository (eg graceshopper-project)
4. Select "Public" for the visibility
5. Select "Create Repository" (create a blank repo, do not check any boxes that add default files).
6. Copy the URL of your repo and clone it to your local machine: `git clone https://github.com/YOUR-PROJECT-URL.git`
7. `cd` into your new repo's folder
8. Follow the instructions from the [Boilerplate repo](https://github.com/fullstackacademy/fs-app-template) where you will be instructed to run these commands:
  ```
  git remote add boilermaker https://github.com/FullstackAcademy/fs-app-template.git
  git fetch boilermaker
  git merge boilermaker/main
  git branch -m master main
  ```
9. Run one more command: `git push origin main`
10. Refresh your Github page and you should see your repo initialized with the boilerplate code.

## Protect your Main Branch

1. From your repo's github page, select "Settings" (rightmost option under the repo name)
2. On the sidebar, select "Branches"
3. Click "Add rule"
4. Put `main` in the text field for "Branch name pattern"
5. Select two checkboxes: "Require pull request reviews before merging" and "Include administrators".
6. Finish by selecting "Create"
