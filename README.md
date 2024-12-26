# Commands Used

`For create a New Directory and Initialize as a git Repo:`
``` bash
mkdir my-project
cd my-project/
git init
```

`For create a README.md File:`
``` bash
echo "# My project" > README.md
```
` For make an Initial Commit:`
``` bash
git add .
git commit -m "Added README.md file"
```
`For push the repo to my remote repository:`
``` bash
git remote add  origin git@github.com:prosenjit72/my-project.git
git remote -v
git branch -M main
git push -u origin main
```
`Here:` `git branch -M main` used for rename the default branch.

`For Create feature-1 branch and switch the branch:`
``` bash
git checkout -b feature-1
```
`Make Changes and Commit:`
``` bash
echo "Feature-1 content" > feature-1.txt
git add .
git commit -m "Added feature-1.txt in the feature-1 branch"
```
`Switch Back to main and Create feature-2 Branch:`
``` bash
git checkout main
git checkout -b feature-2
```
`Make Changes and Commit for feature-2:`
``` bash
echo "Feature-2 content" > feature-2.txt
git add .
git commit -m "Added feature-2.txt in the feature-2 branch"
```
`Push Both Branches to Remote`
``` bash
git push origin feature-1
git push origin feature-2
```
`Create Pull Requests on GitHub`
``` bash
First go to GitHub repository.
Create a PR for feature-1 to main.
Create another PR for feature-2 to main.
```
`Switch to feature-1 locally:`
``` bash
git checkout feature-1
git rebase main
```
`Now Push the updated branch:`
``` bash
git push origin feature-1 --force
```
`Repeat for feature-2:`
``` bash
git checkout feature-2
git rebase main
git push origin feature-2 --force
```
`Merged the feature-1 PR first in GitHub`

`Then update the main branch locally:`
``` bash
git checkout main
git pull origin main
```
`Rebase feature-2 onto the updated main:`
``` bash
git checkout feature-2
git rebase main
git push origin feature-2 --force
```
`Here:` --force replaces the remote branch with your local branch, forcing the push, even if the history is different.

`Then merge the feature-2 PR into main`

`For verify the commit history:`
``` bash
git checkout main
git log --oneline
```
`Now deleted the feature branches locally:`
``` bash
git branch -d feature-1
git branch -d feature-2
```
`Also deleted the feature branches remotely:`
``` bash
git push origin --delete feature-1
git push origin --delete feature-2
```