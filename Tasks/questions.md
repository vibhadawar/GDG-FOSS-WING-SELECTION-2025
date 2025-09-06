### Answer the following questions in you own words.

> It's not necessary that you havee to know and answer all the questions. Just answer the ones
> you know and write in your own words.

1. Give the difference between the remotes - upstream and origin - with an example.

You answer:
Origin: It is the default name give to the remote repository from which you cloned from. 
For ex: git clone https://github.com/vibhadawar/project.
Upstream: It is the original repository from which you forked.
For ex: git remote add upstream https://github.com/google/ML-Project.git

2. You have two branches A and B and you have currently made some changes in branch A.
You want to move into branch B but do not want to commit the current changes in branch A.
What will you do?

You answer: We will switch branches without committing changes in current branch. we will just save the changes.
use  -> git checkout B for branch switching to B  and git stash to save changes in branch A.

3. You were assigned a work to implement a feature and create a PR to your organization's remote repository.
For this you made a branch (say A) and made some changes and commited them. Now you moved to some other branch 
(say B) to do some other assigned work. But later you realisd that have to complete the task assigned earlier 
first and commited some changes in branch B which are meant for branch A. How will you use git to bring the 
changes from branch B to branch A?

You answer: We can merge b into a 
by using git checkout A and git merge B

4. What is the difference between fetching changes and pulling changes?

Your answer:Fetching changes means  downloading changes from remote but not merging into the local branch.
Pulling changes means downloading changes and automatically merging them into the current branch.

5. What does -i flag stand for? What is it's significance in git?

You answer: -i in this stands for interactive.
It is used in commands like git add -i to selectively stage changes , either file by file or part by part.


6. You are working in an organization that follows very strict guidelines for PRs and commits.
You made three commits in your PR and the maintainer says you were supposed to make a single commit.
What will you do in this case?

You answer:
we have two different options to do so:
1.Interactive Base:
git rebase -i HEAD~3               ->it combines the last three commits and mark the first commit as pick and all others as squash.
git push --force
2.Reset & Recommit
git reset --soft HEAD~3          ->It moves back 3 commits but keep changes
git commit -m                      -> here single commit with all changes"
git push --force



7. Explain `git merge` and `git rebase` with example(s).
You answer:
git merge: It combines changes from another branch while keeping the  history.
git rebase: It moves your commits on top of another branch, creating a linear history.

8. Write the flow how you create a repository and push changes to it. Also mention the commands used at each step.

You answer:
1.Create a repository on github:
Go to github->click new repository->assign a name->create the repository
2.Initialize a git in your local folder
git init
3.add your files 
git add .
4.commit changes
git commit -m "Initial commit"
5.Add remote Repository
git remote add origin  https://github.com/vibhadawar/foss_gdg.git
6.push changes 
git push -u origin main
7.Make more changes and push later
git add .
git commit -m "changes"
git push


9. How would you prevent a file or folder from getting tracked by git?

Your answer: we should use .gitignore


10. You did not implement the step you mentioned in question 8 and now you have committed and pushed your database's
secret key to the github. How will you remove the key from your git's commit history to avoid any misuse?

You answer:
1. remove the file from  all the commits  locally using  git filter- branch command:
git filter-branch --force --index-filter \
2. forcefully push the cleaned history to github:
git push origin --force --all
3.add the file to gitignore to prevent it from getting committed again
---